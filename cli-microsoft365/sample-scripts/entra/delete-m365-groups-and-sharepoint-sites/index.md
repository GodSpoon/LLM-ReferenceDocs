-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:  
  - cleanup
  - groups
  - sites
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Delete all Microsoft 365 groups and SharePoint sites

Author: [Patrick Lamber](https://www.nubo.eu/Delete-All-SPO-Sites-And-M365-Groups/)

Another example how you can delete all Microsoft 365 Groups and SharePoint Online sites in your development environment.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  ### Warning. Use with caution. This script deletes all M365 Groups and SPO Sites in your tenant
  $devAccount = "<putyourupnhereforsecuritycheck>"
  ### Deletes the resources from the recyclebin. The CLI does not support this feature yet
  $skipRecycleBin = $true

  $m365Status = m365 status --output text
  Write-Host $m365Status
  if ($m365Status -eq "Logged Out") {
    # Connection to Microsoft 365
    m365 login
    $m365Status = m365 status
  }

  # Check added as security measure
  if ($m365Status[0].ToString().IndexOf($devAccount) -eq -1) {
    Write-Host "The user does not match the target development account. Stopping..." -ForegroundColor Red
    return;
  }

  Write-host "Retrieving all groups..."
  $allGroups = m365 entra m365group list -o json | ConvertFrom-Json
  $groupCount = $allGroups.Count

  Write-Host "Processing $groupCount sites..."
  #Loop through each site
  $groupCounter = 0

  foreach ($group in $allGroups) {
    $groupCounter++
    Write-Host "Deleting $($group.displayName)... ($groupCounter/$groupCount)"
    m365 entra m365group remove --id $group.id --force
  }

  Write-host "Retrieving all SPO sites..."
  $allSites = m365 spo site list --query "[?contains(Template,'SITEPAGEPUBLISHING') || contains(Template,'STS')]" | ConvertFrom-Json
  $siteCount = $allSites.Count

  Write-Host "Processing $siteCount sites..."
  #Loop through each site
  $siteCounter = 0

  foreach ($site in $allSites) {
    $siteCounter++
    Write-Host "Deleting $($site.Url)... ($siteCounter/$siteCount)"
    m365 spo site remove --url $site.Url --skipRecycleBin $skipRecycleBin --force
  }
  ```

  </TabItem>
</Tabs>
