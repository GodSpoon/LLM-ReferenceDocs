-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo file sharinglink add

Creates a new sharing link for a file

## Usage

```sh
m365 spo file sharinglink add [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the file is located.

`--fileUrl [fileUrl]`
: The server- or site-relative decoded URL of the file. Specify either `fileUrl` or `fileId` but not both.

`--fileId [fileId]`
: The UniqueId (GUID) of the file. Specify either `fileUrl` or `fileId` but not both.

`--type <type>`
: The type of sharing link to create. Either `view` or `edit`.

`--expirationDateTime [expirationDateTime]`
: The date and time to set the expiration. This should be defined as a valid ISO 8601 string.

`--scope [scope]`
: The scope of link to create. Either `anonymous` or `organization`. If not specified, the default of the organization will be used.
```

<Global />

## Examples

Creates a sharing link of a specific type for a file by id.

```sh
m365 spo file sharinglink add --webUrl https://contoso.sharepoint.com --fileId daebb04b-a773-4baa-b1d1-3625418e3234 --type view
```

Creates a sharing link of a specific type for a file by url.

```sh
m365 spo file sharinglink add --webUrl https://contoso.sharepoint.com --fileUrl "/sites/demo/Shared Documents/Test1.docx" --type edit
```

Creates a sharing link of a file by url with type, scope and expirationDateTime parameter.

```sh
m365 spo file sharinglink add --webUrl https://contoso.sharepoint.com --fileUrl "/sites/demo/Shared Documents/Test1.docx" --type edit --scope anonymous --expirationDateTime "2023-01-09T16:20:00Z"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "1e581e93-609e-4077-8152-c43865db684c",
    "roles": [
      "read"
    ],
    "expirationDateTime": "2023-10-01T07:00:00Z",
    "hasPassword": false,
    "link": {
      "scope": "anonymous",
      "type": "view",
      "webUrl": "https://contoso.sharepoint.com/:b:/g/EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "preventsDownload": false
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  hasPassword       : false
  expirationDateTime: 2023-10-01T07:00:00Z
  id                : 1e581e93-609e-4077-8152-c43865db684c
  link              : {"scope":"anonymous","type":"view","webUrl":"https://contoso.sharepoint.com/:b:/g/EXAMPLE_SECRET_VALUE_PLACEHOLDER","preventsDownload":false}
  roles             : ["read"]
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,expirationDateTime,roles,hasPassword,link
  1e581e93-609e-4077-8152-c43865db684c,2023-10-01T07:00:00Z,"[""read""]",,"{""scope"":""anonymous"",""type"":""view"",""webUrl"":""https://contoso.sharepoint.com/:b:/g/EXAMPLE_SECRET_VALUE_PLACEHOLDER"",""preventsDownload"":false}"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo file sharinglink add --webUrl "https://contoso.sharepoint.com/sites/demo" --fileUrl "/sites/demo/Shared Documents/logo.jpg" --type "edit" --scope "anonymous" --expirationDateTime "2023-12-12T16:20:00Z"

  Date: 10/3/2023

  ## 9239171b-d85c-4206-a852-45e8d61f9052

  Property | Value
  ---------|-------
  id | 9239171b-d85c-4206-a852-45e8d61f9052
  shareId | u!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  expirationDateTime | 2023-12-12T16:20:00Z
  hasPassword | false
  ```

  </TabItem>
</Tabs>
