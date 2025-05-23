-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:  
  - flows
  - migration
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Export all flows in environment

Author: [Garry Trinder](https://garrytrinder.github.io/2021/01/EXAMPLE_SECRET_VALUE_PLACEHOLDER)

When was the last time you backed up all the flows in your environment?

By combining the CLI for Microsoft 365 and PowerShell we can make this task easy and repeatable.

This script will get all flows in your default environment and export them as both a ZIP file for importing back into Power Automate and as a JSON file for importing into Azure as an Azure Logic App.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  Write-Output "Getting environment info..."
  $environment = m365 flow environment list --query '[?properties.isDefault==`true`].name' --output json | ConvertFrom-JSON

  Write-Output "Getting Flows info..."
  $flows = m365 flow list --environmentName $environment --asAdmin --output json | ConvertFrom-JSON

  Write-Output "Found $($flows.Count) Flows to export..."

  $flows | ForEach-Object {
      Write-Output "Exporting as ZIP & JSON... $($_.displayName)"
      $filename = $_.properties.displayName.Replace(" ","")
      $timestamp = Get-Date -Format "yyyymmddhhmmss"
      $exportPath = "$($filename)_$($timestamp)"
      $flowId = $_.name
      
      m365 flow export --name $flowId --environmentName $environment --packageDisplayName $_.properties.displayName --path "$exportPath.zip"
      m365 flow export --name $flowId --environmentName $environment --format json --path "$exportPath.json"
  }

  Write-Output "Complete"
  ```

  </TabItem>
</Tabs>
