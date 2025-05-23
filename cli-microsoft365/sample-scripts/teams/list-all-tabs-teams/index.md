-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - reports
  - teams
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# List all tabs in Microsoft Teams teams in the tenant

Inspired by: [Patrick Lamber](https://www.nubo.eu/EXAMPLE_SECRET_VALUE_PLACEHOLDER/) and [Veronique Lengelle](https://veronicageek.com/powershell/powershell-for-m365/EXAMPLE_SECRET_VALUE_PLACEHOLDER/2020/07/)

List all tabs in Microsoft Teams teams in the tenant and exports the results in a CSV.

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
  $allTeams = m365 teams team list -o json | ConvertFrom-Json
  $teamCount = $allTeams.Count
  Write-Host "Processing $teamCount teams..."
  #Loop through each Team
  $counter = 0
  foreach ($team in $allTeams) {
    $counter++
    Write-Host "Processing $($team.displayName)... ($counter/$teamCount)"
    $allChannels = m365 teams channel list --teamId $team.id -o json | ConvertFrom-Json
      
    #Loop through each Channel
    foreach ($channel in $allChannels) {
      $allTabs = m365 teams tab list --teamId $team.id --channelId $channel.id -o json | ConvertFrom-Json
          
      #Loop through each Tab + get the info!
      foreach ($tab in $allTabs) {
        $results += [pscustomobject][ordered]@{
          TeamId                = $team.id
          TeamDisplayName       = $team.displayName
          TeamIsArchived        = $team.isArchived
          TeamVisibility        = $team.visibility
          ChannelId             = $channel.id
          ChannelDisplayName    = $channel.DisplayName
          ChannelMemberShipType = $channel.membershipType
          TabId                 = $tab.id
          TabNameDisplayName    = $tab.DisplayName
          TeamsAppTabId         = $tab.teamsApp.id
        }
      }
    }
  }
  Write-Host "Exporting file to $fileExportPath.."
  $results | Export-Csv -Path $fileExportPath -NoTypeInformation
  Write-Host "Completed."
  ```

  </TabItem>
</Tabs>
