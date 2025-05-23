-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - spo
  - page 
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Remove SharePoint page header

The script removes a SharePoint page header.

## Disclaimer
The script will work only for pages created using the new approach for adding page headers. Headers created using the LayoutWebpartsContent property of the page will not be recognized by the script.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $pageName = "pagename.aspx"
  $webUrl = "https://contoso.sharepoint.com/sites/example"

  $m365Status = m365 status --output text
  Write-Host $m365Status
  if ($m365Status -eq "Logged Out") {
      # Connection to Microsoft 365
      m365 login
  }

  $controls = m365 spo page control list --webUrl $webUrl --pageName $pageName --output json | ConvertFrom-Json
  $sectionIdToRemove = -1
  $bannerWebpartId = "cbe7b0a9-3504-44dd-a3a3-0e5cacd07788"

  foreach ($control in $controls) {
      $controlPosition = $control.controlData.position

      # The header section should be the first section, full-width, not a vertical section, and should contain the banner web part.
      if ($controlPosition.zoneIndex -eq 1 -and $controlPosition.sectionFactor -eq 0 -and $controlPosition.layoutIndex -eq 1 -and $control.controlData.webPartId -eq $bannerWebpartId) {
          $sectionIdToRemove = $controlPosition.zoneIndex
          break
      }
  }

  if ($sectionIdToRemove -ne -1) {
      m365 spo page section remove --webUrl $webUrl --pageName $pageName --section $sectionIdToRemove --force
  }
  else {
      Write-Host "No header section to remove"
  }
  ```

  </TabItem>
</Tabs>
