-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo list retentionlabel get

Gets the default retention label set on the specified list or library.

## Usage

```sh
m365 spo list retentionlabel get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list to get the label from is located.

`-l, --listId [listId]`
: ID of the list to get the label from. Specify either `listId`, `listTitle`, or `listUrl` but not multiple.

`-t, --listTitle [listTitle]`
: Title of the list to get the label from. Specify either `listId`, `listTitle`, or `listUrl` but not multiple.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listId`, `listTitle`, or `listUrl` but not multiple.
```

<Global />

## Examples

Gets retention label set on the list with specified title located in the specified site.

```sh
m365 spo list retentionlabel get --listTitle ContosoList --webUrl https://contoso.sharepoint.com/sites/project-x
```

Gets retention label set on the list with specified id located in the specified site.

```sh
m365 spo list retentionlabel get --listId cc27a922-8224-4296-90a5-ebbc54da2e85 --webUrl https://contoso.sharepoint.com/sites/project-x
```

Gets retention label set on the list with specified server relative url located in the specified site.

```sh
m365 spo list retentionlabel get --listUrl 'sites/project-x/Documents' --webUrl https://contoso.sharepoint.com/sites/project-x
```

Gets retention label set on the list with specified site-relative URL located in the specified site.

```sh
m365 spo list retentionlabel get --listUrl 'Shared Documents' --webUrl https://contoso.sharepoint.com/sites/project-x
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "AcceptMessagesOnlyFromSendersOrMembers": false,
    "AccessType": null,
    "AllowAccessFromUnmanagedDevice": null,
    "AutoDelete": false,
    "BlockDelete": false,
    "BlockEdit": false,
    "ContainsSiteLabel": false,
    "DisplayName": "Label A",
    "EncryptionRMSTemplateId": null,
    "HasRetentionAction": false,
    "IsEventTag": false,
    "Notes": null,
    "RequireSenderAuthenticationEnabled": false,
    "ReviewerEmail": null,
    "SharingCapabilities": null,
    "SuperLock": false,
    "TagDuration": 0,
    "TagId": "4d535433-2a7b-40b0-9dad-8f0f8f3b3841",
    "TagName": "Sensitive",
    "TagRetentionBasedOn": null
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  AcceptMessagesOnlyFromSendersOrMembers: false
  AccessType                            : null
  AllowAccessFromUnmanagedDevice        : null
  AutoDelete                            : false
  BlockDelete                           : false
  BlockEdit                             : false
  ContainsSiteLabel                     : false
  DisplayName                           : Label A
  EncryptionRMSTemplateId               : null
  HasRetentionAction                    : false
  IsEventTag                            : false
  Notes                                 : null
  RequireSenderAuthenticationEnabled    : false
  ReviewerEmail                         : null
  SharingCapabilities                   : null
  SuperLock                             : false
  TagDuration                           : 0
  TagId                                 : 4d535433-2a7b-40b0-9dad-8f0f8f3b3841
  TagName                               : Sensitive
  TagRetentionBasedOn                   : null
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  AcceptMessagesOnlyFromSendersOrMembers,AccessType,AllowAccessFromUnmanagedDevice,AutoDelete,BlockDelete,BlockEdit,ContainsSiteLabel,DisplayName,EncryptionRMSTemplateId,HasRetentionAction,IsEventTag,Notes,RequireSenderAuthenticationEnabled,ReviewerEmail,SharingCapabilities,SuperLock,TagDuration,TagId,TagName,TagRetentionBasedOn
  false,,,false,false,false,false,Label A,,false,false,,false,,,false,0,4d535433-2a7b-40b0-9dad-8f0f8f3b3841,Sensitive,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo list retentionlabel get --listUrl "Shared Documents" --webUrl https://contoso.sharepoint.com/sites/project-x

  Date: 2/20/2023

  ## Label A (4d535433-2a7b-40b0-9dad-8f0f8f3b3841)

  Property | Value
  ---------|-------
  AcceptMessagesOnlyFromSendersOrMembers | false
  AccessType | null
  AllowAccessFromUnmanagedDevice | null
  AutoDelete | false
  BlockDelete | false
  BlockEdit | false
  ContainsSiteLabel | false
  DisplayName | Label A
  EncryptionRMSTemplateId | null
  HasRetentionAction | false
  IsEventTag | false
  Notes | null
  RequireSenderAuthenticationEnabled | false
  ReviewerEmail | null
  SharingCapabilities | null
  SuperLock | false
  TagDuration | 0
  TagId | 4d535433-2a7b-40b0-9dad-8f0f8f3b3841
  TagName | Sensitive
  TagRetentionBasedOn | null
  ```

  </TabItem>
</Tabs>
