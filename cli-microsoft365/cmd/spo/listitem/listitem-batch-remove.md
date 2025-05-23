-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo listitem batch remove

Removes items from a list in batch

## Usage

```sh
m365 spo listitem batch remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the SharePoint site.

`-l, --listId [listId]`
: ID of the list. Specify either `listTitle`, `listId` or `listUrl`, but not multiple.

`-t, --listTitle [listTitle]`
: Title of the list. Specify either `listTitle`, `listId` or `listUrl`, but not multiple.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listTitle`, `listId` or `listUrl`, but not multiple.

`-p, --filePath [filePath]`
: The absolute or relative path to a flat CSV file containing the list items. Specify `filePath` or `ids`, but not both.

`-i, --ids [ids]`
: Comma separated list of list item IDs. Specify `filePath` or `ids`, but not both.

`-r, --recycle`
: Recycle the list items. Otherwise, they will be permanently deleted.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

A sample CSV can be found below. The first line of the CSV-file should contain the internal column name of the ID-column.

```csv
ID
123
234
345
```

## Examples

Remove a list of IDs from a list with a csv

```sh	
m365 spo listitem batch remove --filePath ./IDlist.csv --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Demo List"
```

Remove a list of IDs from a list by specifying the IDs

```sh
m365 spo listitem batch remove --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Demo List" --ids "123,234,345"
```

## Response

The command won't return a response on success.
