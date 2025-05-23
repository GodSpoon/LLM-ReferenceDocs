-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - listitems
  - security
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# List all items with unique permissions

Author: [Veronique Lengelle](https://x.com/veronicageek), Inspired by [Salaudeen Rajack](https://www.sharepointdiary.com/2017/03/EXAMPLE_SECRET_VALUE_PLACEHOLDER)

## List all items for a specific SharePoint list on a site

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  #Declare variables
  $siteURL = "https://<TENANT-NAME>.sharepoint.com/sites/<YOUR-SITE>"
  $listName = "<YOUR-LIST-NAME>"
  $allItems = m365 spo listitem list --webUrl $siteUrl --listTitle $listName --fields "ID,HasUniqueRoleAssignments,Title" | ConvertFrom-Json
  $results = @()

  #Loop through each item in the list
  foreach($item in $allItems){
      $results += [pscustomobject][ordered]@{
          ListName = $listName
          ItemID = $item.Id
          ItemTitle = $item.Title
          UniquePermissions = $item.HasUniqueRoleAssignments
      }
  }
  $results
  ```

  </TabItem>
</Tabs>

## List all items for multiple SharePoint lists on a site

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  #Declare variables
  $siteURL = "https://<TENANT-NAME>.sharepoint.com/sites/<YOUR-SITE>"
  $allLists = m365 spo list list --webUrl $siteUrl --query "[?BaseTemplate == ``100``]" | ConvertFrom-Json
  $results = @()

  foreach($list in $allLists){
      if ($list.Hidden -eq $false){ 
          
          $allItems = m365 spo listitem list --webUrl $siteURL --listId $list.Id --fields "ID,HasUniqueRoleAssignments,Title" | ConvertFrom-Json
          
          foreach($item in $allItems){
              $results += [pscustomobject][ordered]@{
                  ListName = $list.Title
                  ItemID = $item.Id
                  ItemTitle = $item.Title
                  UniquePermissions = $item.HasUniqueRoleAssignments
              }
          }
      }
  }
  $results
  ```

  </TabItem>
</Tabs>
