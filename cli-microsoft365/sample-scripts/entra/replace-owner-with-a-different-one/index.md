-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:  
  - users
  - groups
  - security
  - teams
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Replace an owner in a Microsoft 365 Group or Microsoft Team

Inspired by: [Alan Eardley](https://blog.eardley.org.uk/2021/04/managing-teams-movers-and-leavers/), [Patrick Lamber](https://www.nubo.eu/EXAMPLE_SECRET_VALUE_PLACEHOLDER/)

Find all the Microsoft 365 Groups that a user is an Owner of and replace them with someone else useful for when an employee leaves and ownership needs to be updated.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  # This script replaces an owner with a different person in all Microsoft 365 Groups
  $oldUser = "oldUserUpn"
  $newUser = "newUserUpn"
  # Parameters end

  $m365Status = m365 status --output text

  if ($m365Status -eq "Logged Out") {
    # Connection to Microsoft 365
    m365 login
  }

  # configure the CLI to output JSON on each execution
  m365 cli config set --key output --value json
  m365 cli config set --key errorOutput --value stdout
  m365 cli config set --key showHelpOnFailure --value false
  m365 cli config set --key printErrorsAsPlainText --value false

  function Get-CLIValue {
    [cmdletbinding()]
    param(
      [parameter(Mandatory = $true, ValueFromPipeline = $true)]
      $input
    )
      $output = $input | ConvertFrom-Json
      if ($output.error -ne $null) {
        throw $output.error
      }
      return $output
  }

  function Replace-Owner {
      [cmdletbinding()]
      param(
          [parameter(Mandatory = $true)]
          $oldUser,
          [parameter(Mandatory = $true)]
          $newUser
      )
      $groupsToProcess = m365 entra m365group list | Get-CLIValue  
      $i = 0
      $groupsToProcess | ForEach-Object {
          $group = $_
          $i++
          Write-Host "Processing Group ($($group.id)) - $($group.displayName) - ($i/$($groupsToProcess.Length))" -ForegroundColor DarkGray
  
          $hasOwner = $null
          # verify if the old user is in the owners list
          $hasOwner = m365 entra m365group user list --groupId $group.id --role owner --query "[?userPrincipalName=='$oldUser'].[id]" | Get-CLIValue
          if ($hasOwner -ne $null) {
              Write-Host "Found $oldUser" -ForegroundColor Green
              try {
                  Write-Host "Granting $newUser owner rights"
                  m365 entra m365group user add --groupId $group.id --userNames $newUser --role Owner | Get-CLIValue
              }
              catch  {
                  Write-Host $_.Exception.Message -ForegroundColor White
              }

              try {
                  Write-Host "Removing $oldUser permissions..."
                  m365 entra m365group user remove --groupId $group.id --userNames $oldUser | Get-CLIValue
              }
              catch  {
                  Write-Host $_.Exception.Message -ForegroundColor Red
                  continue
              }
          }
      }
  }

  Replace-Owner $oldUser $newUser
  ```

  </TabItem>
</Tabs>
