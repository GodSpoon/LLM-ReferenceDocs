-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra groupsetting get

Gets information about the particular group setting

## Usage

```sh
m365 entra groupsetting get [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The ID of the group setting to retrieve
```

<Global />

## Examples

Get information about the group setting with id _1caf7dcd-7e83-4c3a-94f7-932a1299c844_

```sh
m365 entra groupsetting get --id 1caf7dcd-7e83-4c3a-94f7-932a1299c844
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "14b492fc-5cbe-456c-b083-ee62638c627c",
    "displayName": "Group.Unified",
    "templateId": "62375ab9-6b52-47ed-826b-58e47e0e304b",
    "values": [
      {
        "name": "NewUnifiedGroupWritebackDefault",
        "value": "true"
      },
      {
        "name": "EnableMIPLabels",
        "value": "false"
      },
      {
        "name": "CustomBlockedWordsList",
        "value": ""
      },
      {
        "name": "EnableMSStandardBlockedWords",
        "value": "false"
      },
      {
        "name": "ClassificationDescriptions",
        "value": ""
      },
      {
        "name": "DefaultClassification",
        "value": "MBI"
      },
      {
        "name": "PrefixSuffixNamingRequirement",
        "value": ""
      },
      {
        "name": "AllowGuestsToBeGroupOwner",
        "value": "false"
      },
      {
        "name": "AllowGuestsToAccessGroups",
        "value": "true"
      },
      {
        "name": "GuestUsageGuidelinesUrl",
        "value": ""
      },
      {
        "name": "GroupCreationAllowedGroupId",
        "value": ""
      },
      {
        "name": "AllowToAddGuests",
        "value": "true"
      },
      {
        "name": "UsageGuidelinesUrl",
        "value": "https://contoso.sharepoint.com/sites/compliance"
      },
      {
        "name": "ClassificationList",
        "value": "HBI,MBI,LBI,GDPR"
      },
      {
        "name": "EnableGroupCreation",
        "value": "true"
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  displayName: Group.Unified
  id         : 14b492fc-5cbe-456c-b083-ee62638c627c
  templateId : 62375ab9-6b52-47ed-826b-58e47e0e304b
  values     : [{"name":"NewUnifiedGroupWritebackDefault","value":"true"},{"name":"EnableMIPLabels","value":"false"},{"name":"CustomBlockedWordsList","value":""},{"name":"EnableMSStandardBlockedWords","value":"false"},{"name":"ClassificationDescriptions","value":""},{"name":"DefaultClassification","value":"MBI"},{"name":"PrefixSuffixNamingRequirement","value":""},{"name":"AllowGuestsToBeGroupOwner","value":"false"},{"name":"AllowGuestsToAccessGroups","value":"true"},{"name":"GuestUsageGuidelinesUrl","value":""},{"name":"GroupCreationAllowedGroupId","value":""},{"name":"AllowToAddGuests","value":"true"},{"name":"UsageGuidelinesUrl","value":"https://contoso.sharepoint.com/sites/compliance"},{"name":"ClassificationList","value":"HBI,MBI,LBI,GDPR"},{"name":"EnableGroupCreation","value":"true"}]
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,templateId
  14b492fc-5cbe-456c-b083-ee62638c627c,Group.Unified,62375ab9-6b52-47ed-826b-58e47e0e304b
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra groupsetting get --id "14b492fc-5cbe-456c-b083-ee62638c627c"

  Date: 2023-06-01

  ## Group.Unified (14b492fc-5cbe-456c-b083-ee62638c627c)

  Property | Value
  ---------|-------
  id | 14b492fc-5cbe-456c-b083-ee62638c627c
  displayName | Group.Unified
  templateId | 62375ab9-6b52-47ed-826b-58e47e0e304b
  ```

  </TabItem>
</Tabs>
