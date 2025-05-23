-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo file get

Gets information about the specified file

## Usage

```sh
m365 spo file get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the file is located.

`--url [url]`
: The server- or site-relative decoded URL of the file to retrieve. Specify either `url` or `id` but not both.

`-i, --id [id]`
: The UniqueId (GUID) of the file to retrieve. Specify either `url` or `id` but not both.

`--asString`
: Set to retrieve the contents of the specified file as string.

`--asListItem`
: Set to retrieve the underlying list item.

`--asFile`
: Set to save the file to the path specified in the path option.

`-p, --path [path]`
: The local path where to save the retrieved file. Must be specified when the `--asFile` option is used.

`--withPermissions`
: Set if you want to return associated roles and permissions.
```

<Global />

## Examples

Get file properties for a file with id (UniqueId) parameter located in a site.

```sh
m365 spo file get --webUrl https://contoso.sharepoint.com/sites/project-x --id 'b2307a39-e878-458b-bc90-03bc578531d6'
```

Get contents of the file with id (UniqueId) parameter located in a site.

```sh
m365 spo file get --webUrl https://contoso.sharepoint.com/sites/project-x --id 'b2307a39-e878-458b-bc90-03bc578531d6' --asString
```

Get list item properties for a file with id (UniqueId) parameter located in a site.

```sh
m365 spo file get --webUrl https://contoso.sharepoint.com/sites/project-x --id 'b2307a39-e878-458b-bc90-03bc578531d6' --asListItem
```

Saves the file with id (UniqueId) parameter located in a site to a local file.

```sh
m365 spo file get --webUrl https://contoso.sharepoint.com/sites/project-x --id 'b2307a39-e878-458b-bc90-03bc578531d6' --asFile --path /Users/user/documents/SavedAsTest1.docx
```

Return file properties for a file with server-relative url located in a site.

```sh
m365 spo file get --webUrl https://contoso.sharepoint.com/sites/project-x --url '/sites/project-x/documents/Test1.docx'
```

Returns a file as string for a file with server-relative url located in a site.

```sh
m365 spo file get --webUrl https://contoso.sharepoint.com/sites/project-x --url '/sites/project-x/documents/Test1.docx' --asString
```

Returns the list item properties for a file with the server-relative url located in a site.

```sh
m365 spo file get --webUrl https://contoso.sharepoint.com/sites/project-x --url '/sites/project-x/documents/Test1.docx' --asListItem
```

Saves a file with the server-relative url located in a site to a local file.

```sh
m365 spo file get --webUrl https://contoso.sharepoint.com/sites/project-x --url '/sites/project-x/documents/Test1.docx' --asFile --path /Users/user/documents/SavedAsTest1.docx
```

Gets the file properties for a file with id (UniqueId) parameter located in a site with permissions.

```sh
m365 spo file get --webUrl https://contoso.sharepoint.com/sites/project-x --id 'b2307a39-e878-458b-bc90-03bc578531d6' --withPermissions
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "CheckInComment": "",
    "CheckOutType": 2,
    "ContentTag": "{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1,1",
    "CustomizedPageStatus": 0,
    "ETag": "\"{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1\"",
    "Exists": true,
    "IrmEnabled": false,
    "Length": "5987",
    "Level": 1,
    "LinkingUri": null,
    "LinkingUrl": "",
    "MajorVersion": 1,
    "MinorVersion": 0,
    "Name": "Test1.docx",
    "ServerRelativeUrl": "/sites/project-x/documents/Test1.docx",
    "TimeCreated": "2022-10-30T10:16:18Z",
    "TimeLastModified": "2022-10-30T10:16:18Z",
    "Title": null,
    "UIVersion": 512,
    "UIVersionLabel": "1.0",
    "UniqueId": "b2307a39-e878-458b-bc90-03bc578531d6"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  CheckInComment      :
  CheckOutType        : 2
  ContentTag          : {03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1,1
  CustomizedPageStatus: 0
  ETag                : "{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1"
  Exists              : true
  IrmEnabled          : false
  Length              : 5987
  Level               : 1
  LinkingUri          : null
  LinkingUrl          :
  MajorVersion        : 1
  MinorVersion        : 0
  Name                : Test1.docx
  ServerRelativeUrl   : /sites/project-x/documents/Test1.docx
  TimeCreated         : 2022-10-30T10:16:18Z
  TimeLastModified    : 2022-10-30T10:16:18Z
  Title               : null
  UIVersion           : 512
  UIVersionLabel      : 1.0
  UniqueId            : b2307a39-e878-458b-bc90-03bc578531d6
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  CheckInComment,CheckOutType,ContentTag,CustomizedPageStatus,ETag,Exists,IrmEnabled,Length,Level,LinkingUri,LinkingUrl,MajorVersion,MinorVersion,Name,ServerRelativeUrl,TimeCreated,TimeLastModified,Title,UIVersion,UIVersionLabel,UniqueId
  ,2,"{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1,1",0,"""{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1""",1,,5987,1,,,1,0,Test1.docx,/sites/project-x/documents/Test1.docx,2022-10-30T10:16:18Z,2022-10-30T10:16:18Z,,512,1.0,b2307a39-e878-458b-bc90-03bc578531d6
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo file get --webUrl "https://contoso.sharepoint.com/sites/project-x" --url "/sites/project-x/shared documents/Document.docx"

  Date: 10/3/2023

  ## b2307a39-e878-458b-bc90-03bc578531d6

  Property | Value
  ---------|-------
  CheckInComment |
  CheckOutType | 2
  ContentTag | {03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1,1
  CustomizedPageStatus | 0
  ETag | "{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1"
  Exists | true
  ExistsAllowThrowForPolicyFailures | true
  IrmEnabled | false
  Length | 5987
  Level | 1
  LinkingUri | https://contoso.sharepoint.com/sites/project-x/shared%20documents/Document.docx?d=w59d4e6fcf6f94ce78bea0273cedb1a19
  LinkingUrl | https://contoso.sharepoint.com/sites/project-x/shared documents/Document.docx?d=w59d4e6fcf6f94ce78bea0273cedb1a19
  MajorVersion | 1
  MinorVersion | 0
  Name | Document.docx
  ServerRelativeUrl | /sites/project-x/shared documents/Document.docx
  TimeCreated | 2023-05-23T09:51:34Z
  TimeLastModified | 2023-05-23T10:13:01Z
  Title |
  UIVersion | 1536
  UIVersionLabel | 1.0
  UniqueId | b2307a39-e878-458b-bc90-03bc578531d6
  ```

  </TabItem>
</Tabs>

### `withPermissions` response

When we make use of the option `withPermissions` the response will differ.

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "CheckInComment": "",
    "CheckOutType": 2,
    "ContentTag": "{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1,1",
    "CustomizedPageStatus": 0,
    "ETag": "\"{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1\"",
    "Exists": true,
    "IrmEnabled": false,
    "Length": "5987",
    "Level": 1,
    "LinkingUri": null,
    "LinkingUrl": "",
    "MajorVersion": 1,
    "MinorVersion": 0,
    "Name": "Test1.docx",
    "ServerRelativeUrl": "/sites/project-x/documents/Test1.docx",
    "TimeCreated": "2022-10-30T10:16:18Z",
    "TimeLastModified": "2022-10-30T10:16:18Z",
    "Title": null,
    "UIVersion": 512,
    "UIVersionLabel": "1.0",
    "UniqueId": "b2307a39-e878-458b-bc90-03bc578531d6",
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
  CheckInComment      :
  CheckOutType        : 2
  ContentTag          : {03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1,1
  CustomizedPageStatus: 0
  ETag                : "{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1"
  Exists              : true
  IrmEnabled          : false
  Length              : 5987
  Level               : 1
  LinkingUri          : null
  LinkingUrl          :
  MajorVersion        : 1
  MinorVersion        : 0
  Name                : Test1.docx
  ServerRelativeUrl   : /sites/project-x/documents/Test1.docx
  TimeCreated         : 2022-10-30T10:16:18Z
  TimeLastModified    : 2022-10-30T10:16:18Z
  Title               : null
  UIVersion           : 512
  UIVersionLabel      : 1.0
  UniqueId            : b2307a39-e878-458b-bc90-03bc578531d6
  RoleAssignments     : [{"Member":{"Id":3,"IsHiddenInUI":false,"LoginName":"Communication site Owners","Title":"Communication site Owners","PrincipalType":8,"AllowMembersEditMembership":false,"AllowRequestToJoinLeave":false,"AutoAcceptRequestToJoinLeave":false,"Description":null,"OnlyAllowMembersViewMembership":false,"OwnerTitle":"Communication site Owners","RequestToJoinLeaveEmailSetting":""},"RoleDefinitionBindings":[{"BasePermissions":{"High":"2147483647","Low":"4294967295"},"Description":"Has full control.","Hidden":false,"Id":1073741829,"Name":"Full Control","Order":1,"RoleTypeKind":5,"BasePermissionsValue":["ViewListItems","AddListItems","EditListItems","DeleteListItems","ApproveItems","OpenItems","ViewVersions","DeleteVersions","CancelCheckout","ManagePersonalViews","ManageLists","ViewFormPages","AnonymousSearchAccessList","Open","ViewPages","AddAndCustomizePages","ApplyThemeAndBorder","ApplyStyleSheets","ViewUsageData","CreateSSCSite","ManageSubwebs","CreateGroups","ManagePermissions","BrowseDirectories","BrowseUserInfo","AddDelPrivateWebParts","UpdatePersonalWebParts","ManageWeb","AnonymousSearchAccessWebLists","UseClientIntegration","UseRemoteAPIs","ManageAlerts","CreateAlerts","EditMyUserInfo","EnumeratePermissions"],"RoleTypeKindValue":"Administrator"}],"PrincipalId":3}]
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  CheckInComment,CheckOutType,ContentTag,CustomizedPageStatus,ETag,Exists,IrmEnabled,Length,Level,LinkingUri,LinkingUrl,MajorVersion,MinorVersion,Name,ServerRelativeUrl,TimeCreated,TimeLastModified,Title,UIVersion,UIVersionLabel,UniqueId,RoleAssignments
  ,2,"{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1,1",0,"""{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1""",1,,5987,1,,,1,0,Test1.docx,/sites/project-x/documents/Test1.docx,2022-10-30T10:16:18Z,2022-10-30T10:16:18Z,,512,1.0,b2307a39-e878-458b-bc90-03bc578531d6,"[{""Member"":{""Id"":3,""IsHiddenInUI"":false,""LoginName"":""Communication site Owners"",""Title"":""Communication site Owners"",""PrincipalType"":8,""AllowMembersEditMembership"":false,""AllowRequestToJoinLeave"":false,""AutoAcceptRequestToJoinLeave"":false,""Description"":null,""OnlyAllowMembersViewMembership"":false,""OwnerTitle"":""Communication site Owners"",""RequestToJoinLeaveEmailSetting"":""""},""RoleDefinitionBindings"":[{""BasePermissions"":{""High"":""2147483647"",""Low"":""4294967295""},""Description"":""Has full control."",""Hidden"":false,""Id"":1073741829,""Name"":""Full Control"",""Order"":1,""RoleTypeKind"":5,""BasePermissionsValue"":[""ViewListItems"",""AddListItems"",""EditListItems"",""DeleteListItems"",""ApproveItems"",""OpenItems"",""ViewVersions"",""DeleteVersions"",""CancelCheckout"",""ManagePersonalViews"",""ManageLists"",""ViewFormPages"",""AnonymousSearchAccessList"",""Open"",""ViewPages"",""AddAndCustomizePages"",""ApplyThemeAndBorder"",""ApplyStyleSheets"",""ViewUsageData"",""CreateSSCSite"",""ManageSubwebs"",""CreateGroups"",""ManagePermissions"",""BrowseDirectories"",""BrowseUserInfo"",""AddDelPrivateWebParts"",""UpdatePersonalWebParts"",""ManageWeb"",""AnonymousSearchAccessWebLists"",""UseClientIntegration"",""UseRemoteAPIs"",""ManageAlerts"",""CreateAlerts"",""EditMyUserInfo"",""EnumeratePermissions""],""RoleTypeKindValue"":""Administrator""}],""PrincipalId"":3}]"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo file get --webUrl "https://contoso.sharepoint.com/sites/project-x" --url "/sites/project-x/shared documents/Document.docx" --withPermissions "true"

  Date: 10/3/2023

  ## b2307a39-e878-458b-bc90-03bc578531d6

  Property | Value
  ---------|-------
  CheckInComment |
  CheckOutType | 2
  ContentTag | {03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1,1
  CustomizedPageStatus | 0
  ETag | "{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1"
  Exists | true
  ExistsAllowThrowForPolicyFailures | true
  IrmEnabled | false
  Length | 33454
  Level | 1
  LinkingUri | https://contoso.sharepoint.com/sites/project-x/shared%20documents/Document.docx?d=w59d4e6fcf6f94ce78bea0273cedb1a19
  LinkingUrl | https://contoso.sharepoint.com/sites/project-x/shared documents/Document.docx?d=w59d4e6fcf6f94ce78bea0273cedb1a19
  MajorVersion | 1
  MinorVersion | 0
  Name | Document3.docx
  ServerRelativeUrl | /sites/project-x/shared documents/Document3.docx
  TimeCreated | 2023-05-23T09:51:34Z
  TimeLastModified | 2023-05-23T10:13:01Z
  Title |
  UIVersion | 1536
  UIVersionLabel | 1.0
  UniqueId | b2307a39-e878-458b-bc90-03bc578531d6
  ```

  </TabItem>
</Tabs>
