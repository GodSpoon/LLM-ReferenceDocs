-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo listitem attachment set

Updates an attachment from a list item

## Usage

```sh
m365 spo listitem attachment set [options]
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

`-p, --filePath <filePath>`
: Local path used for updating the attachment contents.

`-n, --fileName <fileName>`
: Name of the file to update.
```

<Global />

## Examples

Update an attachment from a list item by using list title

```sh
m365 spo listitem attachment set --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Demo List" --listItemId 147 --fileName "File1.jpg" --filePath "C:/Reports/File2.jpg"
```

Update an attachment from a list item by using list URL

```sh
m365 spo listitem attachment set --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl "/sites/project-x/Lists/DemoList" --listItemId 147 --fileName "File1.jpg" --filePath "C:/Reports/File2.jpg"
```

## Response

The command won't return a response on success.
