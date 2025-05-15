-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo contenttype sync

Adds a published content type from the content type hub to a site or syncs its latest changes.

## Usage

```sh
m365 spo contenttype sync [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The site to sync the Content Type to.

`-i, --id [id]`
: The Id of the published Content Type to sync from the Content Type Hub. Specify either `id` or `name`.

`-n, --name [name]`
: The name of the published Content Type to sync from the Content Type Hub. Specify either `id` or `name`.

`--listTitle [listTitle]`
: Title of the list. Specify either `listTitle`, `listId` or `listUrl`. Omit to sync as a site content type.

`--listId [listId]`
: ID of the list. Specify either `listTitle`, `listId` or `listUrl`. Omit to sync as a site content type.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listTitle`, `listId` or `listUrl`. Omit to sync as a site content type.
```

<Global />

## Examples

Syncs a given published content type from the hub to the specified site.

```sh
m365 spo contenttype sync —webUrl https://contoso.sharepoint.com/sites/sales --id 0x01007926A45D687BA842B947286090B8F67D
```

Syncs a given published content type from the hub to the specified site and adds it to the specified list.

```sh
m365 spo contenttype sync —webUrl https://contoso.sharepoint.com/sites/sales --id 0x01007926A45D687BA842B947286090B8F67D --listTitle Contacts
```

## Response

:::info

This command will only return a response if the content type is added to the site initially. When syncing the content type, no response is returned.  

:::

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#contentType",
    "@odata.type": "#microsoft.graph.contentType",
    "@odata.etag": "\"2\"",
    "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "isBuiltIn": false,
    "description": "",
    "group": "Custom Content Types",
    "hidden": false,
    "name": "Dummy",
    "parentId": "0x0101",
    "readOnly": true,
    "sealed": false,
    "base": {
      "id": "0x0101",
      "description": "Create a new document.",
      "group": "Document Content Types",
      "hidden": false,
      "name": "Document",
      "readOnly": false,
      "sealed": false
    }
  }
  ```

  </TabItem>
   <TabItem value="Text">

  ```text
  @odata.context: https://graph.microsoft.com/v1.0/$metadata#contentType
  @odata.etag   : "2"
  @odata.type   : #microsoft.graph.contentType
  base          : {"id":"0x0101","description":"Create a new document.","group":"Document Content Types","hidden":false,"name":"Document","readOnly":false,"sealed":false}
  description   :
  group         : Custom Content Types
  hidden        : false
  id            : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  isBuiltIn     : false
  name          : Dummy
  parentId      : 0x0101
  readOnly      : true
  sealed        : false
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  @odata.context,@odata.type,@odata.etag,id,isBuiltIn,description,group,hidden,name,parentId,readOnly,sealed
  https://graph.microsoft.com/v1.0/$metadata#contentType,#microsoft.graph.contentType,"""2""",EXAMPLE_SECRET_VALUE_PLACEHOLDER,,,Custom Content Types,,Dummy,0x0101,1,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo contenttype sync --webUrl "https://contoso.sharepoint.com/sites/project-x" --name "Dummy"

  Date: 13/03/2024

  ## Dummy (EXAMPLE_SECRET_VALUE_PLACEHOLDER)

  Property | Value
  ---------|-------
  @odata.context | https://graph.microsoft.com/v1.0/$metadata#contentType
  @odata.type | #microsoft.graph.contentType
  @odata.etag | "2"
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  isBuiltIn | false
  description |
  group | Custom Content Types
  hidden | false
  name | Dummy 5
  parentId | 0x0101
  readOnly | true
  sealed | false
  ```

  </TabItem>
</Tabs>
