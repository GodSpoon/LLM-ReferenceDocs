-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo web roleassignment add

Adds a role assignment to web permissions.

## Usage

```sh
m365 spo web roleassignment add [options]
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
: ID of the Microsoft Entra group to add. Specify either `principalId`, `upn`, `groupName`, `entraGroupId` or `entraGroupName` but not multiple.

`--entraGroupName [entraGroupName]`
: Display name of the Microsoft Entra group to add. Specify either `principalId`, `upn`, `groupName`, `entraGroupId` or `entraGroupName` but not multiple.

`--roleDefinitionId [roleDefinitionId]`
: ID of role definition. Specify either `roleDefinitionId` or `roleDefinitionName` but not both.

`--roleDefinitionName [roleDefinitionName]`
: The name of a role definition, like 'Contribute', 'Read', etc. Specify either `roleDefinitionId` or `roleDefinitionName` but not both.
```

<Global />

## Examples

add role assignment to a site principal id _11_ and role definition id _1073741829_

```sh
m365 spo web roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --principalId 11 --roleDefinitionId 1073741829
```

add role assignment to a site for a upn and role definition id _1073741829_

```sh
m365 spo web roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --upn "someaccount@tenant.onmicrosoft.com" --roleDefinitionId 1073741829
```

add role assignment to a site for group _someGroup_ and role definition id _1073741829_

```sh
m365 spo web roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --groupName "someGroup" --roleDefinitionId 1073741829
```

add role assignment to a site for principal id _11_ and role definition name _Full Control_

```sh
m365 spo web roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --principalId 11 --roleDefinitionName "Full Control"
```

add role assignment using a Entra Group ID and a role definition 

```sh
m365 spo web roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --entraGroupId "27ae47f1-48f1-46f3-980b-d3c1470e398d" --roleDefinitionId 1073741829
```

## Response

The command won't return a response on success.
