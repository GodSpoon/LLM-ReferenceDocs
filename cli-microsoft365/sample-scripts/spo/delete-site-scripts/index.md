-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - cleanup    
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Delete custom SharePoint site scripts

Author: [Laura Kokkarinen](https://laurakokkarinen.com/EXAMPLE_SECRET_VALUE_PLACEHOLDER/#EXAMPLE_SECRET_VALUE_PLACEHOLDER)

Site designs and especially site scripts can be something that ends up just hanging around in your tenant for a long time even though you no longer need them for anything. Use the scripts below to get rid of them. You might also find some site scripts that are not linked to any site design and hence never get executed!

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $sparksjoy = "Project Site", "Issues List"
  $siteScripts = m365 spo sitescript list -o json | ConvertFrom-Json
  $siteScripts = $siteScripts | where {  -not ($sparksjoy -contains $_.Title)}
  if ($siteScripts.Count -eq 0) { break }
  $siteScripts | Format-Table Title, SiteScriptIds, Description
  Read-Host -Prompt "Press Enter to start deleting (CTRL + C to exit)"
  $progress = 0
  $total = $siteScripts.Count
  foreach ($siteScript in $siteScripts)
  {
    $progress++
    Write-Host $progress / $total":" $siteScript.Title
    m365 spo sitescript remove -i $siteScript.Id --force
  }
  ```

  </TabItem>
  <TabItem value="Bash">

  ```bash
  #!/bin/bash

  # requires jq: https://stedolan.github.io/jq/

  sparksjoy=("Project Site"  "Issues List")
  sitesscriptstoremove=()
  while read script; do
  scriptTitle=$(echo ${script} | jq -r '.Title')
    exists=true
    for keep in "${sparksjoy[@]}"; do
      if [ "$keep" == "$scriptTitle" ] ; then
        exists=false
        break
      fi
    done
    if [ "$exists" = true ]; then
      echo $scriptTitle
      sitesscriptstoremove+=("$script")
    fi

  done < <(m365 spo sitescript list -o json | jq -c '.[]')

  if [ ${#sitesscriptstoremove[@]} = 0 ]; then
    exit 1
  fi

  echo "Press Enter to start deleting (CTRL + C to exit)"
  read foo

  for script in "${sitesscriptstoremove[@]}"; do
    scriptTitle=$(echo ${script} | jq -r '.Title')
    scriptId=$(echo ${script} | jq -r '.Id')
    echo "Deleting Site script..."  $scriptTitle
    m365 spo sitescript remove --id $scriptId --force
  done
  ```

  </TabItem>
</Tabs>
