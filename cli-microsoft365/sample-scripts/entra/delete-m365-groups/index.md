-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:  
  - cleanup
  - groups
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Delete all Microsoft 365 groups

Author: [Laura Kokkarinen](https://laurakokkarinen.com/EXAMPLE_SECRET_VALUE_PLACEHOLDER/#delete-all-office-365-groups)

There are so many different ways to create Microsoft 365 groups. Teams, Planner, SharePoint team sites, etc. — you can accumulate a lot of them very fast. Use this script below to delete the ones you no longer need.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $sparksjoy = "All Company", "TEMPLATE Project", "We have cats in this team! Join!"
  $groups = m365 entra m365group list -o json | ConvertFrom-Json
  $groups = $groups | where {-not ($sparksjoy -contains $_.displayName)}
  if ($groups.Count -eq 0) { break }
  $groups | Format-Table displayName
  Write-Host "Total:" $groups.Count
  Read-Host -Prompt "Press Enter to start deleting (CTRL + C to exit)"
  $progress = 0
  $total = $groups.Count
  foreach ($group in $groups)
  {
      $progress++
      Write-Host $progress / $total":" $group.displayName
      m365 entra m365group remove --id $group.id --force
  }
  ```

  </TabItem>
  <TabItem value="Bash">

  ```bash
  #!/bin/bash

  # requires jq: https://stedolan.github.io/jq/

  sparksjoy=("All Company" "TEMPLATE Project" "We have cats in this team! Join!")
  groupstoremove=()
  while read m365group; do
    exists=false
    displayName=$(echo $m365group | cut -d';' -f 1)
    for keep in "${sparksjoy[@]}"; do
      if [ "$keep" == "$displayName" ] ; then
        exists=true
        break
      fi
    done
    if [ "$exists" = false ]; then
      groupstoremove+=("$m365group")
    fi
  done < <(m365 entra m365group list -o json | jq -r '.[] | .displayName + ";" + .id')

  if [ ${#groupstoremove[@]} = 0 ]; then
    exit 1
  fi

  printf '%s
' "${groupstoremove[@]}"
  echo "Press Enter to start deleting (CTRL + C to exit)"
  read foo

  for m365group in "${groupstoremove[@]}"; do
    displayName=$(echo $m365group | cut -d';' -f 1)
    id=$(echo $m365group | cut -d';' -f 2)
    echo "Deleting $displayName..."
    m365 entra m365group remove --id $id --force
  done
  ```

  </TabItem>
</Tabs>
