-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - apps
  - cleanup
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Uninstall .sppkg package from the specified app catalog

Author: [Saurabh Tripathi](https://github.com/saurabh7019)

The purpose of this script is to uninstall .sppkg package from the specified app catalog. It is primarily used during development after executing the `gulp package-solution` command. If the package name is not provided as a parameter, the script automatically detects and removes the package based on the project structure. To remove a package from the site collection app catalog, use this script in conjunction with the '-appCatalogUrl' parameter.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  param (
  [Parameter(Mandatory = $false, HelpMessage = "Specify the package name. If not provided, searches for all .sppkg files.")]
  [string]$package,
  [Parameter(Mandatory = $false, HelpMessage = "Specify the URL of the app catalog site. If not provided, the package will be removed from the tenant app catalog.")]
  [string]$appCatalogSiteUrl
  )

  Clear-Host

  function Uninstall-Package {
      try {
          $statusOutput = m365 status
          if ($statusOutput -eq "Logged Out") {
              Write-Host "Logging in to Microsoft 365...";
              m365 login --authType browser
          }

          $packageNames = if ([string]::IsNullOrEmpty($package)) {
              Get-ChildItem -Path $PSScriptRoot -Filter *.sppkg -Recurse | Select-Object -ExpandProperty Name
          }
          else {
              @($package)
          }
          $appCatalogUrl = Get-AppCatalogUrl $appCatalogSiteUrl
          $packageNames.ForEach({ Remove-Package $_ $appCatalogUrl })
      }
      catch {
          Write-Host $_.Exception -ForegroundColor DarkRed
      }
  }

  function Get-AppCatalogUrl([string]$url) {
      if ([string]::IsNullOrEmpty($url)) {
          $appCatalogUrl = m365 spo tenant appcatalogurl get | ConvertFrom-Json
      }
      else {
          $appCatalogUrl = $url
      }
      return $appCatalogUrl
  }

  function Remove-Package([string]$packageName, [string]$url) {
      Write-Host ("Uninstalling package {0} from {1}..." -f $packageName, $url) -ForegroundColor Yellow
      $app = if ([string]::IsNullOrEmpty($appCatalogSiteUrl)) {
          m365 spo app get --name $packageName --appCatalogUrl $url | ConvertFrom-Json
      }
      else {
          m365 spo app get --name $packageName --appCatalogUrl $url --appCatalogScope sitecollection | ConvertFrom-Json
      }

      if ($app) {
          if ([string]::IsNullOrEmpty($appCatalogSiteUrl)) {
              m365 spo app retract --id $app.ID --appCatalogUrl $url --force
              m365 spo app remove --id $app.ID --appCatalogUrl $url --force
          }
          else {
              m365 spo app retract --id $app.ID --appCatalogUrl $url --appCatalogScope sitecollection --force
              m365 spo app remove --id $app.ID --appCatalogUrl $url --appCatalogScope sitecollection --force
          }
          Write-Host ("Package {0} successfully uninstalled from {1}." -f $packageName, $url) -ForegroundColor Green
      }
  }

  Uninstall-Package
  #Uninstall-Package -appCatalogUrl $Url -package sample.sppkg
  ```

  </TabItem>
</Tabs>
