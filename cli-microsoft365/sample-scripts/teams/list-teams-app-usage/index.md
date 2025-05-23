-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - apps
  - reports
  - teams
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# List app usage in Microsoft Teams

Inspired by: [Thomy Goelles](https://thomy.tech/list-teams-app-usage/)

A sample script which iterates through all the teams in your tenant and lists all apps in each team. This script will be handy if you want to generate a report of available apps in Teams across your tenant.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $availableTeams = m365 teams team list -o json | ConvertFrom-Json

  if ($availableTeams.count -gt 15) {
      $duration =  [math]::Round(($availableTeams.count/60),1);
      Write-Host "There are total of $($availableTeams.count) teams. This probably will take around $duration minutes to finish."
  } else {
      Write-Host "There are total of $($availableTeams.count) teams."
  }

  foreach ($team in $availableTeams) {
      $apps = m365 teams team app list -i $team.Id   
      Write-Output "All apps in team are given below: $($team.displayName) $($team.id)"
      Write-Output $apps
  }
  ```

  </TabItem>
  <TabItem value="Bash">

  ```bash
  #!/bin/bash

  # requires jq: https://stedolan.github.io/jq/
  defaultIFS=$IFS
  IFS=$'
'

  availableTeams=$(m365 teams team list -o json)

  if [[ $(echo $availableTeams | jq length) -gt 15 ]]; 
  then
    duration=$(((($(echo $availableTeams | jq length)) + 59) / 60))
    echo "There are total of" $(echo $availableTeams | jq length) "teams. This probably will take around" $duration" minutes to finish."
  else
    echo "There are total of" $(echo $availableTeams | jq length) "teams available"
  fi

  for team in $(echo $availableTeams | jq -c '.[]'); do
      apps=$(m365 teams team app list -i $(echo $team | jq ''.id) -a)
      echo "All apps in team are given below: " $(echo $team | jq ''.displayName) " " $(echo $team | jq ''.id)
      echo $apps
  done
  ```

  </TabItem>
</Tabs>
