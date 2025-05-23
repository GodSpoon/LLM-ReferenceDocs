-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo listitem get

Gets a list item from the specified list

## Usage

```sh
m365 spo listitem get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the item is located.

`-i, --id [id]`
: ID of the item to retrieve. Specify either `id` or `uniqueId` but not both.

`--uniqueId [uniqueId]`
: The Unique ID (GUID) of the item to retrieve. Specify either `id` or `uniqueId` but not both.

`-l, --listId [listId]`
: ID of the list. Specify either `listTitle`, `listId`, or `listUrl` but not multiple.

`-t, --listTitle [listTitle]`
: Title of the list. Specify either `listTitle`, `listId`, or `listUrl` but not multiple.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listTitle`, `listId`, or `listUrl` but not multiple.

`-p, --properties [properties]`
: Comma-separated list of properties to retrieve. Will retrieve all properties if not specified and json output is requested.

`--withPermissions`
: Set if you want to return associated roles and permissions.
```

<Global />

## Remarks

If you want to specify a lookup type in the `properties` option, define which columns from the related list should be returned.

## Examples

Get an item with the ID parameter from a given list in a given site.

```sh
m365 spo listitem get --listTitle "Demo List" --id 147 --webUrl https://contoso.sharepoint.com/sites/project-x
```

Get an item with the Unique ID parameter from a given list in a given site.

```sh
m365 spo listitem get --listTitle "Demo List" --uniqueId "64dc28c4-3c43-45f6-ba66-307d9eb7e6aa" --webUrl https://contoso.sharepoint.com/sites/project-x
```

Get an item columns with the ID parameter from a given list in a given site.

```sh
m365 spo listitem get --listTitle "Demo List" --id 147 --webUrl https://contoso.sharepoint.com/sites/project-x --properties "Title,Created"
```

Get an item columns and lookup column with the ID parameter from a given list in a given site.

```sh
m365 spo listitem get --listTitle "Demo List" --id 147 --webUrl https://contoso.sharepoint.com/sites/project-x --properties "Title,Created,Company/Title"
```

Get an item with specific properties from a given list based on the server-relative URL in a specific site.

```sh
m365 spo listitem get --listUrl /sites/project-x/documents --id 147 --webUrl https://contoso.sharepoint.com/sites/project-x --properties "Title,Created,Company/Title"
```

Get an item with ID parameter from a given list based on the server-relative URL in a specific site with permissions.

```sh
m365 spo listitem get --listTitle "Demo List" --id 147 --webUrl https://contoso.sharepoint.com/sites/project-x --withPermissions
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "FileSystemObjectType": 0,
    "Id": 147,
    "ServerRedirectedEmbedUri": null,
    "ServerRedirectedEmbedUrl": "",
    "ContentTypeId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "Title": "Demo Item",
    "Modified": "2022-10-30T10:55:37Z",
    "Created": "2022-10-30T10:55:22Z",
    "AuthorId": 10,
    "EditorId": 10,
    "OData__UIVersionString": "3.0",
    "Attachments": false,
    "GUID": "87f3138d-fac3-4126-97c0-543e55672261",
    "ComplianceAssetId": null
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Attachments             : false
  AuthorId                : 10
  ComplianceAssetId       : null
  ContentTypeId           : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  Created                 : 2022-10-30T10:55:22Z
  EditorId                : 10
  FileSystemObjectType    : 0
  GUID                    : 87f3138d-fac3-4126-97c0-543e55672261
  Id                      : 147
  Modified                : 2022-10-30T10:55:37Z
  OData__UIVersionString  : 3.0
  ServerRedirectedEmbedUri: null
  ServerRedirectedEmbedUrl:
  Title                   : Demo Item
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  FileSystemObjectType,Id,ServerRedirectedEmbedUri,ServerRedirectedEmbedUrl,ContentTypeId,Title,Modified,Created,AuthorId,EditorId,OData__UIVersionString,Attachments,GUID,ComplianceAssetId
  0,147,,,EXAMPLE_SECRET_VALUE_PLACEHOLDER,Demo Item,2022-10-30T10:55:37Z,2022-10-30T10:55:22Z,10,10,3.0,,87f3138d-fac3-4126-97c0-543e55672261,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo listitem get --webUrl "https://contoso.sharepoint.com" --listTitle "My List" --id "147"

  Date: 2/20/2023

  ## Demo Item (147)

  Property | Value
  ---------|-------
  FileSystemObjectType | 0
  Id | 147
  ServerRedirectedEmbedUri | null
  ServerRedirectedEmbedUrl |
  ContentTypeId | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  Title | Demo Item
  ComplianceAssetId | null
  FieldName1 | null
  Modified | 2022-10-30T10:55:37Z
  Created | 2022-10-30T10:55:22Z
  AuthorId | 10
  EditorId | 10
  OData\_\_UIVersionString | 3.0
  Attachments | false
  GUID | 87f3138d-fac3-4126-97c0-543e55672261
  ```

  </TabItem>
</Tabs>

### `withPermissions` response

When we make use of the option `withPermissions` the response will differ. 

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "FileSystemObjectType": 0,
    "Id": 147,
    "ServerRedirectedEmbedUri": null,
    "ServerRedirectedEmbedUrl": "",
    "ContentTypeId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "Title": "Demo Item",
    "Modified": "2022-10-30T10:55:37Z",
    "Created": "2022-10-30T10:55:22Z",
    "AuthorId": 10,
    "EditorId": 10,
    "OData__UIVersionString": "3.0",
    "Attachments": false,
    "GUID": "87f3138d-fac3-4126-97c0-543e55672261",
    "ComplianceAssetId": null,
    "RoleAssignments": [
      {
        "Member": {
          "Id": 3,
          "IsHiddenInUI": false,
          "LoginName": "Communication site Owners",
          "Title": "Communication site Owners",
          "PrincipalType": 8,
          "AllowMembersEditMembership": false,
          "AllowRequestToJoinLeave": false,
          "AutoAcceptRequestToJoinLeave": false,
          "Description": null,
          "OnlyAllowMembersViewMembership": false,
          "OwnerTitle": "Communication site Owners",
          "RequestToJoinLeaveEmailSetting": ""
        },
        "RoleDefinitionBindings": [
          {
            "BasePermissions": {
              "High": "2147483647",
              "Low": "4294967295"
            },
            "Description": "Has full control.",
            "Hidden": false,
            "Id": 1073741829,
            "Name": "Full Control",
            "Order": 1,
            "RoleTypeKind": 5,
            "BasePermissionsValue": [
              "ViewListItems",
              "AddListItems",
              "EditListItems",
              "DeleteListItems",
              "ApproveItems",
              "OpenItems",
              "ViewVersions",
              "DeleteVersions",
              "CancelCheckout",
              "ManagePersonalViews",
              "ManageLists",
              "ViewFormPages",
              "AnonymousSearchAccessList",
              "Open",
              "ViewPages",
              "AddAndCustomizePages",
              "ApplyThemeAndBorder",
              "ApplyStyleSheets",
              "ViewUsageData",
              "CreateSSCSite",
              "ManageSubwebs",
              "CreateGroups",
              "ManagePermissions",
              "BrowseDirectories",
              "BrowseUserInfo",
              "AddDelPrivateWebParts",
              "UpdatePersonalWebParts",
              "ManageWeb",
              "AnonymousSearchAccessWebLists",
              "UseClientIntegration",
              "UseRemoteAPIs",
              "ManageAlerts",
              "CreateAlerts",
              "EditMyUserInfo",
              "EnumeratePermissions"
            ],
            "RoleTypeKindValue": "Administrator"
          }
        ],
        "PrincipalId": 3
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Attachments             : false
  AuthorId                : 10
  ComplianceAssetId       : null
  ContentTypeId           : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  Created                 : 2022-10-30T10:55:22Z
  EditorId                : 10
  FileSystemObjectType    : 0
  GUID                    : 87f3138d-fac3-4126-97c0-543e55672261
  Id                      : 147
  Modified                : 2022-10-30T10:55:37Z
  OData__UIVersionString  : 3.0
  RoleAssignments         : [{"Member":{"Id":3,"IsHiddenInUI":false,"LoginName":"Communication site Owners","Title":"Communication site Owners","PrincipalType":8,"AllowMembersEditMembership":false,"AllowRequestToJoinLeave":false,"AutoAcceptRequestToJoinLeave":false,"Description":null,"OnlyAllowMembersViewMembership":false,"OwnerTitle":"Communication site Owners","RequestToJoinLeaveEmailSetting":""},"RoleDefinitionBindings":[{"BasePermissions":{"High":"2147483647","Low":"4294967295"},"Description":"Has full control.","Hidden":false,"Id":1073741829,"Name":"Full Control","Order":1,"RoleTypeKind":5,"BasePermissionsValue":["ViewListItems","AddListItems","EditListItems","DeleteListItems","ApproveItems","OpenItems","ViewVersions","DeleteVersions","CancelCheckout","ManagePersonalViews","ManageLists","ViewFormPages","AnonymousSearchAccessList","Open","ViewPages","AddAndCustomizePages","ApplyThemeAndBorder","ApplyStyleSheets","ViewUsageData","CreateSSCSite","ManageSubwebs","CreateGroups","ManagePermissions","BrowseDirectories","BrowseUserInfo","AddDelPrivateWebParts","UpdatePersonalWebParts","ManageWeb","AnonymousSearchAccessWebLists","UseClientIntegration","UseRemoteAPIs","ManageAlerts","CreateAlerts","EditMyUserInfo","EnumeratePermissions"],"RoleTypeKindValue":"Administrator"}],"PrincipalId":3}]
  ServerRedirectedEmbedUri: null
  ServerRedirectedEmbedUrl:
  Title                   : Demo Item
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  FileSystemObjectType,Id,ServerRedirectedEmbedUri,ServerRedirectedEmbedUrl,ContentTypeId,Title,Modified,Created,AuthorId,EditorId,OData__UIVersionString,Attachments,GUID,ComplianceAssetId,RoleAssignments
  0,147,,,EXAMPLE_SECRET_VALUE_PLACEHOLDER,Demo Item,2022-10-30T10:55:37Z,2022-10-30T10:55:22Z,10,10,3.0,,87f3138d-fac3-4126-97c0-543e55672261,"[{""Member"":{""Id"":3,""IsHiddenInUI"":false,""LoginName"":""Communication site Owners"",""Title"":""Communication site Owners"",""PrincipalType"":8,""AllowMembersEditMembership"":false,""AllowRequestToJoinLeave"":false,""AutoAcceptRequestToJoinLeave"":false,""Description"":null,""OnlyAllowMembersViewMembership"":false,""OwnerTitle"":""Communication site Owners"",""RequestToJoinLeaveEmailSetting"":""""},""RoleDefinitionBindings"":[{""BasePermissions"":{""High"":""2147483647"",""Low"":""4294967295""},""Description"":""Has full control."",""Hidden"":false,""Id"":1073741829,""Name"":""Full Control"",""Order"":1,""RoleTypeKind"":5,""BasePermissionsValue"":[""ViewListItems"",""AddListItems"",""EditListItems"",""DeleteListItems"",""ApproveItems"",""OpenItems"",""ViewVersions"",""DeleteVersions"",""CancelCheckout"",""ManagePersonalViews"",""ManageLists"",""ViewFormPages"",""AnonymousSearchAccessList"",""Open"",""ViewPages"",""AddAndCustomizePages"",""ApplyThemeAndBorder"",""ApplyStyleSheets"",""ViewUsageData"",""CreateSSCSite"",""ManageSubwebs"",""CreateGroups"",""ManagePermissions"",""BrowseDirectories"",""BrowseUserInfo"",""AddDelPrivateWebParts"",""UpdatePersonalWebParts"",""ManageWeb"",""AnonymousSearchAccessWebLists"",""UseClientIntegration"",""UseRemoteAPIs"",""ManageAlerts"",""CreateAlerts"",""EditMyUserInfo"",""EnumeratePermissions""],""RoleTypeKindValue"":""Administrator""}],""PrincipalId"":3}]"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo listitem get --webUrl "https://contoso.sharepoint.com" --listTitle "My List" --id "147" --withPermissions "true"

  Date: 2/20/2023

  ## Demo Item (1)

  Property | Value
  ---------|-------
  FileSystemObjectType | 0
  Id | 147
  ServerRedirectedEmbedUri | null
  ServerRedirectedEmbedUrl |
  ContentTypeId | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  Title | Demo Item
  ComplianceAssetId | null
  FieldName1 | null
  Modified | 2022-10-30T10:55:37Z
  Created | 2022-10-30T10:55:22Z
  AuthorId | 10
  EditorId | 10
  OData\_\_UIVersionString | 3.0
  Attachments | false
  GUID | 87f3138d-fac3-4126-97c0-543e55672261
  ```

  </TabItem>
</Tabs>
