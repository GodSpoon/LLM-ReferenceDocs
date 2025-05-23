-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo roledefinition list

Gets list of role definitions for the specified site

## Usage

```sh
m365 spo roledefinition list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site for which to retrieve role definitions.
```

<Global />

## Examples

Return list of role definitions for the given site

```sh
m365 spo roledefinition list --webUrl https://contoso.sharepoint.com/sites/project-x
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "BasePermissions": {
        "High": 2147483647,
        "Low": 4294967295
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
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Id          Name
  ----------  -----------------------
  1073741829  Full Control
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Id,Name
  1073741829,Full Control
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo roledefinition list --webUrl "https://contoso.sharepoint.com/sites/project-x"

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
