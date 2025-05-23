-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - governance  
  - lists
  - reports
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Lists the empty folders for each library on a specific site

Author: [Nanddeep Nachan](https://github.com/nanddeepn), Inspired by [Veronique Lengelle](https://veronicageek.com/2020/find-empty-folders-in-spo)

This script lists all the empty folders for each library on a specific site. This can be useful for Governance, especially with the number of libraries we can create in SharePoint.

The script loops through each document library in a site where the folder size should be 0 (zero), and export the results in csv file.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  param
  (
    [Parameter(Mandatory = $true, HelpMessage="URL of the site")][string] $WebUrl
  )

  try {
    $m365Status = m365 status
    if ($m365Status -eq "Logged Out") {
      Write-Host "Logging in the User!"
      m365 login --authType browser
    }

    Write-Host "Retrieving all document libraries in the site $WebUrl"
    $allLibs = m365 spo list list --webUrl $WebUrl --query "[?BaseTemplate == ``101``]" -o json | ConvertFrom-Json

    $resultsEmptyFolders = @()

    foreach($library in $allLibs) {
      Write-Host "Processing document library: $($library.Title)"
      $allFolders = m365 spo folder list --webUrl $WebUrl --parentFolderUrl $library.RootFolder.ServerRelativeUrl --fields "Name,ServerRelativeUrl,TimeCreated,CreatedBy,TimeLastModified" --recursive --filter "ItemCount eq 0" -o json | ConvertFrom-Json

      foreach($folder in $allFolders) {
        $resultsEmptyFolders += [PSCustomObject]@{              
            FolderName = $folder.Email
            FolderPath = $group.LoginName
            CreatedDate = $folder.Title
            ModifiedDate = $folder.Title
        }
      }
    }

    $resultsEmptyFolders | Export-Csv -Path .mpty-folders.csv -NoTypeInformation    
  }
  catch {
    Write-Host -f Red "Error retrieving empty folders: " $_.Exception.Message
  }

  Write-Host "Finished"
  ```

  </TabItem>
</Tabs>
