-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo folder roleassignment add

Adds a role assignment from the specified folder.

## Usage

```sh
m365 spo folder roleassignment add [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the folder is located.

`--folderUrl <folderUrl>`
: The server- or site-relative decoded URL of the folder.

`--principalId [principalId]`
: The SharePoint principal id. It may be either an user id or group id for which the role assignment will be addd. Specify either `upn`, `groupName`, `principalId`, `entraGroupId` or `entraGroupName` but not multiple.

`--upn [upn]`
: The upn/email of the user. Specify either `upn`, `groupName`, `principalId`, `entraGroupId` or `entraGroupName` but not multiple.

`--groupName [groupName]`
: The SharePoint group name. Specify either `upn`, `groupName`, `principalId`, `entraGroupId` or `entraGroupName` but not multiple.

`--entraGroupId [entraGroupId]`
: ID of the Microsoft Entra group to add. Specify either `upn`, `groupName`, `principalId`, `entraGroupId` or `entraGroupName` but not multiple.

`--entraGroupName [entraGroupName]`
: Display name of the Microsoft Entra group to add. Specify either `upn`, `groupName`, `principalId`, `entraGroupId` or `entraGroupName` but not multiple.

`--roleDefinitionId [roleDefinitionId]`
: ID of the role definition. Specify either `roleDefinitionId` or `roleDefinitionName` but not both.

`--roleDefinitionName [roleDefinitionName]`
: The name of the role definition. E.g. 'Contribute', 'Read'. Specify either `roleDefinitionId` or `roleDefinitionName` but not both.
```

<Global />

## Examples

Add the role assignment to the specified folder based on the group name and role definition name.

```sh
m365 spo folder roleassignment add --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --folderUrl  "/Shared Documents/FolderPermission" --groupName "saleGroup" --roleDefinitionName "Edit"
```

Add the role assignment to the specified folder based on the principal Id and role definition id.

```sh
m365 spo folder roleassignment add --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --folderUrl "/Shared Documents/FolderPermission" --principalId 2 --roleDefinitionId 1073741827 
```

Add the role assignment to the specified folder based on the upn and role definition name.

```sh
m365 spo folder roleassignment add --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --folderUrl "/Shared Documents/FolderPermission" --upn "test@contoso.onmicrosoft.com" --roleDefinitionName "Edit"
```

Add the role assignment to the root folder based on the upn and role definition name.

```sh
m365 spo folder roleassignment add --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --folderUrl "/Shared Documents" --upn "test@contoso.onmicrosoft.com" --roleDefinitionName "Edit"
```

Add the role assignment to the specified folder based on the Entra Group Id and role definition id.

```sh
m365 spo folder roleassignment add --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --folderUrl "/Shared Documents/FolderPermission" --entraGroupId "27ae47f1-48f1-46f3-980b-d3c1470e398d" --roleDefinitionId 1073741827 
```

## Response

The command won't return a response on success.
