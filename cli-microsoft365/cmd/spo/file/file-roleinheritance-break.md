-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo file roleinheritance break

Breaks inheritance of a file. Keeping existing permissions is the default behavior.

## Usage

```sh
m365 spo file roleinheritance break [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the file is located.

`--fileUrl [fileUrl]`
: The server- or site-relative decoded URL of the file. Specify either `fileUrl` or `fileId` but not both.

`-i, --fileId [fileId]`
: The UniqueId (GUID) of the file. Specify either `fileUrl` or `fileId` but not both.

`-c, --clearExistingPermissions`
: Clear all existing permissions from the file.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Break the inheritance of a file with a specific id (UniqueId).

```sh
m365 spo file roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --fileId "b2307a39-e878-458b-bc90-03bc578531d6"
```

Break the inheritance of a file with a specific id (UniqueId) and clear all existing permissions.

```sh
m365 spo file roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --fileId "b2307a39-e878-458b-bc90-03bc578531d6" --clearExistingPermissions
```

Break the inheritance of a file with a specific server-relative URL.

```sh
m365 spo file roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --fileUrl "/sites/project-x/documents/Test1.docx"
```

Break the inheritance of a file with a specific server-relative URL and clear all existing permissions.

```sh
m365 spo file roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --fileUrl "/sites/project-x/documents/Test1.docx" --clearExistingPermissions
```

## Response

The command won't return a response on success.
