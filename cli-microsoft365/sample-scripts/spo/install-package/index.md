-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - apps
  - deployment
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Install .sppkg package in the specified app catalog

Author: [Saurabh Tripathi](https://github.com/saurabh7019)

The purpose of this script is to install .sppkg package in the specified app catalog and approve all the permissions requested by the app. It is primarily used during development after executing the 'gulp package-solution' command. If the package name is not provided as a parameter, the script automatically detects and installs the package based on the project structure. To install a package from the site collection app catalog, use this script in conjunction with the '-appCatalogUrl' parameter. If the app catalog is not found in the given site URL, it will add a site collection app catalog.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  param (
      [Parameter(Mandatory = $false, HelpMessage = "Specify the absolute or relative path to the solution package file. If not provided, searches for all .sppkg files.")]
      [string]$package,
      [Parameter(Mandatory = $false, HelpMessage = "Specify the URL of the app catalog site. If not provided, the package will be removed from the tenant app catalog.")]
      [string]$appCatalogSiteUrl,
      [Parameter(Mandatory = $false, HelpMessage = "Specify if the package should be deployed in the whole tenant.")]
      [bool]$tenantDeployment = $false
  )

  Clear-Host

  function Install-Package {
      try {
          $statusOutput = m365 status
          if ($statusOutput -eq "Logged Out") {
              Write-Host "Logging in to Microsoft 365...";
              m365 login --authType browser
          }

          $packages = if ([string]::IsNullOrEmpty($package)) {
              Get-ChildItem -Path $PSScriptRoot -Filter *.sppkg -Recurse
          }
          else {
              if (Test-Path $package -PathType Leaf) {
                  Get-Item -Path $package
              }
              else {
                  Write-Host "File not found: $package" -ForegroundColor Red
              }
          }

          if ($packages.Count -ne 0) {
              $appCatalogUrl = Get-AppCatalogUrl $appCatalogSiteUrl
              $packages.ForEach({ Deploy-Package $_ $appCatalogUrl })
          }
      }
      catch {
          Write-Host $_.Exception -ForegroundColor DarkRed
      }
  }

  function Get-AppCatalogUrl([string]$url) {
      if ([string]::IsNullOrEmpty($url)) {
          return m365 spo tenant appcatalogurl get | ConvertFrom-Json
      }

      $site = m365 spo site get -u $url | ConvertFrom-Json
      if ($site) {
          $appCatalog = m365 spo site appcatalog list --query "[?SiteID == '$($site.Id)']" | ConvertFrom-Json
          if ($appCatalog.Count -eq 0) {
              m365 spo site appcatalog add --siteUrl $url
              Write-Host "App catalog added to the site '$url'" -ForegroundColor Green
          }
          else {
              Write-Host "App catalog already exists on the site '$url'" -ForegroundColor Yellow
          }
          return $url
      }
  }

  function Deploy-Package([System.IO.FileInfo]$package, [string]$url) {
      Write-Host ("Deploying package {0} in {1}..." -f $package.Name, $url) -ForegroundColor Yellow

      $appCatalogScope = if ([string]::IsNullOrEmpty($appCatalogSiteUrl)) {
          "tenant"
      }
      else {
          "sitecollection"
      }
          
      $app = m365 spo app add --filePath $package.FullName --appCatalogUrl $url --appCatalogScope $appCatalogScope --overwrite | ConvertFrom-Json
      $appToDeploy = m365 spo app get --name $app.Name --appCatalogUrl $url --appCatalogScope $appCatalogScope | ConvertFrom-Json
      if ($tenantDeployment -and $EXAMPLE_SECRET_VALUE_PLACEHOLDER) {
          m365 spo app deploy --id $appToDeploy.ID --appCatalogUrl $url --appCatalogScope $appCatalogScope --skipFeatureDeployment
      }
      else {
          m365 spo app deploy --id $appToDeploy.ID --appCatalogUrl $url --appCatalogScope $appCatalogScope
      }

      if (-not [string]::IsNullOrEmpty($appToDeploy.AadPermissions)) {
          Approve-Permissions($appToDeploy.AadPermissions)
      }
          
      Write-Host ("Package {0} successfully deployed in {1}." -f $package.Name, $url) -ForegroundColor Green
  }

  function Approve-Permissions([string]$aadPermissions) {
      Write-Host "`tApproving permissions" -ForegroundColor Yellow
      $resources = @{}
      $resourceScopes = $aadPermissions -split ';'

      foreach ($resourceScope in $resourceScopes) {
          $resource, $scope = $resourceScope -split ','
          $resource = $resource.Trim()
          $scope = $scope.Trim()

          if ($resources.ContainsKey($resource)) {
              $resources[$resource] += $scope
          }
          else {
              $resources[$resource] = @($scope)
          }
      }

      foreach ($resource in $resources.Keys) {
          $scopes = $resources[$resource]
          foreach ($scope in $scopes) {
              $existingGrant = m365 spo serviceprincipal grant list --query "[?Resource == '${resource}' && Scope == '${scope}']" | ConvertFrom-Json
              if ($existingGrant.Count -eq 0) {
                  $grant = m365 spo serviceprincipal grant add --resource "$resource" --scope "$scope" | ConvertFrom-Json
                  Write-Host "`t`tPermission '$($grant.Scope)' for the resource '$($grant.Resource)' granted" -ForegroundColor Green
              }
              else {
                  Write-Host "`t`tPermission '${scope}' for the resource '${resource}' already granted" -ForegroundColor Yellow 
              }
          }
      }
      Write-Host "`tApproved permissions" -ForegroundColor Green
  }

  Install-Package
  #Install-Package -package "sharepoint\solution\sample.sppkg" -appCatalogSiteUrl $Url -tenantDeployment $true
  ```

  </TabItem>
</Tabs>
