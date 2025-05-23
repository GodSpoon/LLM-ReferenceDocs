-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:  
  - cleanup
  - groups
  - security
  - teams
  - users
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Replace a user's membership in selected Microsoft 365 Groups or Teams

Inspired by: [Alan Eardley](https://blog.eardley.org.uk/2021/04/managing-teams-movers-and-leavers/), [Patrick Lamber](https://www.nubo.eu/EXAMPLE_SECRET_VALUE_PLACEHOLDER/)

This script can be used to replace the membership of a user for a selected list of Groups. It might be useful when a person changes role in an organization or is about to leave it.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $fileInput = "<PUTYOURPATHHERE.csv>"
  $oldUser = "upnOfOldUser"
  $newUser = "upnOfNewUser"
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

  function Replace-Membership {
    [cmdletbinding()]
    param(
      [parameter(Mandatory = $true)]
      $fileInput ,
      [parameter(Mandatory = $true)]
      $oldUser,
      [parameter(Mandatory = $true)]
      $newUser
    )
    $groupsToProcess = Import-Csv $fileInput 
    $groupsToProcess.id | ForEach-Object {
      $groupId = $_
      Write-Host "Processing Group ($groupId)" -ForegroundColor DarkGray -NoNewline

      $group = $null
      try {
        $group = m365 entra m365group get --id $groupId | Get-CLIValue 
      }
      catch {
        Write-Host
        Write-Host $_.Exception.Message -ForegroundColor Red
        return
      }
      Write-Host " - $($group.displayName)" -ForegroundColor DarkGray

      $isTeam = $EXAMPLE_SECRET_VALUE_PLACEHOLDER("Team");

      $users = $null
      $users = m365 entra m365group user list --groupId $groupId | Get-CLIValue
      $users | Where-Object { $_.userPrincipalName -eq $oldUser } | ForEach-Object {
        $user = $_
        $isMember = $user.userType -eq "Member"
        $isOwner = $user.userType -eq "Owner"

        Write-Host "Found $oldUser with $($user.userType.tolower()) rights" -ForegroundColor Green

        # owners must be explicitly added as members if it is a team
        if ($isMember -or $isTeam) {
          try {
            Write-Host "Granting $newUser member rights"
            m365 entra m365group user add --groupId $groupId --userNames $newUser | Get-CLIValue
          }
          catch {
            Write-Host $_.Exception.Message -ForegroundColor White
          }
        }

        if ($isOwner) {
          try {
            Write-Host "Granting $newUser owner rights"
            m365 entra m365group user add --groupId $groupId --userNames $newUser --role Owner | Get-CLIValue
          }
          catch {
            Write-Host $_.Exception.Message -ForegroundColor White
          }
        }

        try {
          Write-Host "Removing $oldUser..."
          m365 entra m365group user remove --groupId $groupId --userNames $oldUser | Get-CLIValue
        }
        catch {
          Write-Host $_.Exception.Message -ForegroundColor Red
          continue
        }
      }
    }
  }

  Replace-Membership $fileInput $oldUser $newUser
  ```

  </TabItem>
  <TabItem value="Input CSV File Format">

  ```csv
  id
  <groupId>
  <groupId>
  <groupId>
  ```

  </TabItem>
</Tabs>
