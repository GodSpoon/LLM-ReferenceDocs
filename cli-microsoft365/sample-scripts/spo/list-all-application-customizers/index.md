-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - customizations
  - reports
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# List all application customizers in a tenant

Author: [Rabia Williams](https://x.com/williamsrabia)

List all the application customizers in a tenant. Scope is default `All`. Here we are using the [custom action list](https://pnp.github.io/cli-microsoft365/cmd/spo/customaction/customaction-list/) command to list out all the Application Customizers in all the sites in the tenant.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $sites = m365 spo search --queryText "contentclass:STS_site -SPSiteURL:personal" --selectProperties "Path,Title" --allResults --output json | ConvertFrom-Json
  foreach ($site in $sites) {                                                      
    write-host $site.Title                      
    write-host $site.Path                                             
    m365 spo customaction list --webUrl $site.Path   
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

  sites=$(m365 spo search --queryText "contentclass:STS_site -SPSiteURL:personal" --selectProperties "Path,Title" --allResults --output json)

  for site in $(echo $sites | jq -c '.[]'); do
    siteUrl=$(echo ${site} | jq -r '.Path')
    siteName=$(echo ${site} | jq -r '.Title')
    echo $siteUrl
    echo $siteName
    m365 spo customaction list --webUrl $siteUrl
  done
  ```

  </TabItem>
</Tabs>
