-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo file sharinglink list

Lists all the sharing links of a specific file

## Usage

```sh
m365 spo file sharinglink list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the file is located.

`--fileUrl [fileUrl]`
: The server- or site-relative decoded URL of the file. Specify either `fileUrl` or `fileId` but not both.

`--fileId [fileId]`
: The UniqueId (GUID) of the file. Specify either `fileUrl` or `fileId` but not both.

`-s, --scope [scope]`
: Filter the results to only sharing links of a given scope: `anonymous`, `users` or `organization`. By default all sharing links are listed.
```

<Global />

## Examples

List sharing links of a file by id.

```sh
m365 spo file sharinglink list --webUrl https://contoso.sharepoint.com/sites/demo --fileId daebb04b-a773-4baa-b1d1-3625418e3234
```

List sharing links of a file by url.

```sh
m365 spo file sharinglink list --webUrl https://contoso.sharepoint.com/sites/demo --fileUrl "/sites/demo/shared documents/document.docx"
```

List anonymous sharing links of a file by url.

```sh
m365 spo file sharinglink list --webUrl https://contoso.sharepoint.com/sites/demo --fileUrl "/sites/demo/shared documents/document.docx" --scope anonymous
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "2a021f54-90a2-4016-b3b3-5f34d2e7d932",
      "roles": [
        "read"
      ],
      "hasPassword": false,
      "grantedToIdentitiesV2": [
        {
          "user": {
            "displayName": "John Doe",
            "email": "john@contoso.onmicrosoft.com",
            "id": "fe36f75e-c103-410b-a18a-2bf6df06ac3a"
          },
          "siteUser": {
            "displayName": "John Doe",
            "email": "john@contoso.onmicrosoft.com",
            "id": "9",
            "loginName": "i:0#.f|membership|john@contoso.onmicrosoft.com"
          }
        }
      ],
      "grantedToIdentities": [ 
        {
          "user": {
            "displayName": "John Doe",
            "email": "john@contoso.onmicrosoft.com",
            "id": "fe36f75e-c103-410b-a18a-2bf6df06ac3a"
          }
        }
      ],
      "link": {
        "scope": "organization",
        "type": "view",
        "webUrl": "https://contoso.sharepoint.com/:w:/s/demo/EXAMPLE_SECRET_VALUE_PLACEHOLDER",
        "preventsDownload": false
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    scope         roles  link                                                            
  ------------------------------------  ------------  -----  ----------------------------------------------------------------------------------------
  2a021f54-90a2-4016-b3b3-5f34d2e7d932  organization  read   https://contoso.sharepoint.com/:w:/s/demo/EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,scope,roles,link
  2a021f54-90a2-4016-b3b3-5f34d2e7d932,organization,read,https://contoso.sharepoint.com/:w:/s/demo/EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo file sharinglink list --webUrl "https://contoso.sharepoint.com/sites/demo" --fileUrl "/sites/demo/Shared Documents/logo.jpg"

  Date: 10/3/2023

  ## 44934455-df4f-48a4-90c9-cd8aec82fa7b

  Property | Value
  ---------|-------
  id | 44934455-df4f-48a4-90c9-cd8aec82fa7b
  shareId | u!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  hasPassword | false
  ```

  </TabItem>
</Tabs>
