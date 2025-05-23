-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - provisioning
  - teams
  - users
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Create a Microsoft Teams team and bulk add members from CSV file

Inspired by: [Rakesh Pandey](https://www.flexmind.co/blog/EXAMPLE_SECRET_VALUE_PLACEHOLDER/), [Patrick Lamber](https://www.nubo.eu/EXAMPLE_SECRET_VALUE_PLACEHOLDER/)

This sample script shows you how to create a Team and add members and owners using a CSV.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  # This script provisions a Group with owners and members and Teamifies it
  # The owners and members can be specified using a CSV file following this format
  ## upn,type
  ## pla@expertsinside.com,owner
  ## eba@expertsinside.com,member
  ## szu@expertsinside.com,member
  # The CLI will provision the Group adding the current user as owner. You can remove this user from the owners list by using the $removeYourSelfFromOwners parameter

  $importFile = "<putyourcsvhere.csv>"

  ## parameters for the Group
  $teamDisplayName = "Cool team"
  $teamDescription = "."
  $mailNickname = "uniqueNickname18"
  $visibility = "Private" # Specify either 'Private', 'Public', or 'HiddenMembership'  
  $removeYourSelfFromOwners = $false
  ## parameters for the Group end

  ## Script starts here

  # process teams that you have joined only
  $membersList = Import-Csv $importFile -Delimiter ","

  $m365Status = m365 status --output text

  if ($m365Status -eq "Logged Out") {
    # Connection to Microsoft 365
    m365 login
  }

  $Error.Clear()

  # configure the CLI to output JSON on each execution
  m365 cli config set --key output --value json

  $members = ($membersList | where { $_.type -eq "member" } | Select-Object upn).upn -join ","
  $owners = ($membersList | where { $_.type -eq "owner" } | Select-Object upn).upn -join ","

  Write-Host "Provisioning Group..."
  $group = m365 entra m365group add --displayName $teamDisplayName --description $teamDescription --mailNickname $mailNickname --visibility $visibility --members $members --owners $owners | ConvertFrom-Json

  if ($Error.Count -gt 0) {
      Write-Host "Aborting operation..."
      return
  }

  $trial = 0
  $maxRetry = 3
  $waitingTime = 20
  do {
      $Error.Clear()
      $trial++
      Write-Host "Waiting $waitingTime seconds before teamifying the group (trial $trial/$maxRetry)..."
      Start-Sleep -Seconds $waitingTime
      m365 entra m365group teamify --id $($group.id) 2>$null
  } while ($Error.Count -gt 0 -and $trial -lt $maxRetry)

  # if it still failed, output the error and stop
  if ($Error.Count -gt 0) {
    $Error
    return
  }
  $Error.Clear()

  $whoAmI = m365 status | ConvertFrom-Json
  # remove yourself from the owners group
  if ($removeYourSelfFromOwners -and $owners.IndexOf($whoAmI.connectedAs) -eq -1) {
      Write-Host "Removing $($whoAmI.connectedAs) from the owners list"
      m365 entra m365group user remove --groupId $group.id --userNames $whoAmI.connectedAs --force
  }

  Write-Host "Completed."
  ```

  </TabItem>
</Tabs>
