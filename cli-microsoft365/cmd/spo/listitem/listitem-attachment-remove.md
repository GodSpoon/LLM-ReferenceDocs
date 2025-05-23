-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo listitem attachment remove

Removes an attachment from a list item

## Usage

```sh
m365 spo listitem attachment remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list item is located.

`--listId [listId]`
: ID of the list. Specify either `listTitle`, `listId` or `listUrl`.

`--listTitle [listTitle]`
: Title of the list. Specify either `listTitle`, `listId` or `listUrl`.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listTitle`, `listId` or `listUrl`.

`--listItemId <listItemId>`
: The ID of the list item.

`-n, --fileName <fileName>`
: Name of the file to remove.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Remove an attachment from a list item using list tile.

```sh
m365 spo listitem attachment remove --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Demo List" --listItemId 147 --fileName "File1.jpg"
```

Remove an attachment from a list item using list URL.

```sh
m365 spo listitem attachment remove --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl "/sites/project-x/Lists/DemoList" --listItemId 147 --fileName "File1.jpg"
```

## Response

The command won't return a response on success.
