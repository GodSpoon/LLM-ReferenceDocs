-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - reports
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# List all failed site design for all sites

Author: [Albert-Jan Schot](https://www.cloudappie.nl/failed-sitedesigns-clim365/)

The following script iterates through all site collections and lists all site design runs with errors. By filtering on `OutcomeCode == '1'` it will return all sites and runs with explicit errors. By filtering on `OutcomeCode != '0'` you can also return any result that is not marked as successful.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $allSPOSites = m365 spo site list | ConvertFrom-Json
  $siteCount = $allSPOSites.Count
  Write-Output "Processing $siteCount sites..."
  foreach ($site in $allSPOSites) {
      $siteCounter++
      Write-Output "Processing $($site.Url)... ($siteCounter/$siteCount)"
      $runs = m365 spo sitedesign run list --webUrl $site.Url --output json | ConvertFrom-Json
      foreach ($run in $runs) {
          $runData = m365 spo sitedesign run status get --webUrl $site.Url --runId $run.ID --query '[?OutcomeCode == `1`]' --output json | ConvertFrom-Json
          if ($runData) {
              Write-Output "$($run.SiteDesignTitle) failed at $($site.Url) with id $($run.ID)"
          }
      }
  }
  ```

  </TabItem>
</Tabs>
