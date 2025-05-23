-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo folder roleinheritance break

Breaks the role inheritance of a folder.

## Usage

```sh
m365 spo folder roleinheritance break [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the folder is located.

`--folderUrl <folderUrl>`
: The server- or site-relative decoded URL of the folder.

`-c, --clearExistingPermissions`
: Clear all existing permissions from the folder.

`-f, --force`
: Don't prompt for confirmation to breaking role inheritance of the folder.
```

<Global />

## Examples

Break the inheritance of a folder with a specified site-relative URL.

```sh
m365 spo folder roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --folderUrl "Shared Documents/TestFolder"
```

Break the inheritance of a folder with a specified server-relative URL. It will clear the existing permissions of the folder. It will **not** prompt for confirmation before breaking the inheritance.

```sh
m365 spo folder roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --folderUrl "/sites/project-x/Shared Documents/TestFolder" --clearExistingPermissions --force
```

Break the inheritance of the specified root folder for the library with a specified server-relative URL. It will clear the existing permissions of the root folder. It will **not** prompt for confirmation before breaking the inheritance.

```sh
m365 spo folder roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --folderUrl "/sites/project-x/Shared Documents" --clearExistingPermissions --force
```

## Response

The command won't return a response on success.
