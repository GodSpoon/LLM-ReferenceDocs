-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo listitem roleassignment add

Adds a role assignment to a listitem.

## Usage

```sh
m365 spo listitem roleassignment add [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list item is located

`--listId [listId]`
: ID of the list. Specify either `listId`, `listTitle` or `listUrl` but not multiple.

`--listTitle [listTitle]`
: Title of the list. Specify either `listId`, `listTitle` or `listUrl` but not multiple.

`--listUrl [listUrl]`
: Relative URL of the list. Specify either `listId`, `listTitle` or `listUrl` but not multiple.

`--listItemId <listItemId>`
: Id of the list item to assign the role to.

`--principalId [principalId]`
: The SharePoint Id of the principal. It may be either a user id or group id to add a role assignment for. Specify either `principalId`, `upn`, `groupName`, `entraGroupId`, or `entraGroupName`.

`--upn [upn]`
: The upn/email of user to assign role to. Specify either `principalId`, `upn`, `groupName`, `entraGroupId`, or `entraGroupName`.

`--groupName [groupName]`
: The group name of the SharePoint group. Use this option exclusively for SharePoint Online groups. Specify either `principalId`, `upn`, `groupName`, `entraGroupId`, or `entraGroupName`.

`--entraGroupId [entraGroupId]`
: ID of the Microsoft Entra group to add. Specify either `principalId`, `upn`, `groupName`, `entraGroupId`, or `entraGroupName`.

`--entraGroupName [entraGroupName]`
: Display name of the Microsoft Entra group to add. Specify either `principalId`, `upn`, `groupName`, `entraGroupId`, or `entraGroupName`.

`--roleDefinitionId [roleDefinitionId]`
: ID of role definition. Specify either `roleDefinitionId` or `roleDefinitionName` but not both.

`--roleDefinitionName [roleDefinitionName]`
: The name of a role definition, like 'Contribute', 'Read', etc. Specify either `roleDefinitionId` or `roleDefinitionName` but not both.
```

<Global />

## Examples

Add role assignment to specified list item in specified list located in specified site for specified principal id and specified role definition id.

```sh
m365 spo listitem roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList" --listItemId 1 --principalId 11 --roleDefinitionId 1073741829
```

Add role assignment to specified list item in specified list located in specified site for specified principal id and specified role definition id.

```sh
m365 spo listitem roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listId "0CD891EF-AFCE-4E55-B836-FCE03286CCCF" --listItemId 1 --principalId 11 --roleDefinitionId 1073741829
```

Add role assignment to specified list item in specified list located in specified site for specified principal id and specified role definition id.

```sh
m365 spo listitem roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listUrl "sites/documents" --listItemId 1 --principalId 11 --roleDefinitionId 1073741829
```

Add role assignment to specified list item in specified list located in specified site for specified upn and specified role definition id.

```sh
m365 spo listitem roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList" --listItemId 1 --upn "someaccount@tenant.onmicrosoft.com" --roleDefinitionId 1073741829
```

Add role assignment to specified list item in specified list located in specified site for specified group and specified role definition id.

```sh
m365 spo listitem roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList" --listItemId 1 --groupName "someGroup" --roleDefinitionId 1073741829
```

Add role assignment to specified list item in specified list located in specified site for specified principal id and specified role definition name.

```sh
m365 spo listitem roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList" --listItemId 1 --principalId 11 --roleDefinitionName "Full Control"
```

Add role assignment to specified list item in specified list located in specified site for specified Entra group id and specified role definition name.

```sh
m365 spo listitem roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList" --listItemId 1 --entraGroupId "27ae47f1-48f1-46f3-980b-d3c1470e398d" --roleDefinitionName "Full Control"
```

## Response

The command won't return a response on success.
