<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo folder sharinglink list

Lists all the sharing links of a specific folder

## Usage

```sh
m365 spo folder sharinglink list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the folder is located.

`--folderUrl [folderUrl]`
: The server- or site-relative decoded URL of the folder. Specify either `folderUrl` or `folderId` but not both.

`--folderId [folderId]`
: The UniqueId (GUID) of the folder. Specify either `folderUrl` or `folderId` but not both.

`-s, --scope [scope]`
: Filter the results to only sharing links of a given scope: `anonymous`, `users` or `organization`. By default all sharing links are listed.
```

<Global />

## Examples

List sharing links of a folder by id.

```sh
m365 spo folder sharinglink list --webUrl https://contoso.sharepoint.com/sites/demo --folderId daebb04b-a773-4baa-b1d1-3625418e3234
```

List sharing links of a folder by url.

```sh
m365 spo folder sharinglink list --webUrl https://contoso.sharepoint.com/sites/demo --folderUrl "/sites/demo/shared documents/folder"
```

List anonymous sharing links of a folder by url.

```sh
m365 spo folder sharinglink list --webUrl https://contoso.sharepoint.com/sites/demo --folderUrl "/sites/demo/shared documents/folder" --scope anonymous
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "e6100f73-981c-4bde-986b-eed262f04659",
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
        "webUrl": "https://contoso.sharepoint.com/:f:/g/EXAMPLE_SECRET_VALUE_PLACEHOLDER",
        "preventsDownload": false
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    scope         roles  link
  ------------------------------------  ------------  -----  -----------------------------------------------------------------------------------
  e6100f73-981c-4bde-986b-eed262f04659  anonymous     write  https://contoso.sharepoint.com/:f:/g/EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,shareId,hasPassword
  e6100f73-981c-4bde-986b-eed262f04659,u!EXAMPLE_SECRET_VALUE_PLACEHOLDER,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo folder sharinglink list --webUrl "https://contoso.sharepoint.com/" --folderUrl "/shared documents/folder1"

  Date: 24/04/2024

  ## e6100f73-981c-4bde-986b-eed262f04659

  Property | Value
  ---------|-------
  id | e6100f73-981c-4bde-986b-eed262f04659
  shareId | u!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  hasPassword | false
  ```

  </TabItem>
</Tabs>
