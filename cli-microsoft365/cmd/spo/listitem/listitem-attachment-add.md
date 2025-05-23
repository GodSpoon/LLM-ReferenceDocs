-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo listitem attachment add

Adds an attachment to a list item

## Usage

```sh
m365 spo listitem attachment add [options]
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
: Local path to the file that will be added as an attachment to the list item.

`-n, --fileName [fileName]`
: Name for the file. If no name is provided, the name from `filePath` will be utilized.
```

<Global />

## Examples

Add a new attachment to a list item from a local file by using list title

```sh
m365 spo listitem attachment add --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "DemoList" --listItemId 147 --filePath "C:/Reports/File1.jpg"
```

Add a new attachment to a list item from a local file by using list URL with a different filename

```sh
m365 spo listitem attachment add --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl "/sites/project-x/Lists/DemoList" --listItemId 147 --filePath "C:/Reports/File1.jpg" --fileName "File2"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "FileName": "File1.jpg",
      "FileNameAsPath": {
        "DecodedUrl": "File1.jpg"
      },
      "ServerRelativePath": {
        "DecodedUrl": "/Lists/DemoList/Attachments/147/File1.jpg"
      },
      "ServerRelativeUrl": "/Lists/Test/Attachments/147/File1.jpg"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  FileName          : File1.jpg
  FileNameAsPath    : {"DecodedUrl":"File1jpg"}
  ServerRelativePath: {"DecodedUrl":"/Lists/DemoList/Attachments/743/File1.jpg"}
  ServerRelativeUrl : /Lists/DemoList/Attachments/147/File1.jpg
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  FileName,ServerRelativeUrl
  File1.jpg,/Lists/DemoList/Attachments/147/File1.jpg
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo listitem attachment add --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "DemoList" --listItemId 147 --filePath "C:/Reports/File1.jpg"

  Date: 25/07/2023

  Property | Value
  ---------|-------
  FileName | File1.jpg
  ServerRelativeUrl | /Lists/DemoList/Attachments/147/File1.jpg
  ```

  </TabItem>
</Tabs>
