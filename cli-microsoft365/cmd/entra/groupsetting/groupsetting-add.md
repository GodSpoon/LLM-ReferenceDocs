-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra groupsetting add

Creates a group setting

## Usage

```sh
m365 entra groupsetting add [options]
```

## Options

```md definition-list
`-i, --templateId <templateId>`
: The ID of the group setting template to use to create the group setting
```

<Global />

## Remarks

To create a group setting, you have to specify the ID of the group setting template that should be used to create the setting. You can retrieve the ID of the template using the [entra groupsettingtemplate list](../groupsettingtemplate/groupsettingtemplate-list.mdx) command.

To specify values for the different properties specified in the group setting template, include additional options that match the property in the group setting template. For example `--ClassificationList 'HBI, MBI, LBI, GDPR'` will set the list of classifications to use on modern SharePoint sites.

Each group setting template specifies default value for each property. If you don't specify a value for the particular property yourself, the default value from the group setting template will be used. To find out which properties are available for the particular group setting template, use the [entra groupsettingtemplate get](../groupsettingtemplate/groupsettingtemplate-get.mdx) command.

If the specified templateId doesn't reference a valid group setting template, you will get a _Resource 'xyz' does not exist or one of its queried reference-property objects are not present._ error.

If you try to add a group setting using a template, for which a setting already exists, you will get a _A conflicting object with one or more of the specified property values is present in the directory._ error.

## Examples

Configure classification for modern SharePoint sites

```sh
m365 entra groupsetting add --templateId 62375ab9-6b52-47ed-826b-58e47e0e304b --UsageGuidelinesUrl https://contoso.sharepoint.com/sites/compliance --ClassificationList 'HBI, MBI, LBI, GDPR' --DefaultClassification MBI
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "c01f5e50-aabf-4851-983b-dd7d59b8f07c",
    "displayName": null,
    "templateId": "62375ab9-6b52-47ed-826b-58e47e0e304b",
    "values": [
      {
        "name": "UsageGuidelinesUrl",
        "value": "https://contoso.sharepoint.com/sites/compliance"
      },
      {
        "name": "ClassificationList",
        "value": "HBI, MBI, LBI, GDPR"
      },
      {
        "name": "DefaultClassification",
        "value": "MBI"
      },
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
        "name": "EnableGroupCreation",
        "value": "true"
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  displayName: null
  id         : 01cb3b73-3387-4dec-af09-71cf0de65f0b
  templateId : 62375ab9-6b52-47ed-826b-58e47e0e304b
  values     : [{"name":"UsageGuidelinesUrl","value":"https://contoso.sharepoint.com/sites/compliance"},{"name":"ClassificationList","value":"HBI, MBI, LBI, GDPR"},{"name":"DefaultClassification","value":"MBI"},{"name":"NewUnifiedGroupWritebackDefault","value":"true"},{"name":"EnableMIPLabels","value":"false"},{"name":"CustomBlockedWordsList","value":""},{"name":"EnableMSStandardBlockedWords","value":"false"},{"name":"ClassificationDescriptions","value":""},{"name":"PrefixSuffixNamingRequirement","value":""},{"name":"AllowGuestsToBeGroupOwner","value":"false"},{"name":"AllowGuestsToAccessGroups","value":"true"},{"name":"GuestUsageGuidelinesUrl","value":""},{"name":"GroupCreationAllowedGroupId","value":""},{"name":"AllowToAddGuests","value":"true"},{"name":"EnableGroupCreation","value":"true"}]
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,templateId
  689ac304-6628-4b69-9e86-2ebd99f29da3,62375ab9-6b52-47ed-826b-58e47e0e304b
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra groupsetting add --templateId "62375ab9-6b52-47ed-826b-58e47e0e304b" --UsageGuidelinesUrl "https://contoso.sharepoint.com/sites/compliance" --ClassificationList "HBI, MBI, LBI, GDPR" --DefaultClassification "MBI"

  Date: 2023-06-01

  ## 14b492fc-5cbe-456c-b083-ee62638c627c

  Property | Value
  ---------|-------
  id | 14b492fc-5cbe-456c-b083-ee62638c627c
  templateId | 62375ab9-6b52-47ed-826b-58e47e0e304b
  ```

  </TabItem>
</Tabs>
