-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo roledefinition get

Gets specified role definition from web

## Usage

```sh
m365 spo roledefinition get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site for which to retrieve the role definition.

`-i, --id <id>`
: The Id of the role definition to retrieve.
```

<Global />

## Examples

Retrieve the role definition for the given site

```sh
m365 spo roledefinition get --webUrl https://contoso.sharepoint.com/sites/project-x --id 1
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
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
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  BasePermissions     : {"High":"2147483647","Low":"4294967295"}
  BasePermissionsValue: ["ViewListItems","AddListItems","EditListItems","DeleteListItems","ApproveItems","OpenItems","ViewVersions","DeleteVersions","CancelCheckout","ManagePersonalViews","ManageLists","ViewFormPages","AnonymousSearchAccessList","Open","ViewPages","AddAndCustomizePages","ApplyThemeAndBorder","ApplyStyleSheets","ViewUsageData","CreateSSCSite","ManageSubwebs","CreateGroups","ManagePermissions","BrowseDirectories","BrowseUserInfo","AddDelPrivateWebParts","UpdatePersonalWebParts","ManageWeb","AnonymousSearchAccessWebLists","UseClientIntegration","UseRemoteAPIs","ManageAlerts","CreateAlerts","EditMyUserInfo","EnumeratePermissions"]
  Description         : Has full control.
  Hidden              : false
  Id                  : 1073741829
  Name                : Full Control
  Order               : 1
  RoleTypeKind        : 5
  RoleTypeKindValue   : Administrator
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  BasePermissions,Description,Hidden,Id,Name,Order,RoleTypeKind,BasePermissionsValue,RoleTypeKindValue
  "{""High"":""2147483647"",""Low"":""4294967295""}",Has full control.,,1073741829,Full Control,1,5,"[""ViewListItems"",""AddListItems"",""EditListItems"",""DeleteListItems"",""ApproveItems"",""OpenItems"",""ViewVersions"",""DeleteVersions"",""CancelCheckout"",""ManagePersonalViews"",""ManageLists"",""ViewFormPages"",""AnonymousSearchAccessList"",""Open"",""ViewPages"",""AddAndCustomizePages"",""ApplyThemeAndBorder"",""ApplyStyleSheets"",""ViewUsageData"",""CreateSSCSite"",""ManageSubwebs"",""CreateGroups"",""ManagePermissions"",""BrowseDirectories"",""BrowseUserInfo"",""AddDelPrivateWebParts"",""UpdatePersonalWebParts"",""ManageWeb"",""AnonymousSearchAccessWebLists"",""UseClientIntegration"",""UseRemoteAPIs"",""ManageAlerts"",""CreateAlerts"",""EditMyUserInfo"",""EnumeratePermissions""]",Administrator
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo roledefinition get --webUrl "https://contoso.sharepoint.com/sites/project-x" --id "1073741829"

  Date: 5/6/2023

  ## Full Control (1073741829)

  Property | Value
  ---------|-------
  Description | Has full control.
  Hidden | false
  Id | 1073741829
  Name | Full Control
  Order | 1
  RoleTypeKind | 5
  RoleTypeKindValue | Administrator
  ```

  </TabItem>
</Tabs>
