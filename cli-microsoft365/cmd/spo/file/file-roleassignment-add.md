-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo file roleassignment add

Adds a role assignment to the specified file.

## Usage

```sh
m365 spo file roleassignment add [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the file is located.

`--fileUrl [fileUrl]`
: The server- or site-relative decoded URL of the file to retrieve. Specify either `fileUrl` or `fileId` but not both.

`-i, --fileId [fileId]`
: The UniqueId (GUID) of the file to retrieve. Specify either `fileUrl` or `fileId` but not both.

`--principalId [principalId]`
: The SharePoint Id of the principal. It may be either a user id or group id to add a role assignment for. Specify either `upn`, `groupName`, or `principalId` but not multiple.

`--upn [upn]`
: The upn/email of user to assign role to. Specify either `upn`, `groupName`, `entraGroupId`, `entraGroupName`, or `principalId` but not multiple.

`--groupName [groupName]`
: The group name of the SharePoint group Specify either `upn`, `groupName`, `entraGroupId`, `entraGroupName`, or `principalId` but not multiple. This option is only used for SharePoint Online groups.

`--entraGroupId [entraGroupId]`
: ID of the Microsoft Entra group to add. Specify either `upn`, `groupName`, `entraGroupId`, `entraGroupName`, or `principalId` but not multiple.

`--entraGroupName [entraGroupName]`
: Display name of the Microsoft Entra group to add. Specify either `upn`, `groupName`, `entraGroupId`, `entraGroupName`, or `principalId` but not multiple.

`--roleDefinitionId [roleDefinitionId]`
: ID of role definition. Specify either `roleDefinitionId` or `roleDefinitionName` but not both.

`--roleDefinitionName [roleDefinitionName]`
: The name of a role definition, like 'Contribute', 'Read', etc. Specify either `roleDefinitionId` or `roleDefinitionName` but not both.
```

<Global />

## Examples

Adds a role assignment to a file with a specified id. It will use a principal id and a specific role definition id.

```sh
m365 spo file roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --fileId "b2307a39-e878-458b-bc90-03bc578531d6" --principalId 11 --roleDefinitionId 1073741829
```

Adds a role assignment to a file with a specified site-relative URL for a specific upn and a role definition name.

```sh
m365 spo file roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --fileUrl "Shared Documents/Test1.docx" --upn "testuser@tenant.onmicrosoft.com" --roleDefinitionName "Full Control"
```

Adds a role assignment to a file with a specified server-relative URL the for a specific SharePoint Online group  and a role definition name.

```sh
m365 spo file roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --fileUrl "/sites/project-x/documents/Test1.docx" --groupName "Sales Group" --roleDefinitionName "Read"
```

Adds a role assignment to a file with a specified site-relative URL for a specific Entra Group Id and a role definition name.

```sh
m365 spo file roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --fileUrl "Shared Documents/Test1.docx" --entraGroupId 3c97e01e-978d-417b-a196-b6a3e37fa873 --roleDefinitionName "Full Control"
```

Adds a role assignment to a file with a specified site-relative URL for a specific Entra Group Name and a role definition name.

```sh
m365 spo file roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --fileUrl "Shared Documents/Test1.docx" --entraGroupName "Marketing Memebers" --roleDefinitionName "Full Control"
```
## Response

The command won't return a response on success.
