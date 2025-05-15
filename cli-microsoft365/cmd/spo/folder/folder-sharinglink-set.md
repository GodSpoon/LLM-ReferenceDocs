-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo folder sharinglink set

Updates a sharing link of a folder

## Usage

```sh
m365 spo folder sharinglink set [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
:	The URL of the site where the folder is located.

`--folderUrl [folderUrl]`
:	The server- or site-relative decoded URL of the folder. Specify either `folderUrl` or `folderId` but not both.

`--folderId [folderId]`
:	The unique ID (GUID) of the folder. Specify either `folderUrl` or `folderId` but not both.

`--id <id>`
: The sharing link ID.

`--expirationDateTime <expirationDateTime>`
:	The date and time to set the expiration. This should be defined as a valid ISO 8601 string. This option only works for anonymous links.
```

<Global />

## Examples

Updates the expiration datetime of an anonymous sharing link for a folder specific by folder ID.

```sh
m365 spo folder sharinglink set --webUrl https://contoso.sharepoint.com/sites/demo --folderId daebb04b-a773-4baa-b1d1-3625418e3234 --id 7c9f97c9-1bda-433c-9364-bb83e81771ee --expirationDateTime '2022-11-30T00:00:00Z'
```

Updates the expiration datetime of an anonymous sharing link for a folder specific by folder URL.

```sh
m365 spo folder sharinglink set --webUrl https://contoso.sharepoint.com/sites/demo --folderUrl /sites/demo/shared%20documents/Folder --id 7c9f97c9-1bda-433c-9364-bb83e81771ee --expirationDateTime '2022-11-30T00:00:00Z'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "bd1481e9-958b-4c1a-a33c-fb021f4ed444",
    "roles": [
      "write"
    ],
    "shareId": "u!EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "expirationDateTime": "2024-05-05T16:57:00Z",
    "hasPassword": false,
    "grantedToIdentitiesV2": [],
    "grantedToIdentities": [],
    "link": {
      "scope": "anonymous",
      "type": "edit",
      "webUrl": "https://contoso.sharepoint.com/:f:/g/EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "preventsDownload": false
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  expirationDateTime   : 2024-05-05T16:57:00Z
  grantedToIdentities  : []
  grantedToIdentitiesV2: []
  hasPassword          : false
  id                   : bd1481e9-958b-4c1a-a33c-fb021f4ed444
  link                 : {"scope":"anonymous","type":"edit","webUrl":"https://contoso.sharepoint.com/:f:/g/EXAMPLE_SECRET_VALUE_PLACEHOLDER","preventsDownload":false}
  roles                : ["write"]
  shareId              : u!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,shareId,expirationDateTime,hasPassword
  bd1481e9-958b-4c1a-a33c-fb021f4ed444,u!EXAMPLE_SECRET_VALUE_PLACEHOLDER,2024-05-05T16:57:00Z,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo folder sharinglink set --webUrl "https://contoso.sharepoint.com" --folderUrl "/shared documents/f1" --id "bd1481e9-958b-4c1a-a33c-fb021f4ed444" --expirationDateTime "2024-05-05T16:57:00.000Z"

  Date: 03/05/2024

  ## bd1481e9-958b-4c1a-a33c-fb021f4ed444

  Property | Value
  ---------|-------
  id | bd1481e9-958b-4c1a-a33c-fb021f4ed444
  shareId | u!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  expirationDateTime | 2024-05-05T16:57:00Z
  hasPassword | false
  ```

  </TabItem>
</Tabs>
