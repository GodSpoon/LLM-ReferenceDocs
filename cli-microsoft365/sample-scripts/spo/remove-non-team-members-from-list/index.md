-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - list
  - cleanup
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Remove users from a SharePoint list who are no longer members of a Teams Team

Author: [Saurabh Tripathi](https://github.com/saurabh7019)

This script compares a list of members of a team with a list of people in a SharePoint list and removes anyone who is no longer a team member.

Prerequisites:

- A SharePoint list with the below column:

Column Internal Name | Type  | Required 
---------------------|-------|----------
Email                | Text  | Yes      

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  Write-host 'Remove users from a SharePoint list who are no longer members of a Teams Team'

  function Remove-NonTeamMembersFromList {
      param (
          [Parameter(Mandatory = $true, HelpMessage = "Specify the display name of the Microsoft Teams team for which you want to remove members.")]
          [ValidateNotNullOrEmpty()]
          [string]$teamName,

          [Parameter(Mandatory = $true, HelpMessage = "Specify the title of the SharePoint list you want to clean up.")]
          [ValidateNotNullOrEmpty()]
          [string]$listName,

          [Parameter(Mandatory = $true, HelpMessage = "Specify the URL of the site where the SharePoint list is located.")]
          [ValidateNotNullOrEmpty()]
          [string]$siteUrl
      )

      try {
          Write-Host ("Getting members of the '{0}' team..." -f $teamName) -ForegroundColor Yellow
          $team = m365 teams team get --name $teamName --output json | ConvertFrom-Json
          if ($team) {
              $teamMembers = m365 teams user list --teamId $team.id --output json | ConvertFrom-Json
          }

          Write-Host ("Getting members of the '{0}' list from the site '{1}'..." -f $listName, $siteUrl) -ForegroundColor Yellow
          $listMembers = m365 spo listitem list --listTitle $listName --webUrl $siteUrl --fields "ID,Email" --output json | ConvertFrom-Json

          $membersRemoved = $false
          foreach ($listMember in $listMembers) {
              $match = $teamMembers | Where-Object { $_.userPrincipalName -eq $listMember.Email }
              if ($null -eq $match ) {
                  Write-Host ("Removing '{0}' from the '{1}' list..." -f $($listMember.Email), $listName) -ForegroundColor Yellow
                  $membersRemoved = $true
                  m365 spo listitem remove --webUrl $siteUrl --listTitle $listName --id $listMember.Id --force
              }
          }

          if (!$membersRemoved) {
              Write-Host ("`tNo members to remove from the '{0}' list." -f $listName) -ForegroundColor Green
          }
          else {
              Write-Host ("`tMembers removed successfully from the '{0}' list." -f $listName) -ForegroundColor Green
          }
      }
      catch {
          Write-Host $_.Exception -ForegroundColor DarkRed
      }
  }

  $teamName = 'Sales'
  $listName = 'Contacts'
  $siteUrl = 'https://contoso.sharepoint.com'
  Remove-NonTeamMembersFromList -teamName $teamName -listName $listName -siteUrl $siteUrl
  ```

  </TabItem>
</Tabs>
