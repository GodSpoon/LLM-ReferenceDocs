-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo file version remove

Removes a specific version of a specified file

## Usage

```sh
m365 spo file version remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the file is located.

`--label <label>`
: Label of version which will be removed.

`--fileUrl [fileUrl]`
: The server- or site-relative decoded URL of the file to retrieve. Specify either `fileUrl` or `fileId` but not both.

`-i, --fileId [fileId]`
: The UniqueId (GUID) of the file to retrieve. Specify either `fileUrl` or `fileId` but not both.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Removes a file version in a specific site based on fileId and prompts for confirmation.

```sh
m365 spo file version remove --webUrl https://contoso.sharepoint.com --label "1.0" --fileId 'b2307a39-e878-458b-bc90-03bc578531d6'
```

Removes a file version in a specific site based on fileUrl and prompts for confirmation.

```sh
m365 spo file version remove --webUrl https://contoso.sharepoint.com --label "1.0" --fileUrl '/Shared Documents/Document.docx'
```

Removes a file version in a specific site based on fileId without prompting for confirmation.

```sh
m365 spo file version remove --webUrl https://contoso.sharepoint.com --label "1.0" --fileId 'b2307a39-e878-458b-bc90-03bc578531d6' --force
```

Removes a file version in a specific site based on fileUrl without prompting for confirmation.

```sh
m365 spo file version remove --webUrl https://contoso.sharepoint.com --label "1.0" --fileUrl '/Shared Documents/Document.docx' --force
```

## Response

The command won't return a response on success.
