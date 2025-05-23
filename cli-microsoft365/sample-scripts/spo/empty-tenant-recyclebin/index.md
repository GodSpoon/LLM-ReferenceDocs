-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - cleanup
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Empty the tenant recycle bin

Author: [Laura Kokkarinen](https://laurakokkarinen.com/EXAMPLE_SECRET_VALUE_PLACEHOLDER/#empty-the-tenant-recycle-bin)

Your deleted modern SharePoint sites are not going to disappear from the UI before they have been removed from the tenant recycle bin. You can either wait for three months, delete them manually via the SharePoint admin center, or run the CLI for Microsoft 365 script below.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $deletedSites = m365 spo tenant recyclebinitem list -o json | ConvertFrom-Json
  $deletedSites | Format-Table Url

  if ($deletedSites.Count -eq 0) { break }

  Read-Host -Prompt "Press Enter to start deleting (CTRL + C to exit)"

  $progress = 0
  $total = $deletedSites.Count

  foreach ($deletedSite in $deletedSites)
  {
    $progress++
    Write-Host $progress / $total":" $deletedSite.Url
    m365 spo tenant recyclebinitem remove -u $deletedSite.Url --force
  }
  ```

  </TabItem>
  <TabItem value="Bash">

  ```bash
  #!/bin/bash

  # requires jq: https://stedolan.github.io/jq/

  deletedsites=( $(m365 spo tenant recyclebinitem list -o json | jq -r '.[].Url') )

  if [ ${#deletedsites[@]} = 0 ]; then
    exit 1
  fi

  printf '%s
' "${deletedsites[@]}"
  echo "Press Enter to start deleting (CTRL + C to exit)"
  read foo

  progress=0
  total=${#deletedsites[@]}

  for deletedsite in "${deletedsites[@]}"; do
    ((progress++))
    printf '%s / %s:%s
' "$progress" "$total" "$deletedsite"
    m365 spo tenant recyclebinitem remove -u $deletedsite --force
  done
  ```

  </TabItem>
</Tabs>
