-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - reports
  - sites
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# List SharePoint sites where the particular app is installed

This script helps you to list all sites in SharePoint Online, where a particular app is installed.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  param
  (
    [Parameter(Mandatory = $false, HelpMessage = "ID of the app")][string] $AppID,
    [Parameter(Mandatory = $false, HelpMessage = "Name of the app")][string] $AppName
  )

  if ($AppID -and $AppName) {
    throw "Please specify either AppID or AppName, but not both."
  }

  if ((-not $AppID) -and (-not $AppName)) {
    throw "Please specify either AppID or AppName."
  }

  try {
    $m365Status = m365 status
    if ($m365Status -match "Logged Out") {
      Write-Host "Logging in the User!"
      m365 login --authType browser
    }

    $results = @()

    $queryText = ""
    if ($AppID) {
      $queryText = "[?AppId == '$AppID']"
    }
    else {
      $queryText = "[?Title == '$AppName']"
    }

    Write-Host "Retrieving all sites..."
    $allSPOSites = m365 spo site list | ConvertFrom-Json

    foreach ($site in $allSPOSites) {
      Write-Host "Processing site $($site.Url)..."
      $appInstance = m365 spo app instance list --siteUrl $site.Url --query $queryText | ConvertFrom-Json

      if ($appInstance.count -gt 0) {
        $results += [pscustomobject]@{
          SiteURL = $site.Url
          Title   = $site.Title
        }
      }
    }

    Write-Host $results
  }
  catch {
    Write-Host -f Red "Error listing sites where the particular app is installed: " $_.Exception.Message
  }

  Write-Host "Finished"
  ```

  </TabItem>
</Tabs>
