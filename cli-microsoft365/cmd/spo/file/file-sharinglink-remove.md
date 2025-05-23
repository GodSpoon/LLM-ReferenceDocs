-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo file sharinglink remove

Removes a specific sharing link of a file

## Usage

```sh
m365 spo file sharinglink remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the file is located.

`--fileUrl [fileUrl]`
: The server- or site-relative decoded URL of the file. Specify either `fileUrl` or `fileId` but not both.

`--fileId [fileId]`
: The UniqueId (GUID) of the file. Specify either `fileUrl` or `fileId` but not both.

`-i, --id <id>`
: The ID of the sharing link.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Removes a specific sharing link from a file by id without prompting for confirmation.

```sh
m365 spo file sharinglink remove --webUrl https://contoso.sharepoint.com/sites/demo --fileId daebb04b-a773-4baa-b1d1-3625418e3234 --id c391b57d-5783-4c53-9236-cefb5c6ef323 --force
```

Removes a specific sharing link from a file by a specified site-relative URL.

```sh
m365 spo file sharinglink remove --webUrl https://contoso.sharepoint.com/sites/demo --fileUrl 'Shared Documents/document.docx' --id c391b57d-5783-4c53-9236-cefb5c6ef323
```

Removes a specific sharing link from a file by a specified server-relative URL.

```sh
m365 spo file sharinglink remove --webUrl https://contoso.sharepoint.com/sites/demo --fileUrl '/sites/demo/Shared Documents/document.docx' --id c391b57d-5783-4c53-9236-cefb5c6ef323
```

## Response

The command won't return a response on success.
