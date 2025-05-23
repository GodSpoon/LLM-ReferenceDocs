-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo file sharinglink set

Updates a sharing link of a file

## Usage

```sh
m365 spo file sharinglink set [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
:	The URL of the site where the file is located.

`--fileUrl [fileUrl]`
:	The server- or site-relative decoded URL of the file. Specify either `fileUrl` or `fileId` but not both.

`--fileId [fileId]`
:	The UniqueId (GUID) of the file. Specify either `fileUrl` or `fileId` but not both.

`--id <id>`
: The ID of the sharing link.

`--expirationDateTime <expirationDateTime>`
:	The date and time to set the expiration. This should be defined as a valid ISO 8601 string. This options only works for anonymous links.
```

<Global />

## Examples

Updates an anonymous sharing link from a file by a specified site-relative URL with the expirationDateTime parameter.

```sh
m365 spo file sharinglink set --webUrl https://contoso.sharepoint.com --fileUrl "/sites/demo/Shared Documents/Document.docx" --id 7c9f97c9-1bda-433c-9364-bb83e81771ee --expirationDateTime "2023-01-09T16:57:00.000Z"
```

Updates an anonymous sharing link from a file by id with the expirationDateTime parameter.

```sh
m365 spo file sharinglink set --webUrl https://contoso.sharepoint.com --fileId daebb04b-a773-4baa-b1d1-3625418e3234 --id 7c9f97c9-1bda-433c-9364-bb83e81771ee --expirationDateTime "2023-01-09T16:57:00.000Z"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "7c9f97c9-1bda-433c-9364-bb83e81771ee",
    "roles": [
      "read"
    ],
    "expirationDateTime": "2023-02-09T16:57:00Z",
    "hasPassword": false,
    "grantedToIdentitiesV2": [],
    "grantedToIdentities": [],
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
  expirationDateTime   : 2023-02-09T16:57:00Z
  grantedToIdentities  : []
  grantedToIdentitiesV2: []
  hasPassword          : false
  id                   : 7c9f97c9-1bda-433c-9364-bb83e81771ee
  link                 : {"scope":"anonymous","type":"view","webUrl":"https://contoso.sharepoint.com/:b:/g/EXAMPLE_SECRET_VALUE_PLACEHOLDER","preventsDownload":false}
  roles                : ["read"]
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,roles,expirationDateTime,hasPassword,grantedToIdentitiesV2,grantedToIdentities,link
  7c9f97c9-1bda-433c-9364-bb83e81771ee,"[""read""]",2023-02-09T16:57:00Z,,[],[],"{""scope"":""anonymous"",""type"":""view"",""webUrl"":""https://contoso.sharepoint.com/:b:/g/EXAMPLE_SECRET_VALUE_PLACEHOLDER"",""preventsDownload"":false}"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo file sharinglink set --webUrl "https://contoso.sharepoint.com" --fileUrl "/sites/demo/Shared Documents/Document.docx" --expirationDateTime "2023-02-09T16:57:00.000Z" --id "7c9f97c9-1bda-433c-9364-bb83e81771ee"

  Date: 5/2/2023

  ## 7c9f97c9-1bda-433c-9364-bb83e81771ee

  Property | Value
  ---------|-------
  id | 7c9f97c9-1bda-433c-9364-bb83e81771ee
  expirationDateTime | 2023-02-09T16:57:00Z
  hasPassword | false
  ```

  </TabItem>
</Tabs>
