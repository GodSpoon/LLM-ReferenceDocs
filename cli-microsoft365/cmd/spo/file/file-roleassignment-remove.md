-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo file roleassignment remove

Removes a role assignment from a file.

## Usage

```sh
m365 spo file roleassignment remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the file is located.

`--fileUrl [fileUrl]`
: The server- or site-relative decoded URL of the file. Specify either `fileUrl` or `fileId` but not both.

`-i, --fileId [fileId]`
: The UniqueId (GUID) of the file. Specify either `fileUrl` or `fileId` but not both.

`--principalId [principalId]`
: The SharePoint Id of the principal. It may be either a user id or group id. Specify either `upn`, `groupName`, `entraGroupId`, `entraGroupName`, or `principalId` but not multiple.

`--upn [upn]`
: The upn/email of the user. Specify either `upn`, `groupName`, `entraGroupId`, `entraGroupName`, or `principalId` but not multiple.

`--groupName [groupName]`
: The group name of the SharePoint group Specify either `upn`, `groupName`, `entraGroupId`, `entraGroupName`, or `principalId` but not multiple. This option is only used for SharePoint Online groups.

`--entraGroupId [entraGroupId]`
: ID of the Microsoft Entra group to remove. Specify either `upn`, `groupName`, `entraGroupId`, `entraGroupName`, or `principalId` but not multiple.

`--entraGroupName [entraGroupName]`
: Display name of the Microsoft Entra group to remove. Specify either `upn`, `groupName`, `entraGroupId`, `entraGroupName`, or `principalId` but not multiple.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Remove a role assignment by principal id from a file by id.

```sh
m365 spo file roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --fileId "b2307a39-e878-458b-bc90-03bc578531d6" --principalId 2
```

Remove a role assignment by upn from a file by url.

```sh
m365 spo file roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --fileUrl "/sites/contoso-sales/documents/Test1.docx" --upn "user1@contoso.onmicrosoft.com"
```

Remove a role assignment by group name from a file by id.

```sh
m365 spo file roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --fileId "b2307a39-e878-458b-bc90-03bc578531d6" --groupName "saleGroup"
```

Remove a role assignment by entra group id from a file by id without prompt

```sh
m365 spo file roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --fileId "b2307a39-e878-458b-bc90-03bc578531d6" --entraGroupId 3c97e01e-978d-417b-a196-b6a3e37fa873 --force
```

Remove a role assignment by entra group name from a file by id.

```sh
m365 spo file roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --fileId "b2307a39-e878-458b-bc90-03bc578531d6" --entraGroupName "Marketing Members"
```

## Response

The command won't return a response on success.
