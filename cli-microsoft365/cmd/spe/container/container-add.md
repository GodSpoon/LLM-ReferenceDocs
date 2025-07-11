-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spe container add

Creates a new container

## Usage

```sh
m365 spe container add [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The display name of the new container.

`-d, --description [description]`
: The description of the new container.

`--containerTypeId [containerTypeId]`
: The container type ID of the container instance. Use either `containerTypeId`, or `containerTypeName` but not both.

`--containerTypeName [containerTypeName]`
: The container type name of the container instance. Use either `containerTypeId`, or `containerTypeName` but not both.

`--ocrEnabled [ocrEnabled]`
: Indicates whether Optical Character Recognition (OCR) is enabled for the container. Possible values: `true`, `false`. Defaults to `false`.

`--itemMajorVersionLimit [itemMajorVersionLimit]`
: The maximum major versions allowed for items in the container. Defaults to `500`.

`--itemVersioningEnabled [itemVersioningEnabled]`
: Indicates whether versioning is enabled for items in the container. Possible values: `true`, `false`. Defaults to `true`.
```

<Global />

## Examples

Creates a new container by specifying the container type ID

```sh
m365 spe container add --name Invoices --containerTypeId bba89883-47c2-455b-956b-7a3d8db007fb
```

Creates a new container by specifying the container type name

```sh
m365 spe container add --name Invoices --containerTypeName "Invoice app container type"
```

Creates a new container with additional options

```sh
m365 spe container add --name Invoices --containerTypeId bba89883-47c2-455b-956b-7a3d8db007fb --ocrEnabled true --itemMajorVersionLimit 200 --itemVersioningEnabled true
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "displayName": "Invoices",
    "description": "This container is used to store invoices",
    "containerTypeId": "bfdd048e-e03f-47d2-bd16-dbbc27281aa3",
    "status": "inactive",
    "createdDateTime": "2025-04-15T13:31:09.62Z",
    "lockState": "unlocked",
    "settings": {
      "isOcrEnabled": false,
      "itemMajorVersionLimit": 500,
      "isItemVersioningEnabled": true
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  containerTypeId: bfdd048e-e03f-47d2-bd16-dbbc27281aa3
  createdDateTime: 2025-04-15T15:14:03.89Z
  description    : This container is used to store invoices
  displayName    : Invoices
  id             : b!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  lockState      : unlocked
  settings       : {"isOcrEnabled":false,"itemMajorVersionLimit":500,"isItemVersioningEnabled":true}
  status         : inactive
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,description,containerTypeId,status,createdDateTime,lockState
  b!EXAMPLE_SECRET_VALUE_PLACEHOLDER,Invoices,This container is used to store invoices,bfdd048e-e03f-47d2-bd16-dbbc27281aa3,inactive,2025-04-15T15:14:45.317Z,unlocked
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spe container add --name "Invoices" --containerTypeId "bfdd048e-e03f-47d2-bd16-dbbc27281aa3" --description "This container is used to store invoices"

  Date: 15/04/2025

  ## Invoices (b!EXAMPLE_SECRET_VALUE_PLACEHOLDER)

  Property | Value
  ---------|-------
  id | b!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  displayName | Invoices
  description | This container is used to store invoices
  containerTypeId | bfdd048e-e03f-47d2-bd16-dbbc27281aa3
  status | inactive
  createdDateTime | 2025-04-15T15:15:19.123Z
  lockState | unlocked
  ```

  </TabItem>
</Tabs>
