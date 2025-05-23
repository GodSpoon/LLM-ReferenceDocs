-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - files  
  - lists
  - reports
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# List Attachment Names From SharePoint Lists For A Site

Author: [Veronique Lengelle](https://x.com/veronicageek)

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $siteUrl = "https://<TENANT-NAME>.sharepoint.com/sites/<YOUR-SITE>"
  $allLists = m365 spo list list --webUrl $siteUrl --query "[?BaseTemplate == ``100``]" | ConvertFrom-Json
  $results = @()

  foreach($list in $allLists){
      if ($list.Hidden -eq $false){ 
          $allItems = m365 spo listitem list --listId $list.Id --webUrl $siteUrl | ConvertFrom-Json
          
          foreach($item in $allItems){
              $allAttachments = m365 spo listitem attachment list --webUrl $siteUrl --listTitle $list.Title --listItemId $item.Id | ConvertFrom-Json
              
              foreach($attachment in $allAttachments){
                  $results += [pscustomobject][ordered]@{
                      itemID = $item.Id
                      itemTitle = $item.Title
                      fileName = $attachment.FileName
                      attachmentPath = $attachment.ServerRelativeUrl
                  }
              }
          }
      }
  }
  $results
  ```

  </TabItem>
</Tabs>
