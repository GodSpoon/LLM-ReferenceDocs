-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - reports
  - teams
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# List Microsoft Teams teams, channels, and tabs in the tenant

Inspired by: [Veronique Lengelle](https://veronicageek.com/powershell/powershell-for-m365/EXAMPLE_SECRET_VALUE_PLACEHOLDER/2020/07/)

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  <#
  .SYNOPSIS
    List Microsoft Teams teams information.
  .DESCRIPTION
    This script will list some information about each Teams, channels, and tabs within the tenant. Does not include private channels.
  .EXAMPLE
    PS C:\> Get-TeamsInfoForTenant.ps1
    This script will list some information about each Teams, channels, and tabs within the tenant
  .INPUTS
    Inputs (if any)
  .OUTPUTS
    Output (if any)
  .NOTES
    Does not include private channels.
  #>

  #Declare variables
  $exportFile = "<YOUR_PATH>"
  $allTeams = m365 teams team list -o json | ConvertFrom-Json
  $results = @()

  foreach($team in $allTeams){
      $allChannels = m365 teams channel list --teamId $team.Id -o json | ConvertFrom-Json

      foreach($channel in $allChannels){
          $allTabs = m365 teams tab list --teamId $team.Id --channelId $channel.Id -o json | ConvertFrom-Json

          # Get the Teams information
          foreach($tab in $allTabs){
              $results += [pscustomobject][ordered]@{
                  TeamID = $team.Id
                  Team = $team.DisplayName
                  ArchiveStatus = $team.isArchived
                  ChannelName = $channel.DisplayName
                  TabName = $tab.DisplayName
              }
          }
      }

  }
  $results | Export-Csv -Path $exportFile -NoTypeInformation
  ```

  </TabItem>
</Tabs>
