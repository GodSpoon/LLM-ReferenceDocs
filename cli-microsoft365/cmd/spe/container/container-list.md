-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spe container list

Lists containers of a specific Container Type

## Usage

```sh
m365 spe container list [options]
```

## Options

```md definition-list
`--containerTypeId [containerTypeId]`
: The Container Type Id of the container instance. Use either `containerTypeId` or `containerTypeName` but not both.

`--containerTypeName [containerTypeName]`
: The Container Type name of the container instance. Use either `containerTypeId` or `containerTypeName` but not both.
```

<Global />

## Examples

List containers of a specific type by id.

```sh
m365 spe container list --containerTypeId "91710488-5756-407f-9046-fbe5f0b4de73"
```

List containers of a specific type by name.

```sh
m365 spe container list --containerTypeName "trial container"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "displayName": "My File Storage Container",
      "containerTypeId": "e2756c4d-fa33-4452-9c36-2325686e1082",
      "createdDateTime": "2021-11-24T15:41:52.347Z"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                                                  displayName                containerTypeId                       createdDateTime
  ------------------------------------------------------------------  -------------------------  ------------------------------------  ------------------------
  b!EXAMPLE_SECRET_VALUE_PLACEHOLDER  My File Storage Container  e2756c4d-fa33-4452-9c36-2325686e1082  2021-11-24T15:41:52.347Z
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,containerTypeId,createdDateTime
  b!EXAMPLE_SECRET_VALUE_PLACEHOLDER,My File Storage Container,e2756c4d-fa33-4452-9c36-2325686e1082,2021-11-24T15:41:52.347Z
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spe container list

  Date: 10/06/2024

  ## My File Storage Container

  Property | Value
  ---------|-------
  id | b!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  displayName | My File Storage Container
  containerTypeId | e2756c4d-fa33-4452-9c36-2325686e1082
  createdDateTime | 2021-11-24T15:41:52.347Z
  ```

  </TabItem>
</Tabs>

## More information

In SharePoint Embedded, all files and documents are stored in Containers. The calling app should be the owning app of the container type.
