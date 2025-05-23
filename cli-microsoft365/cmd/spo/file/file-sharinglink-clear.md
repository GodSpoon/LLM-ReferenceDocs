-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo file sharinglink clear

Removes sharing links of a file

## Usage

```sh
m365 spo file sharinglink clear [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the file is located.

`--fileUrl [fileUrl]`
: The server- or site-relative decoded URL of the file. Specify either `fileUrl` or `fileId` but not both.

`--fileId [fileId]`
: The UniqueId (GUID) of the file. Specify either `fileUrl` or `fileId` but not both.

`-s, --scope [scope]`
: Scope of the sharing link. Possible options are: `anonymous`, `users` or `organization`. If not specified, all links will be removed.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Removes all sharing links from a file specified by id without prompting for confirmation.

```sh
m365 spo file sharinglink clear --webUrl https://contoso.sharepoint.com/sites/demo --fileId daebb04b-a773-4baa-b1d1-3625418e3234 --force
```

Removes sharing links of type anonymous from a file specified by url with prompting for confirmation.

```sh
m365 spo file sharinglink clear --webUrl https://contoso.sharepoint.com/sites/demo --fileUrl '/sites/demo/Shared Documents/document.docx' --scope anonymous
```

## Response

The command won't return a response on success.
