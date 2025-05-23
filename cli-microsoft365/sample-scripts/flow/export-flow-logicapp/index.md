-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:  
  - azure
  - flows
  - migration
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Export a single flow to a Logic App

Author: [Albert-Jan Schot](https://www.cloudappie.nl/cli-m365-exportflow/)

Want to upgrade one of your Power Automate flows to a Logic App? Missing the option in the UI? Or just looking at an easy way to do it programmatically?

By combining the CLI for Microsoft 365 and PowerShell we can make this task easy and repeatable.

This script will export the Power Automate flow *Your sample test flow*, make sure to pass the correct name in the script, and your flow will be exported right away.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  Write-Output "Getting environment info..."
  $environmentId = $(m365 flow environment get -o json | ConvertFrom-Json).name
  $flowId = $(m365 flow list --environmentName $environmentId --query "[?displayName == 'Your sample test flow']" -o json | ConvertFrom-Json)[0].name

  Write-Output "Getting Flow info..."
  m365 flow export --environmentName $environmentId --name $flowId --format 'json'

  Write-Output "Complete"
  ```

  </TabItem>
  <TabItem value="Bash">

  ```bash
  #!/bin/bash
  ENV_NAME=m365 flow environment get --output 'json' --query 'name'
  FLOW_NAME=m365 flow list --environmentName $environmentId --query '[?displayName == `Your sample test flow`] .name'
  echo "Exporting your flow"
  m365 flow export --environmentName $ENV_NAME --name $FLOW_NAME -f 'json'
  ```

  </TabItem>
</Tabs>
