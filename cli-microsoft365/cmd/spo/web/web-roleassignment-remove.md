-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo web roleassignment remove

Removes a role assignment from web permissions.

## Usage

```sh
m365 spo web roleassignment remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site.

`--principalId [principalId]`
: SharePoint ID of principal it may be either user id or group id we want to add permissions to. Specify either `principalId`, `upn`, `groupName`, `entraGroupId` or `entraGroupName` but not multiple.

`--upn [upn]`
: The upn/email of user to assign role to. Specify either `principalId`, `upn`, `groupName`, `entraGroupId` or `entraGroupName` but not multiple.

`--groupName [groupName]`
: The group name of the SharePoint group. Use this option exclusively for SharePoint Online groups. Specify either `principalId`, `upn`, `groupName`, `entraGroupId` or `entraGroupName` but not multiple.

`--entraGroupId [entraGroupId]`
: ID of the Microsoft Entra group to remove. Specify either `principalId`, `upn`, `groupName`, `entraGroupId` or `entraGroupName` but not multiple.

`--entraGroupName [entraGroupName]`
: Display name of the Microsoft Entra group to remove. Specify either `principalId`, `upn`, `groupName`, `entraGroupId` or `entraGroupName` but not multiple.

`-f, --force`
: Don't prompt for confirming removing the roleassignment.
```

<Global />

## Examples

Remove roleassignment from web based on group name

```sh
m365 spo web roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales"  --groupName "saleGroup"
```

Remove roleassignment from web based on principal Id

```sh
m365 spo web roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales"  --principalId 2
```

Remove roleassignment from web based on upn

```sh
m365 spo web roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales"  --upn "someaccount@tenant.onmicrosoft.com"
```

Remove roleassignment from web based on principal Id without prompting for confirmation

```sh
m365 spo web roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales"  --principalId 2 --force
```

Remove roleassignment from web based on Entra Group Id and don't prompt for confirmation

```sh
m365 spo web roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales"  --entraGroupId "27ae47f1-48f1-46f3-980b-d3c1470e398d" --force
```

## Response

The command won't return a response on success.
