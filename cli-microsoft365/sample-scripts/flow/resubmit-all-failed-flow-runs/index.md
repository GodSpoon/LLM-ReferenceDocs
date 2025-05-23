-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:  
  - flows
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Resubmit all failed flow runs for a flow in an environment

Author: [Mohamed Ashiq Faleel](https://ashiqf.com/2021/05/09/EXAMPLE_SECRET_VALUE_PLACEHOLDER/)

Have you ever been forced to resubmit lot of failed Power Automate flow runs manually?

Microsoft 365 CLI cmdlets to the rescue, it will help you resubmit the flow runs automatically.

This script will resubmit all failed flow runs of a Power Automate flow created in an environment. Pass the Flow environment id and the flow guid as parameter while running the script.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $flowEnvironment = $args[0]
  $flowGUID = $args[1]
  $flowRuns = m365 flow run list --environmentName $flowEnvironment --flowName $flowGUID --status Failed --output json | ConvertFrom-Json
  foreach ($run in $flowRuns) {
    Write-Output "Run details: " $run
    #Resubmit all the failed flows
    m365 flow run resubmit --environmentName $flowEnvironment --flowName $flowGUID --name $run.name --force
    Write-Output "Run resubmitted successfully"
  }
  ```

  </TabItem>
</Tabs>
