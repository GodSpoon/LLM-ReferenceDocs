-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:  
  - apps
  - flows
  - reports
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# List all Power Platform Environments and their Flows and Apps

Author: [Albert-Jan Schot](https://www.cloudappie.nl/EXAMPLE_SECRET_VALUE_PLACEHOLDER/)

This script will retrieve all environments as an Administrator and loop through all Flows and Apps to provide you with a report indicating how much Power Platform components are in use in the tenant.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $m365Status = m365 status

  if ($m365Status -eq "Logged Out") {
      # Connection to Microsoft 365
      m365 login
  }

  $environments = m365 pp environment list --asAdmin | ConvertFrom-Json

  Write-Host -f Green "Processing $($environments.Count) environments";

  $results = @()

  $environments | ForEach-Object {
    Write-Host -f Green "Processing environment: $($_.displayName)"
    $envId = $($_.name)

    $results += [pscustomobject]@{
      type        = "environment"
      id          = $envId
      displayName = $_.displayName
      envId       = $envId
      lifeCycleId = $_.properties.environmentSku
      status      = $_.properties.isDefault ? "Default" : "NotDefault"
      createdByUpn = $EXAMPLE_SECRET_VALUE_PLACEHOLDER ? $EXAMPLE_SECRET_VALUE_PLACEHOLDER : ""
    }

    $apps = m365 pa app list --environmentName $envId --asAdmin | ConvertFrom-Json
    Write-Host -f Green "Processing: $($apps.Count) apps"

    $apps | ForEach-Object {

      $results += [pscustomobject]@{
        type              = $_.appType
        id                = $_.name
        displayName       = $_.displayName
        envId             = $envId
        lifeCycleId       = $_.properties.lifeCycleId
        status            = $_.properties.status
        createdByUpn      = $EXAMPLE_SECRET_VALUE_PLACEHOLDER
      }
    }

    $flows = m365 flow list --environmentName $envId --asAdmin | ConvertFrom-Json
    Write-Host -f Green "Processing: $($flows.Count) flows"

    $flows | ForEach-Object {
      $createUser = m365 entra user get --id $_.properties.creator.userId | ConvertFrom-Json

      $results += [pscustomobject]@{
        type          = "flow"
        id            = $_.name
        displayName   = $_.properties.displayName
        envId         = $envId
        lifeCycleId   = $_.properties.lifeCycleId
        status        = $_.properties.state
        createdByUpn  = $createUser.userPrincipalName
      }
    }
  }

  $results | Export-Csv -Path .