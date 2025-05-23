-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo list defaultvalue remove

Removes a specific default column value for a specific document library

## Usage

```sh
m365 spo list defaultvalue remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list is located.

`-i, --listId [listId]`
: ID of the list. Specify either `listTitle`, `listId`, or `listUrl`.

`-t, --listTitle [listTitle]`
: Title of the list. Specify either `listTitle`, `listId`, or `listUrl`.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listTitle`, `listId`, or `listUrl`.

`--fieldName <fieldName>`
: Internal name of the field.

`--folderUrl [folderUrl]`
: Server- or site-relative URL of a specific folder to remove the field from. By default, the root folder of the list is used.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Remove a default column value from the root folder of the list

```sh
m365 spo list defaultvalue remove --webUrl https://contoso.sharepoint.com/sites/Marketing --listTitle Logos --fieldName Company
```

Remove a column default value from a specific folder using web-relative URL

```sh
m365 spo list defaultvalue remove --webUrl https://contoso.sharepoint.com/sites/Marketing --listUrl '/Logos' --fieldName Company --folderUrl '/Logos/Branding'
```

Remove a column default value from a specific folder by server relative URL

```sh
m365 spo list defaultvalue remove --webUrl https://contoso.sharepoint.com/sites/Marketing --listId fc6d514f-e7da-47d4-b48b-f72e2fb9c82a --field Company --folderUrl '/sites/Marketing/Logos/Branding'
```

## Response

The command won't return a response on success.
