-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo list roleassignment add

Adds a role assignment to list permissions

## Usage

```sh
m365 spo list roleassignment add [options]
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
: SharePoint ID of principal it may be either user id or group id we want to add permissions to. Specify either `principalId`, `upn`, `groupName`, `entraGroupId`, or `entraGroupName`.

`--upn [upn]`
: The upn/email of user to assign role to. Specify either `principalId`, `upn`, `groupName`, `entraGroupId`, or `entraGroupName`.

`--entraGroupId [entraGroupId]`
: ID of the Microsoft Entra group to assign permissions to. Specify either `principalId`, `upn`, `groupName`, `entraGroupId`, or `entraGroupName`.

`--entraGroupName [entraGroupName]`
: Display name of the Microsoft Entra group to assign permissions to. Specify either `principalId`, `upn`, `groupName`, `entraGroupId`, or `entraGroupName`.

`--groupName [groupName]`
: The group name of the SharePoint group. Specify either `principalId`, `upn`, `groupName`, `entraGroupId`, or `entraGroupName`.

`--roleDefinitionId [roleDefinitionId]`
: ID of role definition. Specify either `roleDefinitionId` or `roleDefinitionName` but not both.

`--roleDefinitionName [roleDefinitionName]`
: The name of a role definition, like 'Contribute', 'Read', etc. Specify either `roleDefinitionId` or `roleDefinitionName` but not both.
```

<Global />

## Examples

Adds role assignment to a list by title located in a specific site for given principal id and role definition id.

```sh
m365 spo list roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList" --principalId 11 --roleDefinitionId 1073741829
```

Adds role assignment to list by id located in a specific site for given principal id and role definition id.

```sh
m365 spo list roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listId "0CD891EF-AFCE-4E55-B836-FCE03286CCCF" --principalId 11 --roleDefinitionId 1073741829
```

Adds role assignment to list by url located in a specific site for given principal id and role definition id.

```sh
m365 spo list roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listUrl "sites/documents" --principalId 11 --roleDefinitionId 1073741829
```

Adds role assignment to list by title located in a specific site for given upn and role definition id.

```sh
m365 spo list roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList" --upn "someaccount@tenant.onmicrosoft.com" --roleDefinitionId 1073741829
```

Adds role assignment to list by title located in a specific site for given group and role definition id.

```sh
m365 spo list roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList" --groupName "someGroup" --roleDefinitionId 1073741829
```

Adds role assignment to list by title located in a specific site for given principal id and role definition name.

```sh
m365 spo list roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList" --principalId 11 --roleDefinitionName "Full Control"
```

Adds role assignment to list for a Microsoft Entra group specified by display name.

```sh
m365 spo list roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList" --entraGroupName "Marketing" --roleDefinitionName "Full Control"
```

## Response

The command won't return a response on success.
