-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo file version restore

Restores a specific version of a specified file

## Usage

```sh
m365 spo file version restore [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the file is located.

`--label <label>`
: Label of version which will be restored.

`--fileUrl [fileUrl]`
: The server- or site-relative decoded URL of the file whose version will be restored. Specify either `fileUrl` or `fileId` but not both.

`-i, --fileId [fileId]`
: The UniqueId (GUID) of the file whose version will be restored. Specify either `fileUrl` or `fileId` but not both.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Restores a file version in a specific site based on fileId and prompts for confirmation.

```sh
m365 spo file version restore --webUrl https://contoso.sharepoint.com --label "1.0" --fileId 'b2307a39-e878-458b-bc90-03bc578531d6'
```

Restores a file version in a specific site based on fileUrl and prompts for confirmation.

```sh
m365 spo file version restore --webUrl https://contoso.sharepoint.com --label "1.0" --fileUrl '/Shared Documents/Document.docx'
```

Restores a file version in a specific site based on fileId without prompting for confirmation.

```sh
m365 spo file version restore --webUrl https://contoso.sharepoint.com --label "1.0" --fileId 'b2307a39-e878-458b-bc90-03bc578531d6' --force
```

Restores a file version in a specific site based on fileUrl without prompting for confirmation.

```sh
m365 spo file version restore --webUrl https://contoso.sharepoint.com --label "1.0" --fileUrl '/Shared Documents/Document.docx' --force
```

## Response

The command won't return a response on success.
