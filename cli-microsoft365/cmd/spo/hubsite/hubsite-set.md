-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo hubsite set

Updates properties of the specified hub site

## Usage

```sh
m365 spo hubsite set [options]
```

## Options

```md definition-list
`-i, --id <id>`
: ID of the hub site.

`-t, --title [title]`
: The new title for the hub site.

`-d, --description [description]`
: The new description for the hub site.

`-l, --logoUrl [logoUrl]`
: The URL of the new logo for the hub site.
```

<Global />

## Remarks

:::info

To use this command you must be a Global or SharePoint administrator.

:::

If the specified `id` doesn't refer to an existing hub site, you will get an `Unknown Error` error.

## Examples

Update hub site's title.

```sh
m365 spo hubsite set --id 255a50b2-527f-4413-8485-57f4c17a24d1 --title Sales
```

Update hub site's title and description.

```sh
m365 spo hubsite set --id 255a50b2-527f-4413-8485-57f4c17a24d1 --title Sales --description "All things sales"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Description": "All things sales",
    "EnablePermissionsSync": false,
    "HideNameInNavigation": false,
    "ID": "255a50b2-527f-4413-8485-57f4c17a24d1",
    "LogoUrl": "https://contoso.sharepoint.com/sites/intra/SiteAssets/teapoint.png",
    "ParentHubSiteId": "/Guid(00000000-0000-0000-0000-000000000000)/",
    "Permissions": null,
    "RequiresJoinApproval": false,
    "SiteDesignId": "/Guid(184644fb-90ed-4841-a7ad-6930cf819060)/",
    "SiteId": "255a50b2-527f-4413-8485-57f4c17a24d1",
    "SiteUrl": "https://contoso.sharepoint.com/sites/intra",
    "Title": "Sales"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Description          : All things sales
  EnablePermissionsSync: false
  HideNameInNavigation : false
  ID                   : 255a50b2-527f-4413-8485-57f4c17a24d1
  LogoUrl              : https://contoso.sharepoint.com/sites/intra/SiteAssets/teapoint.png
  ParentHubSiteId      : /Guid(00000000-0000-0000-0000-000000000000)/
  Permissions          : null
  RequiresJoinApproval : false
  SiteDesignId         : /Guid(184644fb-90ed-4841-a7ad-6930cf819060)/
  SiteId               : 255a50b2-527f-4413-8485-57f4c17a24d1
  SiteUrl              : https://contoso.sharepoint.com/sites/intra
  Title                : Sales
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Description,EnablePermissionsSync,HideNameInNavigation,ID,LogoUrl,ParentHubSiteId,Permissions,RequiresJoinApproval,SiteDesignId,SiteId,SiteUrl,Title
  All things sales,,,255a50b2-527f-4413-8485-57f4c17a24d1,https://contoso.sharepoint.com/sites/intra/SiteAssets/teapoint.png,/Guid(00000000-0000-0000-0000-000000000000)/,,,/Guid(184644fb-90ed-4841-a7ad-6930cf819060)/,255a50b2-527f-4413-8485-57f4c17a24d1,https://contoso.sharepoint.com/sites/intra,Sales
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo hubsite set --id "255a50b2-527f-4413-8485-57f4c17a24d1" --title "Sales" --description "All things sales"

  Date: 2/20/2023

  ## Sales (255a50b2-527f-4413-8485-57f4c17a24d1)

  Property | Value
  ---------|-------
  Description | All things sales
  EnablePermissionsSync | false
  HideNameInNavigation | false
  ID | 255a50b2-527f-4413-8485-57f4c17a24d1
  LogoUrl | https://contoso.sharepoint.com/sites/intra/SiteAssets/teapoint.png
  ParentHubSiteId | /Guid(00000000-0000-0000-0000-000000000000)/
  Permissions | null
  RequiresJoinApproval | false
  SiteDesignId | /Guid(00000000-0000-0000-0000-000000000000)/
  SiteId | 255a50b2-527f-4413-8485-57f4c17a24d1
  SiteUrl | https://contoso.sharepoint.com/sites/intra
  Title | Sales
  ```

  </TabItem>
</Tabs>

## More information

- SharePoint hub sites new in Microsoft 365: [https://techcommunity.microsoft.com/t5/SharePoint-Blog/SharePoint-hub-sites-new-in-Office-365/ba-p/109547](https://techcommunity.microsoft.com/t5/SharePoint-Blog/SharePoint-hub-sites-new-in-Office-365/ba-p/109547)
