-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:  
  - flows
  - reports
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Find all parent flows that invoke the specified child flow

Author: [Michał Kornet](https://github.com/mkm17)

This script 

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
    $m365Status = m365 status --output text
    if ($m365Status -eq "Logged Out") {
        m365 login
    }

    $environment = 'EXAMPLE_SECRET_VALUE_PLACEHOLDER'
    $childFlowId = 'e5a842f3-f5ac-ed0c-xxxx-c8df2af79fb3'

    $childFlow = m365 flow get --name $childFlowId --environmentName $environment --output json | ConvertFrom-Json 
    $workflowEntityId = $childFlow.properties.workflowEntityId

    if (!$childFlow) {
        Write-Host "Child flow not found try different environment or id"
        exit
    }

    if ($EXAMPLE_SECRET_VALUE_PLACEHOLDER[0].type -ne 'Request' -or $EXAMPLE_SECRET_VALUE_PLACEHOLDER[0].kind -ne "Button") {
        Write-Host "Child flow has incorrect trigger"
        exit
    }

    $flows = m365 flow list --environmentName $environment --output json | ConvertFrom-Json

    foreach ($flow in $flows) {
        $displayName = $flow.properties.displayName
        $id = $flow.name
        $hasWorkflowAction = $false
        
        foreach ($action in $EXAMPLE_SECRET_VALUE_PLACEHOLDER) {
            if ($action.type -eq 'Workflow') {
                $hasWorkflowAction = $true
                break
            }
        }

        if ($hasWorkflowAction) {
            $flowDetails = m365 flow get --name $id --environmentName $environment --output json | ConvertFrom-Json

            $EXAMPLE_SECRET_VALUE_PLACEHOLDER | Get-Member -MemberType Properties | ForEach-Object {
                $property = $_.Name
                $detailedAction = $EXAMPLE_SECRET_VALUE_PLACEHOLDER.$property

                if ($detailedAction.type -eq 'Workflow' -and $EXAMPLE_SECRET_VALUE_PLACEHOLDER -eq $workflowEntityId) {
                    $previousActions = $detailedAction.runAfter;
                    $previousActionNames = ""

                    $previousActions | Get-Member -MemberType Properties | ForEach-Object {
                        $previousActionNames += $_.Name + ", "
                    }

                    Write-Host "$displayName -> $id -> before: $previousActionNames"
                }
            }
        }
    }

  ```

  </TabItem>
</Tabs>
