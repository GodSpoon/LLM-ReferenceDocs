-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo file version clear

Removes all version history of a specified file

## Usage

```sh
m365 spo file version clear [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the file is located.

`--fileUrl [fileUrl]`
: The server- or site-relative decoded URL of the file. Specify either `fileUrl` or `fileId` but not both.

`-i, --fileId [fileId]`
: The UniqueId (GUID) of the file. Specify either `fileUrl` or `fileId` but not both.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Removes all file version history in a specific site based on fileId and prompts for confirmation.

```sh
m365 spo file version clear --webUrl https://contoso.sharepoint.com --fileId 'b2307a39-e878-458b-bc90-03bc578531d6'
```

Removes all file version history in a specific site based on fileUrl and prompts for confirmation.

```sh
m365 spo file version clear --webUrl https://contoso.sharepoint.com --fileUrl '/Shared Documents/Document.docx'
```

Removes all file version history in a specific site based on fileId without prompting for confirmation.

```sh
m365 spo file version clear --webUrl https://contoso.sharepoint.com --fileId 'b2307a39-e878-458b-bc90-03bc578531d6' --force
```

Removes all file version history in a specific site based on fileUrl without prompting for confirmation.

```sh
m365 spo file version clear --webUrl https://contoso.sharepoint.com --fileUrl '/Shared Documents/Document.docx' --force
```

## Response

The command won't return a response on success.
