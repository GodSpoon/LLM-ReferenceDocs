-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo file checkout undo

Discards a checked out file

## Usage

```sh
m365 spo file checkout undo [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the file is located.

`--fileUrl [fileUrl]`
: The server- or site-relative decoded URL of the file to retrieve. Specify either `fileUrl` or `fileId` but not both.

`-i, --fileId [fileId]`
: The UniqueId (GUID) of the file to retrieve. Specify either `fileUrl` or `fileId` but not both.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Discards a checked-out file with a specific ID.

```sh
m365 spo file checkout undo --webUrl https://contoso.sharepoint.com/sites/project-x --fileId 'b2307a39-e878-458b-bc90-03bc578531d6'
```

Discards a checked-out file with a specific URL without prompting for confirmation.

```sh
m365 spo file checkout undo --webUrl https://contoso.sharepoint.com/sites/project-x --fileUrl '/sites/project-x/documents/Test1.docx' --force
```

## Response

The command won't return a response on success.
