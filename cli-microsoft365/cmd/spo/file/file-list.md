-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo file list

Gets all files within the specified folder and site

## Usage

```sh
m365 spo file list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the folder from which to retrieve files is located.

`--folderUrl <folderUrl>`
: The server- or site-relative decoded URL of the parent folder from which to retrieve files.

`--fields [fields]`
: Comma-separated list of fields to retrieve. Will retrieve all fields if not specified.

`--filter [filter]`
: OData filter to use to query the list of items with.

`-r, --recursive`
: Set to retrieve files from subfolders.
```

<Global />

## Remarks

When the `fields` option includes values with a `/`, for example: `ListItemAllFields/Id`, an additional `$expand` query parameter will be included on `ListItemAllFields`.

## Examples

Return all files from a folder.

```sh
m365 spo file list --webUrl https://contoso.sharepoint.com/sites/project-x --folderUrl 'Shared Documents'
```

Return all files from a folder and all the sub-folders.

```sh
m365 spo file list --webUrl https://contoso.sharepoint.com/sites/project-x --folderUrl 'Shared Documents' --recursive
```

Return the files from a folder with specific fields which will be expanded.

```sh
m365 spo file list --webUrl https://contoso.sharepoint.com/sites/project-x --folderUrl 'Shared Documents' --fields "Title,Length"
```

Return the files from a folder that meet the criteria of the filter with specific fields which will be expanded.

```sh
m365 spo file list --webUrl https://contoso.sharepoint.com/sites/project-x --folderUrl 'Shared Documents' --fields ListItemAllFields/Id --filter "Name eq 'document.docx'"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "CheckInComment": "",
      "CheckOutType": 2,
      "ContentTag": "{F09C4EFE-B8C0-4E89-A166-03418661B89B},9,12",
      "CustomizedPageStatus": 0,
      "ETag": "\"{F09C4EFE-B8C0-4E89-A166-03418661B89B},9\"",
      "Exists": true,
      "IrmEnabled": false,
      "Length": 331673,
      "Level": 1,
      "LinkingUri": "https://contoso.sharepoint.com/sites/project-x/Shared Documents/Document.docx?d=wf09c4efeb8c04e89a16603418661b89b",
      "LinkingUrl": "https://contoso.sharepoint.com/sites/project-x/Shared Documents/Document.docx?d=wf09c4efeb8c04e89a16603418661b89b",
      "MajorVersion": 3,
      "MinorVersion": 0,
      "Name": "Document.docx",
      "ServerRelativeUrl": "/sites/project-x/Shared Documents/Document.docx",
      "TimeCreated": "2018-02-05T08:42:36Z",
      "TimeLastModified": "2018-02-05T08:44:03Z",
      "Title": "",
      "UIVersion": 1536,
      "UIVersionLabel": "3.0",
      "UniqueId": "f09c4efe-b8c0-4e89-a166-03418661b89b"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Name                               ServerRelativeUrl                                UniqueId
  ---------------------------------  -----------------------------------------------  ------------------------------------
  Document.docx                      /sites/project-x/Shared Documents/Document.docx  5eb97525-2167-4d26-94b8-092a97d65716
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Name,ServerRelativeUrl,UniqueId
  Document.docx,/sites/project-x/Shared Documents/Document.docx,5eb97525-2167-4d26-94b8-092a97d65716
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo file list --webUrl "https://contoso.sharepoint.com" --folderUrl "Shared Documents"

  Date: 23/3/2023

  ## Document.docx (5eb97525-2167-4d26-94b8-092a97d65716)

  Property | Value
  ---------|-------
  Name | Document.docx
  ServerRelativeUrl | /sites/project-x/Shared Documents/Document.docx
  UniqueId | 5eb97525-2167-4d26-94b8-092a97d65716
  ```

  </TabItem>
</Tabs>
