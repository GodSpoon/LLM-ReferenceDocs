-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - customizations
  - reports
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Export Configurations of Tenant Wide Extensions

Author: [Joseph Velliah](https://sprider.blog/export-configs-tenant-wide-extensions)

The SharePoint Admin Center provides various governance features, but there is no way to easily export Configurations of Tenant Wide Extensions from the SharePoint admin center for governance activities. This script retrieves Tenant Wide Extension configurations from the App Catalog and exports the same in a comma-separated values (CSV) file.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $resultDir = "Output"
  $listName = "Tenant Wide Extensions"
  $fields = $fields = "Title, Modified, Created, AuthorId, EditorId, TenantWideExtensionComponentId, TenantWideExtensionComponentProperties, TenantWideExtensionListTemplate, TenantWideExtensionWebTemplate, TenantWideExtensionSequence, TenantWideExtensionHostProperties, TenantWideExtensionLocation, TenantWideExtensionDisabled"

  $executionDir = $PSScriptRoot
  $outputDir = "$executionDir/$resultDir"
  $outputFilePath = "$outputDir/$(get-date -f yyyyMMdd-HHmmss)-tenantwideextensions.csv"

  if (-not (Test-Path -Path "$outputDir" -PathType Container)) {
      Write-Host "Creating $outputDir folder..."
      New-Item -ItemType Directory -Path "$outputDir"
  }

  $appCatalogUrl = m365 spo tenant appcatalogurl get

  if ($appCatalogUrl) {
      $spolItems = m365 spo listitem list --listTitle $listName --webUrl $appCatalogUrl --fields $fields  -o json | ConvertFrom-Json

      if ($spolItems.Count -gt 0) {
          $configurations = @()

          foreach ($spolItem in $spolItems) {
              $author = m365 spo user get --webUrl $appCatalogUrl --id $spolItem.AuthorId -o json | ConvertFrom-Json
              $editor = m365 spo user get --webUrl $appCatalogUrl --id $spolItem.EditorId -o json | ConvertFrom-Json

              $configurationObject = New-Object -TypeName PSObject

              $configurationObject | Add-Member -MemberType NoteProperty -Name "Title" -Value $spolItem.Title
              $configurationObject | Add-Member -MemberType NoteProperty -Name "Modified" -Value $spolItem.Modified
              $configurationObject | Add-Member -MemberType NoteProperty -Name "Created" -Value $spolItem.Created
              $configurationObject | Add-Member -MemberType NoteProperty -Name "Author" -Value $author.Title
              $configurationObject | Add-Member -MemberType NoteProperty -Name "Editor" -Value $editor.Title
              $configurationObject | Add-Member -MemberType NoteProperty -Name "TenantWideExtensionComponentId" -Value $spolItem.TenantWideExtensionComponentId
              $configurationObject | Add-Member -MemberType NoteProperty -Name "TenantWideExtensionComponentProperties" -Value $EXAMPLE_SECRET_VALUE_PLACEHOLDER
              $configurationObject | Add-Member -MemberType NoteProperty -Name "TenantWideExtensionListTemplate" -Value $EXAMPLE_SECRET_VALUE_PLACEHOLDER
              $configurationObject | Add-Member -MemberType NoteProperty -Name "TenantWideExtensionWebTemplate" -Value $spolItem.TenantWideExtensionWebTemplate
              $configurationObject | Add-Member -MemberType NoteProperty -Name "TenantWideExtensionSequence" -Value $spolItem.TenantWideExtensionSequence
              $configurationObject | Add-Member -MemberType NoteProperty -Name "TenantWideExtensionHostProperties" -Value $EXAMPLE_SECRET_VALUE_PLACEHOLDER
              $configurationObject | Add-Member -MemberType NoteProperty -Name "TenantWideExtensionLocation" -Value $spolItem.TenantWideExtensionLocation
              $configurationObject | Add-Member -MemberType NoteProperty -Name "TenantWideExtensionDisabled" -Value $spolItem.TenantWideExtensionDisabled

              $configurations += $configurationObject
          }

          $configurations | Export-Csv -Path "$outputFilePath" -NoTypeInformation
          Write-Host "Open $outputFilePath to review Tenant Wide Extensions configurations report."
      }
      else {
          Write-Host "Tenant Wide Extensions list is empty."
      }
  }
  else {
      Write-Host "Unable to get App Catalog Url."
  }
  ```

  </TabItem>
</Tabs>
