-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo listitem isrecord

Checks if the specified list item is a record

## Usage

```sh
m365 spo listitem isrecord [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the list is located

`-i, --id <id>`
: The ID of the list item to check if it is a record

`-l, --listId [listId]`
: ID of the list where the item should be checked. Specify either `listTitle`, `listId` or `listUrl`

`-t, --listTitle [listTitle]`
: Title of the list where the item should be checked. Specify either `listTitle`, `listId` or `listUrl`

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listTitle`, `listId` or `listUrl`
```

<Global />

## Examples

Check whether the document with id _1_ in list with title _Documents_ located in site _https://contoso.sharepoint.com/sites/project-x_ is a record

```sh
m365 spo listitem isrecord --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'Documents' --id 1
```

Check whether the document with id _1_ in list with id _0cd891ef-afce-4e55-b836-fce03286cccf_ located in site _https://contoso.sharepoint.com/sites/project-x_ is a record

```sh
m365 spo listitem isrecord --webUrl https://contoso.sharepoint.com/sites/project-x --listId 0cd891ef-afce-4e55-b836-fce03286cccf --id 1
```

Check whether a document with a specific id in a list retrieved by server-relative URL in a specific site is a record

```sh
m365 spo listitem isrecord --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl /sites/project-x/documents --id 1
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  false
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  false
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  false
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  false
  ```

  </TabItem>
</Tabs>
