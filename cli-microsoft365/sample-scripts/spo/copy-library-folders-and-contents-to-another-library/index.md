-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - files
  - folders
  - libraries
  - migration
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Copy library folders and contents to another library

Author: [Nico De Cleyre](https://www.nicodecleyre.com)

The following script shows how you can copy all library folders and contents to another library.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  param
  (
      [Parameter(Mandatory = $true, HelpMessage = "The source site url")][string] $SiteURL,
      [Parameter(Mandatory = $true, HelpMessage = "The server- or site-relative URL of the source document library")][string] $SourceFolder,
      [Parameter(Mandatory = $true, HelpMessage = "The server- or site-relative URL of the destination document library")][string] $DestinationFolder,
      [Parameter(Mandatory = $false, HelpMessage = "The destination site url")][string] $DestinationUrl
  )
  try {
      #Connect to m365
      $M365Status = m365 status
      if($M365Status -match "Logged Out"){
          Write-Host "Logging in the User!"
          m365 login --authType browser
      }

      # Set the destination URL the same as the source URL if it's not given
      if($DestinationUrl -eq ''){
          $DestinationUrl = $SiteURL
      }

      $SourceFolders = m365 spo folder list --webUrl $SiteURL --parentFolderUrl $SourceFolder | ConvertFrom-Json
      foreach($Folder in $SourceFolders){
          if($Folder.Name -eq "Forms"){
              continue
          }
          $DestinationFolderUrl = $Folder.ServerRelativeUrl.Replace($SourceFolder, $DestinationFolder)

          # Create level 1 folders first
          Write-Host "Creating '$($Folder.Name)' in '$DestinationFolder'" -ForegroundColor Yellow
          m365 spo folder add --webUrl $DestinationUrl --parentFolderUrl $DestinationFolder --name $Folder.Name | Out-null

          # Copy everything (folders and files) to this target level 1 folder
          Write-Host "Copying '$($Folder.ServerRelativeUrl)' to '$DestinationFolderUrl'" -ForegroundColor Cyan
          m365 spo folder copy --webUrl $SiteURL --sourceUrl $Folder.ServerRelativeUrl --targetUrl $DestinationFolderUrl
      }

      # Copy files from root
      $SourceFiles = m365 spo file list --webUrl $SiteUrl --folderUrl $SourceFolder --fields "ServerRelativeUrl" | ConvertFrom-Json
      foreach($File in $SourceFiles){
          $DestinationFileUrl = $DestinationUrl.Substring(0,$DestinationUrl.ToLower().IndexOf("/sites")) + $DestinationFolder

          Write-Host "Copying '$($File.ServerRelativeUrl)' to '$DestinationFileUrl'" -ForegroundColor Cyan
          m365 spo file copy --webUrl $SiteURL --sourceUrl $File.ServerRelativeUrl --targetUrl $DestinationFileUrl
      }

      Write-host "Document library $SourceFolder is successfully copied to $DestinationFolder" -f Green
  }
  catch {
      Write-Host -f Red "Error making the list $ListName read-only: " $_.Exception.Message
  }
  ```

  </TabItem>
</Tabs>
