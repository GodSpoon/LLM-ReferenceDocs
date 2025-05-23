-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo list roleassignment remove

Removes a role assignment from list permissions

## Usage

```sh
m365 spo list roleassignment remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list is located.

`-i, --listId [listId]`
: ID of the list. Specify either `listId`, `listTitle`, or `listUrl` but not multiple.

`-t, --listTitle [listTitle]`
: Title of the list. Specify either `listId`, `listTitle`, or `listUrl` but not multiple.

`--listUrl [listUrl]`
: Relative URL of the list. Specify either `listId`, `listTitle`, or `listUrl` but not multiple.

`--principalId [principalId]`
: SharePoint ID of principal it may be either user id or group id you want to remove permissions. Specify either `principalId`, `upn`, `groupName`, `entraGroupId`, or `entraGroupName`.

`--upn [upn]`
: The upn/email of user. Specify either `principalId`, `upn`, `groupName`, `entraGroupId`, or `entraGroupName`.

`--groupName [groupName]`
: The group name of the SharePoint group. Specify either `principalId`, `upn`, `groupName`, `entraGroupId`, or `entraGroupName`.

`--entraGroupId [entraGroupId]`
: ID of the Microsoft Entra group. Specify either `principalId`, `upn`, `groupName`, `entraGroupId`, or `entraGroupName`.

`--entraGroupName [entraGroupName]`
: Display name of the Microsoft Entra group. Specify either `principalId`, `upn`, `groupName`, `entraGroupId`, or `entraGroupName`.

`-f, --force`
: Don't prompt for confirming removing the role assignment.
```

<Global />

## Examples

Remove roleassignment from list by title based on group name.

```sh
m365 spo list roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --listTitle "someList" --groupName "saleGroup"
```

Remove roleassignment from list by title based on principal Id.

```sh
m365 spo list roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --listTitle "Events" --principalId 2
```

Remove roleassignment from list by url based on principal Id.

```sh
m365 spo list roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --listUrl '/sites/contoso-sales/lists/Events' --principalId 2
```

Remove roleassignment from Microsoft Entra group specified by display name.

```sh
m365 spo list roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --listUrl '/sites/contoso-sales/lists/Events' --entraGroupName "Sales Team"
```

## Response

The command won't return a response on success.
