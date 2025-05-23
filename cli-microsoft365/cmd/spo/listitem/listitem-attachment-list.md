-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo listitem attachment list

Gets the attachments associated to a list item

## Usage

```sh
m365 spo listitem attachment list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site from which the item should be retrieved.

`--listId [listId]`
: ID of the list where the item should be retrieved. Specify either `listTitle`, `listId` or `listUrl`.

`--listTitle [listTitle]`
: Title of the list where the item should be retrieved. Specify either `listTitle`, `listId` or `listUrl`.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listTitle`, `listId` or `listUrl`.

`--listItemId <listItemId>`
: ID of the list item.
```

<Global />

## Examples

Gets the attachments from list item with the specified listItemId in list with the specified title in the specified site.

```sh
m365 spo listitem attachment list --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Demo List" --listItemId 147
```

Gets the attachments from list item with the specified listItemId in list with the specified id in the specified site.

```sh
m365 spo listitem attachment list --webUrl https://contoso.sharepoint.com/sites/project-x --listId 0cd891ef-afce-4e55-b836-fce03286cccf --listItemId 147
```

Gets the attachments from a specific list item in a specific list obtained by server-relative URL in a specific site.

```sh
m365 spo listitem attachment list --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl /sites/project-x/Documents --listItemId 147
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "FileName": "DummyDocument.docx",
      "FileNameAsPath": {
        "DecodedUrl": "DummyDocument.docx"
      },
      "ServerRelativePath": {
        "DecodedUrl": "/Lists/Test/Attachments/236/DummyDocument.docx"
      },
      "ServerRelativeUrl": "/Lists/Test/Attachments/236/DummyDocument.docx"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  FileName            ServerRelativeUrl  
  ------------------  ----------------------------------------------
  DummyDocument.docx  /Lists/Test/Attachments/236/DummyDocument.docx
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  FileName,ServerRelativeUrl
  DummyDocument.docx,/Lists/Test/Attachments/236/DummyDocument.docx
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo listitem attachment list --webUrl "https://contoso.sharepoint.com" --listTitle "Test" --listItemId "236"

  Date: 2/20/2023

  Property | Value
  ---------|-------
  FileName | DummyDocument.docx
  ServerRelativeUrl | /Lists/Test/Attachments/236/DummyDocument.docx
  ```

  </TabItem>
</Tabs>
