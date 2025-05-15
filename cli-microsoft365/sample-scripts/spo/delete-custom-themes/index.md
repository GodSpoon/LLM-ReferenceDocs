-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - provisioning
  - cleanup
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Delete custom color themes from SharePoint

Author: [Laura Kokkarinen](https://laurakokkarinen.com/EXAMPLE_SECRET_VALUE_PLACEHOLDER/#EXAMPLE_SECRET_VALUE_PLACEHOLDER)

Have you been creating a lot of beautiful themes lately and testing them in your dev tenant, but don’t want to keep them anymore? If yes, then this PowerShell script is for you.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $sparksjoy = "Cat Lovers United", "Multicolored theme"
  $themes = m365 spo theme list -o json | ConvertFrom-Json
  $themes = $themes | where {-not ($sparksjoy -contains $_.name)}
  $themes | Format-Table name
  if ($themes.Count -eq 0) { break }
  Read-Host -Prompt "Press Enter to start deleting (CTRL + C to exit)"
  $progress = 0
  $total = $themes.Count
  foreach ($theme in $themes)
  {
    $progress++
    write-host $progress / $total":" $theme.name
    m365 spo theme remove --name "$($theme.name)" --force
  }
  ```

  </TabItem>
  <TabItem value="Bash">

  ```bash
  #!/bin/bash

  # requires jq: https://stedolan.github.io/jq/

  sparksjoy=("Cat Lovers United" "Multicolored theme")
  themestoremove=()
  while read theme; do
    exists=false
    for keep in "${sparksjoy[@]}"; do
      if [ "$keep" == "$theme" ] ; then
        exists=true
        break
      fi
    done
    if [ "$exists" = false ]; then
      themestoremove+=("$theme")
    fi
  done < <(m365 spo theme list -o json | jq -r '.[].name')

  if [ ${#themestoremove[@]} = 0 ]; then
    exit 1
  fi

  printf '%s
' "${themestoremove[@]}"
  echo "Press Enter to start deleting (CTRL + C to exit)"
  read foo

  for theme in "${themestoremove[@]}"; do
    echo "Deleting $theme..."
    m365 spo theme remove --name "$theme" --force
  done
  ```

  </TabItem>
</Tabs>
