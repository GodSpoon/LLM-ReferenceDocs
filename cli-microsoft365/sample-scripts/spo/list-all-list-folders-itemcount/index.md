-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - files  
  - libraries  
  - reports
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Lists number of files in all lists and folders for the given site

Author: [Albert-Jan Schot](https://www.cloudappie.nl/lists-file-count-cli-microsoft-365/)

List all Lists, the folders and sub folders in a given site, and output the item count. Each folder is processed recursively. By default only non hidden document libraries are processed. As specified with the filter `$false -eq $list.Hidden -and $list.BaseTemplate -eq "101"`. The output is a CSV that contains the itemcount for each list and folder found in the specified site collection.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $siteUrl = "<PUTYOURURLHERE>"
  $fileExportPath = "<PUTYOURPATHHERE.csv>"

  $m365Status = m365 status --output text

  if ($m365Status -eq "Logged Out") {
    # Connection to Microsoft 365
    m365 login
  }

  [System.Collections.ArrayList]$results = @()

  function Get-Folders($webUrl, $folderUrl) {
    $folders = m365 spo folder list -u $webUrl --parentFolderUrl $folderUrl -o json | ConvertFrom-Json

    foreach ($folder in $folders) {
      $folderStats = m365 spo folder get -u $webUrl --url $folder.ServerRelativeUrl -o json | ConvertFrom-Json

      Write-Output "Processing folder: $($folder.ServerRelativeUrl);"
      [void]$results.Add([pscustomobject]@{ Url = $folder.ServerRelativeUrl; ItemCount = $folderStats.ItemCount; Type = "Folder"; })

      Get-Folders $webUrl $folder.ServerRelativeUrl
    }
  }

  $allLists = m365 spo list list -u $siteUrl -o json | ConvertFrom-Json

  foreach ($list in $allLists) {
    if ($false -eq $list.Hidden -and $list.BaseTemplate -eq "101") {
      Write-Output "Processing $($list.RootFolder.ServerRelativeUrl)"
      [void]$results.Add([PSCustomObject]@{ Url = $list.RootFolder.ServerRelativeUrl; ItemCount = $list.ItemCount; Type = "List"; })

      Get-Folders $siteUrl $list.RootFolder.ServerRelativeUrl
    }
  }

  $results | Export-Csv -Path $fileExportPath -NoTypeInformation
  ```

  </TabItem>
</Tabs>
