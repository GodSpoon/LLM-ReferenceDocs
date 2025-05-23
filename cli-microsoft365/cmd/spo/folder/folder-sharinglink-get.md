-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo folder sharinglink get

Gets details about a specific sharing link on a folder

## Usage

```sh
m365 spo folder sharinglink get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the folder is located.

`--folderUrl [folderUrl]`
: The server- or site-relative decoded URL of the folder. Specify either `folderUrl` or `folderId` but not both.

`--folderId [folderId]`
: The Unique ID (GUID) of the folder. Specify either `folderUrl` or `folderId` but not both.

`-i, --id <id>`
: The sharing link ID.
```

<Global />

## Examples

Gets a specific sharing link of a folder by id.

```sh
m365 spo folder sharinglink get --webUrl https://contoso.sharepoint.com/sites/demo --id 45fa6aed-362f-48b1-b04e-6da85a526506 --folderId daebb04b-a773-4baa-b1d1-3625418e3234
```

Gets a specific sharing link of a folder by url.

```sh
m365 spo folder sharinglink get --webUrl https://contoso.sharepoint.com/sites/demo --id 45fa6aed-362f-48b1-b04e-6da85a526506 --folderUrl "/sites/demo/shared documents/folder"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "d6f6a428-9857-471f-9635-edd68d5aa6c1",
    "roles": [
      "write"
    ],
    "shareId": "u!EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "hasPassword": false,
    "grantedToIdentitiesV2": [],
    "grantedToIdentities": [],
    "link": {
      "scope": "anonymous",
      "type": "edit",
      "webUrl": "https://contoso.sharepoint.com/:f:/s/demo/EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "preventsDownload": false
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  grantedToIdentities            : []
  grantedToIdentitiesV2          : []
  hasPassword                    : false
  id                             : d6f6a428-9857-471f-9635-edd68d5aa6c1
  link                           : {"scope":"anonymous","type":"edit","webUrl":"https://contoso.sharepoint.com/:f:/s/demo/EXAMPLE_SECRET_VALUE_PLACEHOLDER","preventsDownload":false}
  roles                          : ["write"]
  shareId                        : u!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,shareId,hasPassword
  d6f6a428-9857-471f-9635-edd68d5aa6c1,u!EXAMPLE_SECRET_VALUE_PLACEHOLDER,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo folder sharinglink get --webUrl "https://contoso.sharepoint.com/sites/demo" --id "d6f6a428-9857-471f-9635-edd68d5aa6c1" --folderUrl "/sites/demo/shared documents/Test"

  Date: 5/2/2024

  ## d6f6a428-9857-471f-9635-edd68d5aa6c1

  Property | Value
  ---------|-------
  id | d6f6a428-9857-471f-9635-edd68d5aa6c1
  shareId | u!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  hasPassword | false
  ```

  </TabItem>
</Tabs>
