-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo folder roleassignment remove

Removes a role assignment from the specified folder.

## Usage

```sh
m365 spo folder roleassignment remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the folder is located.

`--folderUrl <folderUrl>`
: The server- or site-relative decoded URL of the folder.

`--principalId [principalId]`
: The SharePoint principal id. It may be either an user id or group id for which the role assignment will be removed. Specify either `upn`, `groupName`, `principalId`, `entraGroupId` or `entraGroupName` but not multiple.

`--upn [upn]`
: The upn/email of the user. Specify either `upn`, `groupName`, `principalId`, `entraGroupId` or `entraGroupName` but not multiple.

`--groupName [groupName]`
: The SharePoint group name. Specify either `upn`, `groupName`, `principalId`, `entraGroupId` or `entraGroupName` but not multiple.

`--entraGroupId [entraGroupId]`
: ID of the Microsoft Entra group to remove. Specify either `upn`, `groupName`, `principalId`, `entraGroupId` or `entraGroupName` but not multiple.

`--entraGroupName [entraGroupName]`
: Display name of the Microsoft Entra group to remove. Specify either `upn`, `groupName`, `principalId`, `entraGroupId` or `entraGroupName` but not multiple.

`-f, --force`
: Don't prompt for confirmation when removing the role assignment.
```

<Global />

## Examples

Remove roleassignment from folder based on group name.

```sh
m365 spo folder roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --folderUrl  "/Shared Documents/FolderPermission" --groupName "saleGroup"
```

Remove the role assignment from the specified folder based on the principal id.

```sh
m365 spo folder roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --folderUrl "/Shared Documents/FolderPermission" --principalId 2
```

Remove the role assignment from the specified folder based on the principal id without prompting for removal confirmation.

```sh
m365 spo folder roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --folderUrl "/Shared Documents/FolderPermission" --principalId 2 --force
```

Remove the role assignment from the specified folder based on the upn.

```sh
m365 spo folder roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --folderUrl "/Shared Documents/FolderPermission" --upn "test@contoso.onmicrosoft.com"
```

Remove the role assignment from the specified folder based on the Entra group id.

```sh
m365 spo folder roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --folderUrl "/Shared Documents/FolderPermission" --entraGroupId "27ae47f1-48f1-46f3-980b-d3c1470e398d"
```

## Response

The command won't return a response on success.
