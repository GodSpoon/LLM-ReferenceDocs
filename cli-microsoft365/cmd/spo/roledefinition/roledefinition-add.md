-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo roledefinition add

Adds a new roledefinition to web

## Usage

```sh
m365 spo roledefinition add [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site to which role should be added.

`-n, --name <name>`
: role definition name.

`-d, --description [description]`
: role definition description.

`--rights [rights]`
: A case-sensitive string array that contain the permissions needed for the custom action. Allowed values `EmptyMask`, `ViewListItems`, `AddListItems`, `EditListItems`, `DeleteListItems`, `ApproveItems`, `OpenItems`, `ViewVersions`, `DeleteVersions`, `CancelCheckout`, `ManagePersonalViews`, `ManageLists`, `ViewFormPages`, `AnonymousSearchAccessList`, `Open`, `ViewPages`, `AddAndCustomizePages`, `ApplyThemeAndBorder`, `ApplyStyleSheets`, `ViewUsageData`, `CreateSSCSite`, `ManageSubwebs`, `CreateGroups`, `ManagePermissions`, `BrowseDirectories`, `BrowseUserInfo`, `AddDelPrivateWebParts`,`UpdatePersonalWebParts`, `ManageWeb`, `AnonymousSearchAccessWebLists`, `UseClientIntegration`, `UseRemoteAPIs`, `ManageAlerts`, `CreateAlerts`, `EditMyUserInfo`, `EnumeratePermissions`, `FullMask`. Default `EmptyMask`.
```

<Global />

## Remarks

The `--rights` option accepts **case-sensitive** values.

## Examples

Adds the role definition for the given site

```sh
m365 spo roledefinition add --webUrl https://contoso.sharepoint.com/sites/project-x --name test
```

Adds the role definition for the given site with description and rights

```sh
m365 spo roledefinition add --webUrl https://contoso.sharepoint.com/sites/project-x --name test --description "test description" --rights "ViewListItems,AddListItems,EditListItems,DeleteListItems"
```

## Response

The command won't return a response on success.
