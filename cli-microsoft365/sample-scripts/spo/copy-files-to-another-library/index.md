-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - files
  - libraries
  - migration
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Copy files to another SharePoint Library in another site

Author: [Garry Trinder](https://github.com/garrytrinder), [Adam](https://github.com/Adam-it), Inspired by Veronique Lengelle

This script shows how you can use the CLI to:

- when copyKeepingSameFolderStructure is true - copy all files and folders from source library to a different library in different SharePoint site keeping the same folder and subfolder structure
- when copyKeepingSameFolderStructure is false - copy all files from all folders and subfolders from source library to a different library to a root folder in different SharePoint

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  Write-host 'Copy files to another SharePoint Library in another site'

  function Copy-FilesFromFolderToLibrary(
    [Parameter(Mandatory = $True)][string] $tenatUrl,
    [Parameter(Mandatory = $True)][string] $sourceSite,
    [Parameter(Mandatory = $True)][string] $folder,
    [Parameter(Mandatory = $True)][string] $targetLibrary,
    [Parameter(Mandatory = $True)][string] $targetSite) {
      Write-Host $folder

      $allFolders = m365 spo folder list --webUrl "$tenatUrl$sourceSite" --parentFolderUrl $folder --output 'json'
      $allFolders = $allFolders | ConvertFrom-Json
      foreach ($innerfolder in $allFolders) {
        if ($innerfolder.Name -ne 'Forms') {
          $folderUrl = $innerfolder.ServerRelativeUrl -replace $sourceSite, ''
          Copy-FilesFromFolderToLibrary -tenatUrl $tenatUrl -sourceSite $sourceSite -folder $folderUrl -targetLibrary $targetLibrary -targetSite $targetSite
        }
      }

      $allFiles = m365 spo file list --webUrl "$tenatUrl$sourceSite" --folderUrl $folder.substring(1) --output 'json'
      $allFiles = $allFiles | ConvertFrom-Json
      foreach ($file in $allFiles) {
        $fileUrl = $file.ServerRelativeUrl -replace $sourceSite, ''
        m365 spo file copy --webUrl "$tenatUrl$sourceSite" --sourceUrl $fileUrl --targetUrl "$targetSite/$targetLibrary"
      }
  }

  function Copy-LibraryToLibrary(
    [Parameter(Mandatory = $True)][string] $tenatUrl,
    [Parameter(Mandatory = $True)][string] $sourceLibrary,
    [Parameter(Mandatory = $True)][string] $sourceSite,
    [Parameter(Mandatory = $True)][string] $targetLibrary,
    [Parameter(Mandatory = $True)][string] $targetSite,
    [Parameter(Mandatory = $True)][bool] $copyKeepingSameFolderStructure) {
    if ($copyKeepingSameFolderStructure) {
      Write-host "Copy the same structure"

      $allFolders = m365 spo folder list --webUrl "$tenatUrl$sourceSite" --parentFolderUrl "/$sourceLibrary" --output 'json'
      $allFolders = $allFolders | ConvertFrom-Json
      foreach ($folder in $allFolders) {
        if ($folder.Name -ne 'Forms') {
          $folderName = $folder.Name
          m365 spo folder copy --webUrl "$tenatUrl$sourceSite" --sourceUrl "/$sourceLibrary/$folderName" --targetUrl "$targetSite/$targetLibrary"
        }
      }

      $allFiles = m365 spo file list --webUrl "$tenatUrl$sourceSite" --folderUrl $sourceLibrary --output 'json'
      $allFiles = $allFiles | ConvertFrom-Json
      foreach ($file in $allFiles) {
        $fileUrl = $file.ServerRelativeUrl -replace $sourceSite, ''
        m365 spo file copy --webUrl "$tenatUrl$sourceSite" --sourceUrl $fileUrl --targetUrl "$targetSite/$targetLibrary"
      }
    }
    else {
      Write-host "Copy files to the root target folder"

      Copy-FilesFromFolderToLibrary -tenatUrl $tenatUrl -sourceSite $sourceSite -folder "/$sourceLibrary" -targetLibrary $targetLibrary -targetSite $targetSite
    }
  }

  Write-host 'ensure logged in'
  $m365Status = m365 status --output text
  if ($m365Status -eq "Logged Out") {
    m365 login
  }

  $tenatUrl = 'https://contoso.sharepoint.com'
  $sourceLibrary = 'Shared Documents'
  $sourceSite = '/sites/FromSite'
  $targetLibrary = 'Shared Documents'
  $targetSite = '/sites/ToSite'
  $copyKeepingSameFolderStructure = $false
  Copy-LibraryToLibrary -tenatUrl $tenatUrl -sourceLibrary $sourceLibrary -sourceSite $sourceSite -targetLibrary $targetLibrary -targetSite $targetSite -copyKeepingSameFolderStructure $copyKeepingSameFolderStructure
  ```

  </TabItem>
</Tabs>
