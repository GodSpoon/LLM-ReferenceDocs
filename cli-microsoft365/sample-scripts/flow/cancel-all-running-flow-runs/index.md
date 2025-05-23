-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:  
  - cleanup
  - flows
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Cancel all running flow runs for a flow in an environment

Author: [Mohamed Ashiq Faleel](https://ashiqf.com/2021/05/16/EXAMPLE_SECRET_VALUE_PLACEHOLDER/)

Do you want to automate the cancellation of running Power Automate flow runs?

Microsoft 365 CLI cmdlets will help you to cancel all the running flow runs.

This script will cancel all running flow runs of a Power Automate flow created in an environment. Pass the Flow environment id and the flow guid as parameter while running the script.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $flowEnvironment = $args[0]
  $flowGUID = $args[1]
  $flowRuns = m365 flow run list --environmentName $flowEnvironment --flowName $flowGUID --status Running --output json | ConvertFrom-Json
  foreach ($run in $flowRuns) {
    Write-Output "Run details: " $run
    # Cancel all the running flow runs
    m365 flow run cancel --environmentName $flowEnvironment --flowName $flowGUID --name $run.name --force
    Write-Output "Run Cancelled successfully"
  }
  ```

  </TabItem>
</Tabs>
