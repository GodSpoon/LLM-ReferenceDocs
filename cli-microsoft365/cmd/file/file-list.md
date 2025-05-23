-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# file list

Retrieves files from the specified folder and site

## Usage

```sh
m365 file list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the folder from which to retrieve files is located

`--folderUrl <folderUrl>`
: The server- or site-relative URL of the folder from which to retrieve files

`--recursive`
: Set to retrieve files from subfolders
```

<Global />

## Remarks

This command is an improved version of the `spo file list` command. The main difference between the two commands is, that `file list` uses Microsoft Graph and properly supports retrieving files from large folders. Because `file list` uses Microsoft Graph and `spo file list` uses SharePoint REST APIs, the data returned by both commands is different.

## Examples

Return all files from the folder _Shared Documents_ located in site _https://contoso.sharepoint.com/sites/project-x_

```sh
m365 file list --webUrl https://contoso.sharepoint.com/sites/project-x --folderUrl 'Shared Documents'
```

Return all files from the folder _Shared Documents_ and all the sub-folders of _Shared Documents_ located in site _https://contoso.sharepoint.com/sites/project-x_

```sh
m365 file list --webUrl https://contoso.sharepoint.com/sites/project-x --folderUrl 'Shared Documents' --recursive
```

Return all files from the _Important_ folder in the _Shared Documents_ document library located in site _https://contoso.sharepoint.com/sites/project-x_

```sh
m365 file list --webUrl https://contoso.sharepoint.com/sites/project-x --folderUrl 'Shared Documents/Important'
```

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "@microsoft.graph.downloadUrl": "https://contoso.sharepoint.com/_layouts/15/download.aspx?UniqueId=9bdc8c49-644a-4875-aaa3-82914fb23226&Translate=false&tempauth=&ApiVersion=2.0",
      "createdDateTime": "2024-02-14T22:41:41Z",
      "eTag": "\"{9BDC8C49-644A-4875-AAA3-82914FB23226},1\"",
      "id": "013TMHP6SJRTOJWSTEOVEKVI4CSFH3EMRG",
      "lastModifiedDateTime": "2024-02-14T22:41:41Z",
      "name": "Document.docx",
      "webUrl": "https://contoso.sharepoint.com/_layouts/15/Doc.aspx?sourcedoc=%7B9BDC8C49-644A-4875-AAA3-82914FB23226%7D&file=Document.Docx&action=default&mobileredirect=true",
      "cTag": "\"c:{9BDC8C49-644A-4875-AAA3-82914FB23226},2\"",
      "size": 41554,
      "createdBy": {
        "user": {
          "email": "john@contoso.com",
          "id": "fe36f75e-c103-410b-a18a-2bf6df06ac3a",
          "displayName": "John Doe"
        }
      },
      "lastModifiedBy": {
        "user": {
          "email": "john@contoso.com",
          "id": "fe36f75e-c103-410b-a18a-2bf6df06ac3a",
          "displayName": "John Doe"
        }
      },
      "parentReference": {
        "driveType": "documentLibrary",
        "driveId": "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER",
        "id": "013TMHP6V6Y2GOVW7725BZO354PWSELRRZ",
        "name": "TEST",
        "path": "/drives/b!EXAMPLE_SECRET_VALUE_PLACEHOLDER/root:",
        "siteId": "0f9b8f4f-0e8e-4630-bb0a-501442db9b64"
      },
      "file": {
        "mimeType": "application/EXAMPLE_SECRET_VALUE_PLACEHOLDER",
        "hashes": {
          "quickXorHash": "MX9jeQT/AfhDDMpYygXlCPYI/kc="
        }
      },
      "fileSystemInfo": {
        "createdDateTime": "2024-02-14T22:41:41Z",
        "lastModifiedDateTime": "2024-02-14T22:41:41Z"
      },
      "shared": {
        "scope": "users"
      },
      "lastModifiedByUser": "John Doe"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  lastModifiedByUser: John Doe
  name              : Document.docx
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  @microsoft.graph.downloadUrl,createdDateTime,eTag,id,lastModifiedDateTime,name,webUrl,cTag,size,lastModifiedByUser
  https://contoso.sharepoint.com/_layouts/15/download.aspx?UniqueId=9bdc8c49-644a-4875-aaa3-82914fb23226&Translate=false&tempauth=&ApiVersion=2.0,2024-02-14T22:41:41Z,"""{9BDC8C49-644A-4875-AAA3-82914FB23226},1""",013TMHP6SJRTOJWSTEOVEKVI4CSFH3EMRG,2024-02-14T22:41:41Z,Thailand.xlsx,https://contoso.sharepoint.com/_layouts/15/Doc.aspx?sourcedoc=%7B9BDC8C49-644A-4875-AAA3-82914FB23226%7D&file=Document.docx&action=default&mobileredirect=true,"""c:{9BDC8C49-644A-4875-AAA3-82914FB23226},2""",41554,John Doe
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # file list --webUrl "https://contoso.sharepoint.com" --folderUrl "Test"

  Date: 14/02/2024

  ## Document.docx (013TMHP6SJRTOJWSTEOVEKVI4CSFH3EMRG)

  Property | Value
  ---------|-------
  @microsoft.graph.downloadUrl | https://contoso.sharepoint.com/\_layouts/15/download.aspx?UniqueId=9bdc8c49-644a-4875-aaa3-82914fb23226&Translate=false&tempauth=&ApiVersion=2.0
  createdDateTime | 2024-02-14T22:41:41Z
  eTag | "{9BDC8C49-644A-4875-AAA3-82914FB23226},1"
  id | 013TMHP6SJRTOJWSTEOVEKVI4CSFH3EMRG
  lastModifiedDateTime | 2024-02-14T22:41:41Z
  name | Document.docx
  webUrl | https://contoso.sharepoint.com/\_layouts/15/Doc.aspx?sourcedoc=%7B9BDC8C49-644A-4875-AAA3-82914FB23226%7D&file=Thailand.xlsx&action=default&mobileredirect=true
  cTag | "c:{9BDC8C49-644A-4875-AAA3-82914FB23226},2"
  size | 41554
  lastModifiedByUser | John Doe
  ```

  </TabItem>
</Tabs>
