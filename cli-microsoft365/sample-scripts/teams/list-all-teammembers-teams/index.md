-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - users
  - reports
  - teams
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# List all team members in Microsoft Teams teams in the tenant

List all team members in Microsoft Teams teams in the tenant and exports the results in a CSV.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  function Get-TeamMembers(
      [Parameter(Mandatory = $false)][string] $teamID
  ) {
      if (!$teamID) {
          Write-Error "'Team ID' is required!"
          return
      }
      Write-Host "Retrieving the users.."
      $results = @()
      $users = m365 teams user list --teamId $teamID -o 'json' | ConvertFrom-Json
      if ($users.length -gt 0) {
          foreach ($user in $users) {
              $results += [pscustomobject][ordered]@{
                  ID             = $user.id
                  "Display Name" = $user.displayName
                  UPN            = $user.userPrincipalName
                  Role           = $user.userType
              }
          }
      }
      else {
          Write-Output "No team members!"
      }
      Write-Host "Exporting the results.."
      $results | Export-Csv -Path "TeamMembers.csv" -NoTypeInformation
      Write-Host "Completed."
  }

  Write-Host "Ensure logged in"
  $m365Status = m365 status --output text
  if ($m365Status -eq "Logged Out") {
      Write-Host "Logging in the User!"
      m365 login --authType browser
  }
  ```

  </TabItem>
</Tabs>
