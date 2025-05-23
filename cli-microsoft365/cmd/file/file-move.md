-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# file move

Moves a file to another location using the Microsoft Graph

## Usage

```sh
m365 file move [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the file is located.

`-s, --sourceUrl <sourceUrl>`
: Server-relative or absolute URL of the file.

`-t, --targetUrl <targetUrl>`
: Server-relative or absolute URL of the location.

`--newName [newName]`
: New name of the destination file.

`--nameConflictBehavior [nameConflictBehavior]`
: Behavior when a document with the same name is already present at the destination. Possible values: `fail`, `replace`, `rename`. Default is `fail`.
```

<Global />

## Remarks

- If the source and target locations are within the same document library or drive, the command will utilize the Move DriveItem API, preserving the version history of the file.
- If the source and target locations are in different document libraries or drives, the command will use a copy-and-delete combination to move the file. Please note that in this case, version history will not be retained.

## Examples

Move a file by server-relative URL to a folder in the same document library

```sh
m365 file move --webUrl "https://contoso.sharepoint.com/sites/project" --sourceUrl "/sites/project/Shared Documents/Document.pdf" --targetUrl "/sites/project/Shared Documents/NewFolder"
```

Move a file by server-relative URL to a document library in another site collection with server relative URL

```sh
m365 file move --webUrl "https://contoso.sharepoint.com/sites/project" --sourceUrl "/sites/project/Shared Documents/Document.pdf" --targetUrl "/sites/IT/Shared Documents"
```

Move a file by absolute URL to a document library in another site collection with absolute URL

```sh
m365 file move --webUrl "https://contoso.sharepoint.com" --sourceUrl "https://contoso.sharepoint.com/Shared Documents/Document.pdf" --targetUrl "https://contoso.sharepoint.com/sites/IT/Shared Documents"
```

Move a file to a document library in another site collection and rename the file

```sh
m365 file move --webUrl "https://contoso.sharepoint.com" --sourceUrl "/Shared Documents/Document.pdf" --targetUrl "/sites/IT/Shared Documents" --newName "newName"
```

Move a file to a document library in another site collection and rename the file if a file with the same name already exists.

```sh
m365 file move --webUrl "https://contoso.sharepoint.com" --sourceUrl "/Shared Documents/Document.pdf" --targetUrl "/sites/IT/Shared Documents" --nameConflictBehavior rename
```

Move a file to Onedrive for business 

```sh
m365 file move --webUrl "https://contoso.sharepoint.com" --sourceUrl "/Shared Documents/Document.pdf" --targetUrl "https://contoso-my.sharepoint.com/personal/john_contoso_onmicrosoft_com/documents"
```

## Response

The command won't return a response on success.
