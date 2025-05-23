-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo web retentionlabel list

Get a list of retention labels that are available on a site.

## Usage

```sh
m365 spo web retentionlabel list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site.
```

<Global />

## Examples

Get a list of retention labels for the _Sales_ site

```sh
m365 spo web retentionlabel list --webUrl 'https://contoso.sharepoint.com/sites/sales'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "AcceptMessagesOnlyFromSendersOrMembers": false,
      "AccessType": null,
      "AllowAccessFromUnmanagedDevice": null,
      "AutoDelete": true,
      "BlockDelete": true,
      "BlockEdit": false,
      "ComplianceFlags": 1,
      "ContainsSiteLabel": false,
      "DisplayName": "",
      "EncryptionRMSTemplateId": null,
      "HasRetentionAction": true,
      "IsEventTag": false,
      "MultiStageReviewerEmail": null,
      "NextStageComplianceTag": null,
      "Notes": null,
      "RequireSenderAuthenticationEnabled": false,
      "ReviewerEmail": null,
      "SharingCapabilities": null,
      "SuperLock": false,
      "TagDuration": 2555,
      "TagId": "def61080-111c-4aea-b72f-5b60e516e36c",
      "TagName": "Some label",
      "TagRetentionBasedOn": "CreationAgeInDays",
      "UnlockedAsDefault": false
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  TagId                                 TagName
  ------------------------------------  --------------
  def61080-111c-4aea-b72f-5b60e516e36c  Some label
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  AcceptMessagesOnlyFromSendersOrMembers,AutoDelete,BlockDelete,BlockEdit,ComplianceFlags,ContainsSiteLabel,DisplayName,HasRetentionAction,IsEventTag,RequireSenderAuthenticationEnabled,SuperLock,TagDuration,TagId,TagName,TagRetentionBasedOn,UnlockedAsDefault
  ,1,1,,1,,,1,,,,2555,def61080-111c-4aea-b72f-5b60e516e36c,Some label,CreationAgeInDays,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo web retentionlabel list --webUrl "https://contoso.sharepoint.com/sites/sales"

  Date: 4/11/2023

  Property | Value
  ---------|-------
  AcceptMessagesOnlyFromSendersOrMembers | false
  AutoDelete | true
  BlockDelete | true
  BlockEdit | false
  ComplianceFlags | 1
  ContainsSiteLabel | false
  DisplayName | 
  HasRetentionAction | true
  IsEventTag | false
  RequireSenderAuthenticationEnabled | false
  SuperLock | false
  TagDuration | 2555
  TagId | def61080-111c-4aea-b72f-5b60e516e36c
  TagName | Some Label
  TagRetentionBasedOn | CreationAgeInDays
  UnlockedAsDefault | false
  ```

  </TabItem>
</Tabs>
