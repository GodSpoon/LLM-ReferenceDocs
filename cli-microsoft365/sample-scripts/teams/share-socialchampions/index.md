-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - adoption
  - users
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Share social champions to Teams

Author: [Albert-Jan Schot](https://www.cloudappie.nl/recognize-contributions-clim365) Inspired by: [Emily Mancini](https://learn.microsoft.com/microsoft-365/community/identifying-your-sharepoint-champions)

Retrieves activities for SharePoint Online, Teams and Viva Engage and shares the top 3 contributors for each category as an adaptive card to the specified webhook url.

:::note

As of September 1st 2021 reports pseudonymize user-level information. In order to use the user display name make sure to disable this option to provide the report with the UPN value [Privacy changes to Microsoft 365 Usage Analytics](https://techcommunity.microsoft.com/t5/microsoft-365-blog/EXAMPLE_SECRET_VALUE_PLACEHOLDER/ba-p/2694137). Without changing this value the sample will work but will return a hashed value that is not recognizable.

:::

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $m365Status = m365 status --output text

  if ($m365Status -eq "Logged Out") {
    # Connection to Microsoft 365
    m365 login
  }

  $webhookUrl = "<PUTYOURURLHERE>"

  # Send top 3 for SharePoint based on file actions.
  $activityUsers = m365 spo report activityuserdetail --period D7 --output json --query 'reverse(sort_by(@, &\"Viewed Or Edited File Count\")) | [0:3].\"User Principal Name\"' | ConvertFrom-Json
  $title = "SharePoint Weekly Social Champions"
  $card = '{ \"type\": \"AdaptiveCard\", \"$schema\": \"http://adaptivecards.io/schemas/adaptive-card.json\", \"version\": \"1.2\", \"body\": [  {  \"type\": \"TextBlock\",  \"text\": \"'+$($title)+'\",  \"wrap\": true,  \"size\": \"Medium\",  \"weight\": \"Bolder\",  \"color\": \"Attention\"  },  {  \"type\": \"TextBlock\",  \"wrap\": true,  \"text\": \"Week '+$(get-date -UFormat %V)+'\",  \"fontType\": \"Default\",  \"size\": \"Small\",  \"weight\": \"Lighter\",  \"isSubtle\": true  },  {  \"type\": \"FactSet\",  \"facts\": [   {   \"title\": \"First place\",   \"value\": \"'+$($activityUsers[0])+'\"   },   {   \"title\": \"Second place\",   \"value\": \"'+$($activityUsers[1])+'\"   },   {   \"title\": \"Third place\",   \"value\": \"'+$($activityUsers[2])+'\"   }  ]  } ] }'
  m365 adaptivecard send --url $webhookUrl --card $card

  # Send top 3 for Teams based on chat messages
  $activityUsers = m365 teams report useractivityuserdetail --period D7 --output json --query 'reverse(sort_by(@, &\"Team Chat Message Count\")) | [0:3].\"User Principal Name\"' | ConvertFrom-Json
  $title = "Teams Weekly Social Champions"
  $card = '{ \"type\": \"AdaptiveCard\", \"$schema\": \"http://adaptivecards.io/schemas/adaptive-card.json\", \"version\": \"1.2\", \"body\": [  {  \"type\": \"TextBlock\",  \"text\": \"'+$($title)+'\",  \"wrap\": true,  \"size\": \"Medium\",  \"weight\": \"Bolder\",  \"color\": \"Attention\"  },  {  \"type\": \"TextBlock\",  \"wrap\": true,  \"text\": \"Week '+$(get-date -UFormat %V)+'\",  \"fontType\": \"Default\",  \"size\": \"Small\",  \"weight\": \"Lighter\",  \"isSubtle\": true  },  {  \"type\": \"FactSet\",  \"facts\": [   {   \"title\": \"First place\",   \"value\": \"'+$($activityUsers[0])+'\"   },   {   \"title\": \"Second place\",   \"value\": \"'+$($activityUsers[1])+'\"   },   {   \"title\": \"Third place\",   \"value\": \"'+$($activityUsers[2])+'\"   }  ]  } ] }'
  m365 adaptivecard send --url $webhookUrl --card $card

  # Send top 3 for Viva Engage based on posts
  $activityUsers = m365 viva engage report activityuserdetail --period D7 --output json --query 'reverse(sort_by(@, &\"Posted Count\")) | [0:3].\"User Principal Name\"' | ConvertFrom-Json
  $title = "Viva Engage Weekly Social Champions"
  $card = '{ \"type\": \"AdaptiveCard\", \"$schema\": \"http://adaptivecards.io/schemas/adaptive-card.json\", \"version\": \"1.2\", \"body\": [  {  \"type\": \"TextBlock\",  \"text\": \"'+$($title)+'\",  \"wrap\": true,  \"size\": \"Medium\",  \"weight\": \"Bolder\",  \"color\": \"Attention\"  },  {  \"type\": \"TextBlock\",  \"wrap\": true,  \"text\": \"Week '+$(get-date -UFormat %V)+'\",  \"fontType\": \"Default\",  \"size\": \"Small\",  \"weight\": \"Lighter\",  \"isSubtle\": true  },  {  \"type\": \"FactSet\",  \"facts\": [   {   \"title\": \"First place\",   \"value\": \"'+$($activityUsers[0])+'\"   },   {   \"title\": \"Second place\",   \"value\": \"'+$($activityUsers[1])+'\"   },   {   \"title\": \"Third place\",   \"value\": \"'+$($activityUsers[2])+'\"   }  ]  } ] }'
  m365 adaptivecard send --url $webhookUrl --card $card
  ```

  </TabItem>
</Tabs>
