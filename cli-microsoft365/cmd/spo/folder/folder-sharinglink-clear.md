-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo folder sharinglink clear

Removes sharing links of a folder

## Usage

```sh
m365 spo folder sharinglink clear [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the folder is located.

`--folderUrl [folderUrl]`
: The server- or site-relative decoded URL of the folder. Specify either `folderUrl` or `folderId` but not both.

`--folderId [folderId]`
: The Unique ID (GUID) of the folder. Specify either `folderUrl` or `folderId` but not both.

`-s, --scope [scope]`
: Scope of the sharing link. Possible options are: `anonymous`, `users` or `organization`. If not specified, all links will be removed.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Removes all sharing links from a folder specified by id without prompting for confirmation.

```sh
m365 spo folder sharinglink clear --webUrl https://contoso.sharepoint.com/sites/demo --folderId daebb04b-a773-4baa-b1d1-3625418e3234 --force
```

Removes sharing links of type anonymous from a folder specified by url with prompting for confirmation.

```sh
m365 spo folder sharinglink clear --webUrl https://contoso.sharepoint.com/sites/demo --folderUrl '/sites/demo/Shared Documents/folder1' --scope anonymous
```

## Response

The command won't return a response on success.
