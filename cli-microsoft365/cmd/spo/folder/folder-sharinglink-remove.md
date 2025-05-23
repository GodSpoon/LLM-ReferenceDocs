-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo folder sharinglink remove

Removes a specific sharing link of a folder

## Usage

```sh
m365 spo folder sharinglink remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the folder is located.

`--folderUrl [folderUrl]`
: The server- or site-relative decoded URL of the folder. Specify either `folderUrl` or `folderId` but not both.

`--folderId [folderId]`
: The UniqueId (GUID) of the folder. Specify either `folderUrl` or `folderId` but not both.

`-i, --id <id>`
: The ID of the sharing link.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Removes a specific sharing link from a folder by id without prompting for confirmation.

```sh
m365 spo folder sharinglink remove --webUrl https://contoso.sharepoint.com/sites/demo --folderId daebb04b-a773-4baa-b1d1-3625418e3234 --id c391b57d-5783-4c53-9236-cefb5c6ef323 --force
```

Removes a specific sharing link from a folder by url with prompting for confirmation.

```sh
m365 spo folder sharinglink remove --webUrl https://contoso.sharepoint.com/sites/demo --folderUrl /sites/demo/shared%20documents/Folder --id c391b57d-5783-4c53-9236-cefb5c6ef323
```

## Response

The command won't return a response on success.
