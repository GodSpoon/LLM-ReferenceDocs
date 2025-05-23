-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo listitem attachment get

Gets an attachment from a list item

## Usage

```sh
m365 spo listitem attachment get [options]
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
: Name of the file to get.
```

<Global />

## Examples

Get an attachment from a list item by using list title.

```sh
m365 spo listitem attachment get --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Demo List" --listItemId 147 --fileName "File1.jpg"
```

Get an attachment from a list item by using list URL.

```sh
m365 spo listitem attachment get --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl "/sites/project-x/Lists/DemoList" --listItemId 147 --fileName "File1.jpg"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "FileName": "File1.jpg",
    "FileNameAsPath": {
      "DecodedUrl": "File1.jpg"
    },
    "ServerRelativePath": {
      "DecodedUrl": "/sites/project-x/Lists/DemoListAttachments/147/File1.jpg"
    },
    "ServerRelativeUrl": "/sites/project-x/Lists/DemoListAttachments/147/File1.jpg"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  FileName          : File1.jpg
  FileNameAsPath    : {"DecodedUrl":"File1.jpg"}
  ServerRelativePath: {"DecodedUrl":"/sites/project-x/Lists/DemoListAttachments/147/File1.jpg"}
  ServerRelativeUrl : /sites/project-x/Lists/DemoListAttachments/147/File1.jpg
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  FileName,ServerRelativeUrl
  File1.jpg,/sites/project-x/Lists/DemoListAttachments/147/File1.jpg
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo listitem attachment get --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "PnP PowerShell List" --listItemId "1" --fileName "File1.jpg"

  Date: 7/20/2023

  Property | Value
  ---------|-------
  FileName | File1.jpg
  ServerRelativeUrl | /sites/project-x/Lists/DemoListAttachments/147/File1.jpg
  ```

  </TabItem>
</Tabs>
