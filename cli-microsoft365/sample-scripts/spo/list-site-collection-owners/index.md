-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - reports
  - security
  - users
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# List site collection owners

Author: [Patrick Lamber](https://www.nubo.eu/EXAMPLE_SECRET_VALUE_PLACEHOLDER/)

This script helps you to list and export all site collection owners in your SharePoint Online sites.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $fileExportPath = "<PUTYOURPATHHERE.csv>"

  $m365Status = m365 status --output text

  if ($m365Status -eq "Logged Out") {
    # Connection to Microsoft 365
    m365 login
  }

  $results = @()
  Write-host "Retrieving all sites..."
  $allSPOSites = m365 spo site list | ConvertFrom-Json
  $siteCount = $allSPOSites.Count

  Write-Host "Processing $siteCount sites..."
  #Loop through each site
  $counter = 0
  foreach($site in $allSPOSites){
      $counter++
      Write-Host "Processing $($site.Url)... ($counter/$siteCount)"
      $users = m365 spo user list --webUrl $site.Url -o json | ConvertFrom-Json
      $owners = $users.value | where { $_.IsSiteAdmin -eq $true } 
      
      foreach($owner in $owners){
          $results += [pscustomobject][ordered]@{
              SiteUrl = $site.Url
              LoginName = $owner.LoginName
              Title = $owner.Title
              Email = $owner.Email
          }
      }
  }
  Write-Host "Exporting file to $fileExportPath..."
  $results | Export-Csv -Path $fileExportPath -NoTypeInformation
  Write-Host "Completed."
  ```

  </TabItem>
</Tabs>
