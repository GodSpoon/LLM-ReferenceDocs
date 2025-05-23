-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - guests
  - security
  - users
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# List all external users in all site collections

Author: [Albert-Jan Schot](https://www.cloudappie.nl/migration-report-external-users/)

This script helps you to list all external users in all SharePoint Online sites. It provides insights in who the users are, and if available who they where invited by.

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
  Write-host "Retrieving all sites and check external users..."
  $allSPOSites = m365 spo site list | ConvertFrom-Json
  $siteCount = $allSPOSites.Count

  Write-Host "Processing $siteCount sites..."
  #Loop through each site
  $siteCounter = 0

  foreach ($site in $allSPOSites) {
    $siteCounter++
    Write-Host "Processing $($site.Url)... ($siteCounter/$siteCount)"

    Write-host "Retrieving all external users ..."

    $users = m365 spo user list --webUrl $site.Url --output json --query "[?contains(LoginName,'#ext#')]" | ConvertFrom-Json

    foreach ($user in $users) {
      $externalUserObject = m365 spo externaluser list --siteUrl $site.url -o json --query "[?AcceptedAs == '$($user.Email)']" | ConvertFrom-Json

      $results += [pscustomobject][ordered]@{
        UserPrincipalName = $user.UserPrincipalName
        Email             = $user.Email
        InvitedAs         = $externalUserObject.InvitedAs
        WhenCreated       = $externalUserObject.WhenCreated
        InvitedBy         = $externalUserObject.InvitedBy
        Url               = $site.Url
      }
    }
  }

  Write-Host "Exporting file to $fileExportPath..."
  $results | Export-Csv -Path $fileExportPath -NoTypeInformation
  Write-Host "Completed."
  ```

  </TabItem>
</Tabs>
