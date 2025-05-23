-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo folder roleinheritance reset

Restores the role inheritance of a folder.

## Usage

```sh
m365 spo folder roleinheritance reset [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the folder is located.

`--folderUrl <folderUrl>`
: The server- or site-relative decoded URL of the folder.

`-f, --force`
: Don't prompt for confirmation to reset role inheritance of the folder.
```

<Global />

## Examples

Reset inheritance of folder with a specific site-relative URL.

```sh
m365 spo folder roleinheritance reset --webUrl "https://contoso.sharepoint.com/sites/project-x" --folderUrl "Shared Documents/TestFolder"
```

Reset inheritance of folder with a specific server-relative URL. It will **not** prompt for confirmation before resetting.

```sh
m365 spo folder roleinheritance reset --webUrl "https://contoso.sharepoint.com/sites/project-x" --folderUrl "/sites/project-x/Shared Documents/TestFolder" --force
```

Reset inheritance of the specified root folder for the library with a specific server-relative URL. It will **not** prompt for confirmation before resetting.

```sh
m365 spo folder roleinheritance reset --webUrl "https://contoso.sharepoint.com/sites/project-x" --folderUrl "/sites/project-x/Shared Documents" --force
```

## Response

The command won't return a response on success.
