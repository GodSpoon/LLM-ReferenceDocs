-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - teams
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# List all Microsoft Teams team's Owners and Members

Author: [Patrick Lamber](https://www.nubo.eu/EXAMPLE_SECRET_VALUE_PLACEHOLDER/)

This script allows you to list all Teams team's owners and members and export them into a CSV file. This script is inspired by [Robin Clarke](https://dailysysadmin.com/KB/Article/3607/EXAMPLE_SECRET_VALUE_PLACEHOLDER/).

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $fileExportPath = "<PUTYOURPATHHERE.csv>"
  # process teams that you have joined only
  $joined = $false

  $m365Status = m365 status --output text

  if ($m365Status -eq "Logged Out") {
    # Connection to Microsoft 365
    m365 login
  }

  # configure the CLI to output JSON on each execution
  m365 cli config set --key output --value json

  $exportData = @()
  $teams = m365 teams team list --joined $joined | ConvertFrom-Json
  # you can use the next line if you already know the GroupId/TeamId
  #$teams = @(m365 teams team get --id $teamId | ConvertFrom-Json)

  $i = 0
  $teams | ForEach-Object {
    $team = $_
    $i++
    Write-Host "Processing Team '$($team.displayName)' - ($i/$($teams.length))"
    $owners = $null
    $owners = m365 teams user list --teamId $team.id --role Owner --query "[].userPrincipalName" | ConvertFrom-Json
    $members = $null
    $members = m365 teams user list --teamId $team.id --role Member --query "[].userPrincipalName" | ConvertFrom-Json
    $exportData += [PSCustomObject]@{ Id = $team.id; DisplayName = $team.displayName; Owners = $owners -join ', '; Members = $members -join ', '}
  }

  Write-Host "Exporting file to $fileExportPath..."
  $exportData | Export-Csv -Path $fileExportPath -NoTypeInformation
  Write-Host "Completed."
  ```

  </TabItem>
</Tabs>
