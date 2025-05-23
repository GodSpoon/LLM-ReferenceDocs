-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo folder move

Moves a folder to another location

## Usage

```sh
m365 spo folder move [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the folder is located.

`-s, --sourceUrl [sourceUrl]`
: The server-, site-relative or absolute decoded URL of the folder to move. Specify either `sourceUrl` or `sourceId` but not both.

`-i, --sourceId [sourceId]`
: The ID of the folder to move. Specify either `sourceUrl` or `sourceId` but not both.

`-t, --targetUrl <targetUrl>`
: Server-relative or absolute decoded URL where to move the folder.

`--newName [newName]`
: The new name of the destination folder.

`--nameConflictBehavior [nameConflictBehavior]`
: Behavior when a file or folder with the same name is already present at the destination. Allowed values: `fail`, `rename`. Defaults to `fail`.

`--skipWait`
: Don't wait for the move operation to complete.
```

<Global />

## Remarks

When you specify a value for `nameConflictBehavior`, consider the following:

- `fail` will throw an error when the destination folder already exists.
- `rename` will add a suffix (e.g. folder1) when the destination folder already exists.

## Examples

Move a folder to a document library in another site collection by server-relative URL.

```sh
m365 spo folder move --webUrl https://contoso.sharepoint.com/sites/project-x --sourceUrl "/sites/project-x/Shared Documents/Reports" --targetUrl "/sites/project-y/Shared Documents/Reports January"
```

Move a folder to another location using site-relative URLs and rename it.

```sh
m365 spo folder move --webUrl https://contoso.sharepoint.com/sites/project-x --sourceUrl "/Shared Documents/Reports" --targetUrl "/sites/project-y/Shared Documents" --newName "Reports January"
```

Move a folder to another location and use a new name on conflict.

```sh
m365 spo folder move --webUrl https://contoso.sharepoint.com/sites/project-x --sourceUrl "/sites/project-x/Shared Documents/Reports" --targetUrl "/sites/project-y/Shared Documents/Project files" --nameConflictBehavior rename
```

Move a folder referenced by its ID to another document library and don't wait for the move job to finish.

```sh
m365 spo folder move --webUrl https://contoso.sharepoint.com/sites/project-x --sourceId b8cc341b-9c11-4f2d-aa2b-0ce9c18bcba2 --targetUrl "/sites/project-x/Project files" --skipWait
```

## Response

### Standard Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Exists": true,
    "ExistsAllowThrowForPolicyFailures": true,
    "ExistsWithException": true,
    "IsWOPIEnabled": false,
    "ItemCount": 6,
    "Name": "Company",
    "ProgID": null,
    "ServerRelativeUrl": "/sites/Sales/Icons/Company",
    "TimeCreated": "2024-09-26T22:08:53Z",
    "TimeLastModified": "2024-09-26T22:09:31Z",
    "UniqueId": "d3a37396-ca16-467b-b968-48f5fc41f2b6",
    "WelcomePage": ""
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Exists                           : true
  ExistsAllowThrowForPolicyFailures: true
  ExistsWithException              : true
  IsWOPIEnabled                    : false
  ItemCount                        : 6
  Name                             : Company
  ProgID                           : null
  ServerRelativeUrl                : /sites/Sales/Icons/Company
  TimeCreated                      : 2024-09-26T22:08:53Z
  TimeLastModified                 : 2024-09-26T22:09:31Z
  UniqueId                         : d3a37396-ca16-467b-b968-48f5fc41f2b6
  WelcomePage                      :
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Exists,ExistsAllowThrowForPolicyFailures,ExistsWithException,IsWOPIEnabled,ItemCount,Name,ProgID,ServerRelativeUrl,TimeCreated,TimeLastModified,UniqueId,WelcomePage
  1,1,1,0,6,Company,,/sites/Sales/Icons/Company,2024-09-26T22:08:53Z,2024-09-26T22:09:31Z,d3a37396-ca16-467b-b968-48f5fc41f2b6,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo folder move --webUrl "https://contoso.sharepoint.com/sites/Marketing" --sourceUrl "/Logos/Contoso" --targetUrl "/sites/Sales/Logos"

  Date: 27/09/2024

  ## Company (d3a37396-ca16-467b-b968-48f5fc41f2b6)

  Property | Value
  ---------|-------
  Exists | true
  ExistsAllowThrowForPolicyFailures | true
  ExistsWithException | true
  IsWOPIEnabled | false
  ItemCount | 6
  Name | Company
  ServerRelativeUrl | /sites/Sales/Icons/Company
  TimeCreated | 2024-09-26T22:08:53Z
  TimeLastModified | 2024-09-26T22:09:31Z
  UniqueId | d3a37396-ca16-467b-b968-48f5fc41f2b6
  WelcomePage | 
  ```

  </TabItem>
</Tabs>

### `skipWait` response

The command won't return a response on success.
