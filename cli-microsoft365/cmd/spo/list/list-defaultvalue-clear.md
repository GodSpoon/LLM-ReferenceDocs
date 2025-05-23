-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo list defaultvalue clear

Clears default column values for a specific document library

## Usage

```sh
m365 spo list defaultvalue clear [options]
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

`--fieldName [fieldName]`
: Internal name of the field to clear over the entire list. Specify either `fieldName` or `folderUrl`, but not both.

`--folderUrl [folderUrl]`
: Clear all fields of a specific folder by specifying a server- or site-relative URL. Specify either `fieldName` or `folderUrl`, but not both.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Remove all default column values from a library

```sh
m365 spo list defaultvalue clear --webUrl https://contoso.sharepoint.com/sites/Marketing --listTitle Logos
```

Clear a field from all folders of a library

```sh
m365 spo list defaultvalue clear --webUrl https://contoso.sharepoint.com/sites/Marketing --listTitle Logos --field Company
```

Clear all fields from a specific folder in a library

```sh
m365 spo list defaultvalue clear --webUrl https://contoso.sharepoint.com/sites/Marketing --listTitle Logos --folderUrl "/sites/Marketing/Logos/Contoso"
```

## Response

The command won't return a response on success.
