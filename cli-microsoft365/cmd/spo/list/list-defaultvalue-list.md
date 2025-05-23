-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo list defaultvalue list

Retrieves default column values for a specific document library

## Usage

```sh
m365 spo list defaultvalue list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list is located.

`-i, --listId [listId]`
: ID of the list. Specify either `listTitle`, `listId`, or `listUrl`.

`-t, --listTitle [listTitle]`
: Title of the list. Specify either `listTitle`, `listId`, or `listUrl`.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listTitle`, `listId`, or `listUrl`.

`--folderUrl [folderUrl]`
: Only get default column values from a specific folder.
```

<Global />

## Examples

List all default column values of a list specified by title

```sh
m365 spo list defaultvalue list --webUrl https://contoso.sharepoint.com/sites/marketing --listTitle "Project Documents"
```

List all default column values of a list specified by ID

```sh
m365 spo list defaultvalue list --webUrl https://contoso.sharepoint.com/sites/marketing --listId 12345678-90ab-cdef-1234-567890abcdef
```

List all default column values of a list specified by server relative URL

```sh
m365 spo list defaultvalue list --webUrl https://contoso.sharepoint.com/sites/marketing --listUrl "/sites/marketing/Project Documents"
```

List all default column values of a specific folder in a list specified by site relative URLs

```sh
m365 spo list defaultvalue list --webUrl https://contoso.sharepoint.com/sites/marketing --listUrl "/Project Documents" --folderUrl "/Project Documents/Archive"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "fieldName": "Countries",
      "fieldValue": "19;#Belgium|442affc2-7fab-4f33-9590-330403a579c2",
      "folderUrl": "/sites/Marketing/Project Documents"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  fieldName  fieldValue                                        folderUrl
  ---------  ------------------------------------------------  ----------------------------------
  Countries  19;#Belgium|442affc2-7fab-4f33-9590-330403a579c2  /sites/Marketing/Project Documents
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  fieldName,fieldValue,folderUrl
  Countries,19;#Belgium|442affc2-7fab-4f33-9590-330403a579c2,/sites/Marketing/Project Documents
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo list defaultvalue list --webUrl "https://contoso.sharepoint.com/sites/marketing" --listUrl "/Project Documents"

  Date: 20/10/2024

  Property | Value
  ---------|-------
  fieldName | Countries
  fieldValue | 19;#Belgium\|442affc2-7fab-4f33-9590-330403a579c2
  folderUrl | /sites/Marketing/Project Documents
  ```

  </TabItem>
</Tabs>
