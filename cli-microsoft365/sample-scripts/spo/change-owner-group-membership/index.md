-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - groups
  - users
  - security
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Change group membership of all SharePoint Online sites

Author: [Arjun Menon](https://x.com/arjunumenon), Inspired by [Patrick Lamber](https://www.nubo.eu/EXAMPLE_SECRET_VALUE_PLACEHOLDER/)


This is a script which takes a subset or all members of the default owner group and downgrades the permission to the default member group.

*The below script filters all the `Communication Sites` from your tenant whose Title contains the keyword `Central`. Based on your use case / requirement, you can modify the script*


<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $siteFilterKeyword = "Central"

  #Getting the Communication Sites whose title contains the the given keyword
  $siteList = m365 spo site list --type CommunicationSite --output json --query "[? contains(Title,'$siteFilterKeyword')]" | ConvertFrom-Json
  $TotalSiteCount = $SiteList.Count
  Write-Host "Total number sites which has the keyword '$siteFilterKeyword' in their title are : $TotalSiteCount"
  $SiteCounter = 1

  Foreach ($site in $siteList) {
      Write-Host "Processing site No : $SiteCounter / $TotalSiteCount."
      Write-Host "Site URL - $($site.Url)"
      # Getting only Associated Owner and Member Groups using JMES Query
      $AssociatedGroups = m365 spo web get --url $site.Url --withGroups --query "{MemberGroup: AssociatedMemberGroup, OwnerGroup: AssociatedOwnerGroup}" --output json | ConvertFrom-Json

      # Getting list of members from the Owner Group
      $UserList = m365 spo group member list --webUrl $site.Url --groupId $AssociatedGroups.OwnerGroup.Id --output json | ConvertFrom-Json

      Write-Host "Total Users available in the Group, $($AssociatedGroups.OwnerGroup.Title) : "$UserList.Count
      Foreach ($User in $UserList){
          # Adding the user to Member Group
          m365 spo group member add --webUrl $site.Url --groupId $AssociatedGroups.MemberGroup.Id --userNames "$($User.UserPrincipalName)"
          
          # Removing the user from Owner Group
          m365 spo group member remove --webUrl $site.Url --groupId $AssociatedGroups.OwnerGroup.Id --userName "$($User.UserPrincipalName)" --force
      }
      $SiteCounter++
  }
  ```

  </TabItem>
</Tabs>
