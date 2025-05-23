-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - cleanup
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Delete custom SharePoint site designs

Author: [Laura Kokkarinen](https://laurakokkarinen.com/EXAMPLE_SECRET_VALUE_PLACEHOLDER/#EXAMPLE_SECRET_VALUE_PLACEHOLDER)

Site designs and especially site scripts can be something that ends up just hanging around in your tenant for a long time even though you no longer need them for anything. Use the scripts below to get rid of them. You might also find some site scripts that are not linked to any site design and hence never get executed!

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $sparksjoy = "Cat Lovers United", "Multicolored theme"
  $sitedesigns = m365 spo sitedesign list -o json | ConvertFrom-Json
  $sitedesigns = $sitedesigns | where {-not ($sparksjoy -contains $_.Title)}
  $sitedesigns | Format-Table Title, SiteScriptIds, Description
  if ($sitedesigns.Count -eq 0) { break }
  Read-Host -Prompt "Press Enter to start deleting (CTRL + C to exit)"
  $progress = 0
  $total = $sitedesigns.Count
  foreach ($sitedesign in $sitedesigns)
  {
    $progress++
    write-host $progress / $total":" $sitedesign.Title
    m365 spo sitedesign remove --id "$($sitedesign.Id)" --force
  }
  ```

  </TabItem>
  <TabItem value="Bash">

  ```bash
  #!/bin/bash

  # requires jq: https://stedolan.github.io/jq/

  sparksjoy=("Cat Lovers United" "Multicolored theme")
  sitedesignstoremove=()
  while read sitedesign; do
    exists=false
    designinfo=(${sitedesign//;/ })
    for keep in "${sparksjoy[@]}"; do
      if [ "$keep" == "${designinfo[0]}" ] ; then
        exists=true
        break
      fi
    done
    if [ "$exists" = false ]; then
      sitedesignstoremove+=("$sitedesign")
    fi
  done < <(m365 spo sitedesign list -o json | jq -r '.[].Title + ";" + .[].Id')

  if [ ${#sitedesignstoremove[@]} = 0 ]; then
    exit 1
  fi

  printf '%s
' "${sitedesignstoremove[@]}"
  echo "Press Enter to start deleting (CTRL + C to exit)"
  read foo

  for sitedesign in "${sitedesignstoremove[@]}"; do
    designinfo=(${sitedesign//;/ })
    echo "Deleting ${designinfo[0]}..."
    m365 spo sitedesign remove --id "${designinfo[1]}" --force
  done
  ```

  </TabItem>
</Tabs>
