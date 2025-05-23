-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo folder sharinglink add

Creates a new sharing link to a folder

## Usage

```sh
m365 spo folder sharinglink add [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the folder is located.

`--folderUrl [folderUrl]`
: The server- or site-relative decoded URL of the folder. Specify either `folderUrl` or `folderId` but not both.

`--folderId [folderId]`
: The UniqueId (GUID) of the folder. Specify either `folderUrl` or `folderId` but not both.

`--type <type>`
: The type of sharing link to create. Either `view` or `edit`.

`--expirationDateTime [expirationDateTime]`
: The date and time to set the expiration. This should be defined as a valid ISO 8601 string.

`--scope [scope]`
: The scope of link to create. Either `anonymous`, `organization` or `users`. If not specified, the default of the organization will be used.

`--retainInheritedPermissions [retainInheritedPermissions]`
: If `true`, any existing inherited permissions are retained on the shared item when sharing this item for the first time. If `false`, all existing permissions are removed when sharing for the first time.

`--recipients [recipients]`
: Comma separated list of users with whom we wish to share the item with. Required when using scope `users`.
```

<Global />

## Examples

Creates a view-only anonymous sharing link of a folder by id.

```sh
m365 spo folder sharinglink add --webUrl https://contoso.sharepoint.com/sites/demo --folderId daebb04b-a773-4baa-b1d1-3625418e3234 --type view --scope anonymous
```

Creates an edit organization sharing link of a folder by url with a specific expiration date.

```sh
m365 spo folder sharinglink add --webUrl https://contoso.sharepoint.com/sites/demo --folderUrl /sites/demo/shared%20documents/Folder --type edit --scope organization --expirationDateTime '2022-11-30T00:00:00Z'
```

Creates a user sharing link of a folder by id.

```sh
m365 spo folder sharinglink add --webUrl https://contoso.sharepoint.com/sites/demo --folderId daebb04b-a773-4baa-b1d1-3625418e3234 --type view --scope users --recipients john@contoso.com,doe@contoso.com
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "4fe11ccb-6c83-4927-8072-95642422b8ae",
    "roles": [
      "read"
    ],
    "shareId": "u!EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "hasPassword": false,
    "link": {
      "scope": "anonymous",
      "type": "view",
      "webUrl": "https://contoso.sharepoint.com/:f:/g/EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "preventsDownload": false
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  hasPassword: false
  id         : 4fe11ccb-6c83-4927-8072-95642422b8ae
  link       : {"scope":"anonymous","type":"view","webUrl":"https://contoso.sharepoint.com/:f:/g/EXAMPLE_SECRET_VALUE_PLACEHOLDER","preventsDownload":false}
  roles      : ["read"]
  shareId    : u!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,shareId,hasPassword
  4fe11ccb-6c83-4927-8072-95642422b8ae,u!EXAMPLE_SECRET_VALUE_PLACEHOLDER,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo folder sharinglink add --webUrl "https://contoso.sharepoint.com" --folderUrl "/shared documents/folder1" --type "view" --scope "anonymous"

  Date: 29/04/2024

  ## 4fe11ccb-6c83-4927-8072-95642422b8ae

  Property | Value
  ---------|-------
  id | 4fe11ccb-6c83-4927-8072-95642422b8ae
  shareId | u!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  hasPassword | false
  ```

  </TabItem>
</Tabs>
