-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo file version get

Gets information about a specific version of a specified file

## Usage

```sh
m365 spo file version get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the file is located.

`--label <label>`
: Label of version which will be retrieved.

`--fileUrl [fileUrl]`
: The server- or site-relative decoded URL of the file to retrieve. Specify either `fileUrl` or `fileId` but not both.

`-i, --fileId [fileId]`
: The UniqueId (GUID) of the file to retrieve. Specify either `fileUrl` or `fileId` but not both.
```

<Global />

## Examples

Get file version in a specific site based on fileId.

```sh
m365 spo file version get --webUrl https://contoso.sharepoint.com --label "1.0" --fileId 'b2307a39-e878-458b-bc90-03bc578531d6'
```

Get file in a specific site based on fileUrl.

```sh
m365 spo file version get --webUrl https://contoso.sharepoint.com --label "1.0" --fileUrl '/Shared Documents/Document.docx'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "CheckInComment": "",
    "Created": "2022-10-30T12:03:06Z",
    "ID": 512,
    "IsCurrentVersion": false,
    "Length": "18898",
    "Size": 18898,
    "Url": "_vti_history/512/Shared Documents/Document.docx",
    "VersionLabel": "1.0"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  CheckInComment  :
  Created         : 2022-10-30T12:03:06Z
  ID              : 512
  IsCurrentVersion: false
  Length          : 18898
  Size            : 18898
  Url             : _vti_history/512/Shared Documents/Document.docx
  VersionLabel    : 1.0
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  CheckInComment,Created,ID,IsCurrentVersion,Length,Size,Url,VersionLabel
  ,2022-10-30T12:03:06Z,512,,18898,18898,_vti_history/512/Shared Documents/Document.docx,1.0
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo file version get --webUrl "https://contoso.sharepoint.com" --label "1.0" --fileUrl "/Shared Documents/Document.docx"

  Date: 10/3/2023

  ## 512

  Property | Value
  ---------|-------
  CheckInComment |
  Created | 2022-10-30T12:03:06Z
  ID | 512
  IsCurrentVersion | false
  Length | 18898
  Size | 18898
  Url | \_vti\_history/512/Shared Documents/Document.docx
  VersionLabel | 1.0
  ```

  </TabItem>
</Tabs>
