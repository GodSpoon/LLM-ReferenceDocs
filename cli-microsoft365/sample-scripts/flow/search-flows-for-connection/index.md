-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:  
  - flows
  - reports
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Search flows for connections

Author: [Albert-Jan Schot](https://www.cloudappie.nl/search-flows-connections/)

Search all flows as, an administrator, for a specific search string and report results. This sample allows you to get a report of all flows that are connected to a specific site or list. The `$searchString` can be any value but results are the best when using a GUID or site collection URL.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  Write-Output "Retrieving all environments"

  $environments = m365 flow environment list -o json | ConvertFrom-Json
  $searchString = "15f5b014-9508-4941-b564-b4ab1b863a7a" #listGuid
  $path = "exportedflow.json";

  ForEach ($env in $environments) {
      Write-Output "Processing $($env.displayName)..."

      $flows = m365 flow list --environmentName $env.name --asAdmin -o json | ConvertFrom-Json

      ForEach ($flow in $flows) {
          Write-Output "Processing $($flow.displayName)..."
          m365 flow export --name $flow.name --environmentName $env.name --format json --path $path

          $flowData = Get-Content -Path $path -ErrorAction SilentlyContinue

          if ($null -ne $flowData) {
              if ($flowData.Contains($searchString)) {
                  Write-Output $($flow.properties.displayName + "contains your search string" + $searchString)
                  Write-Output $flow.id
              }

              Remove-Item $path -Confirm:$false
          }
      }
  }
  ```

  </TabItem>
</Tabs>
