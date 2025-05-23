-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo file rename

Renames a file

## Usage

```sh
m365 spo file rename [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the file is located.

`-s, --sourceUrl <sourceUrl>`
: The server- or site-relative decoded URL of the file to rename.

`-t, --targetFileName <targetFileName>`
: New file name of the file.

`--force`
: If a file already exists with target file name, it will be moved to the recycle bin. If omitted, the rename operation will be canceled if a file already exists with the specified file name.
```

<Global />

## Remarks

If you try to rename a file without the `--force` flag and a file with this name already exists, the operation will be cancelled.

## Examples

Renames a file.

```sh
m365 spo file rename --webUrl https://contoso.sharepoint.com/sites/project-x --sourceUrl '/Shared Documents/Test1.docx' --targetFileName 'Test2.docx'
```

Renames a file. If the file with the target file name already exists, this file will be moved to the recycle bin.

```sh
m365 spo file rename --webUrl https://contoso.sharepoint.com/sites/project-x --sourceUrl '/Shared Documents/Test1.docx' --targetFileName 'Test2.docx' --force
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "ErrorCode": 0,
      "ErrorMessage": null,
      "FieldName": "FileLeafRef",
      "FieldValue": "Newlogo2.jpg",
      "HasException": false,
      "ItemId": 26
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  ErrorCode   : 0
  ErrorMessage: null
  FieldName   : FileLeafRef
  FieldValue  : Newlogo2.jpg
  HasException: false
  ItemId      : 26
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ErrorCode,FieldName,FieldValue,HasException,ItemId
  0,FileLeafRef,Newlogo2.jpg,,26
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo file rename --webUrl "https://contoso.sharepoint.com/sites/project-x" --sourceUrl "/Shared Documents/Newlogo.jpg" --targetFileName "Newlogo2.jpg"

  Date: 10/3/2023

  Property | Value
  ---------|-------
  ErrorCode | 0
  FieldName | FileLeafRef
  FieldValue | Newlogo2.jpg
  HasException | false
  ItemId | 26
  ```

  </TabItem>
</Tabs>
