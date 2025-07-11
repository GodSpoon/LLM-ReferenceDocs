-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spe container recyclebinitem list

Lists deleted containers of a specific container type

## Usage

```sh
m365 spe container recyclebinitem list [options]
```

## Options

```md definition-list
`--containerTypeId [containerTypeId]`
: The container type ID of the container instance. Use either `containerTypeId` or `containerTypeName` but not both.

`--containerTypeName [containerTypeName]`
: The container type name of the container instance. Use either `containerTypeId` or `containerTypeName` but not both.
```

<Global />

## Examples

List deleted containers of a specific container type specified by id.

```sh
m365 spe container recyclebinitem list --containerTypeId "91710488-5756-407f-9046-fbe5f0b4de73"
```

List deleted containers of a specific container type specified by name.

```sh
m365 spe container recyclebinitem list --containerTypeName "My container type name"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "displayName": "My Application Storage Container",
      "containerTypeId": "1a55ba46-a673-45a4-b0d9-bd9913d06957",
      "createdDateTime": "2025-04-15T21:51:48Z",
      "settings": {
        "isOcrEnabled": false
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                                                  displayName
  ------------------------------------------------------------------  --------------------------------
  b!EXAMPLE_SECRET_VALUE_PLACEHOLDER  My Application Storage Container
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,containerTypeId,createdDateTime
  b!EXAMPLE_SECRET_VALUE_PLACEHOLDER,My Application Storage Container,1a55ba46-a673-45a4-b0d9-bd9913d06957,2025-04-15T21:51:48Z
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spe container recyclebinitem list --containerTypeId "1a55ba46-a673-45a4-b0d9-bd9913d06957"

  Date: 18/04/2025

  ## My Application Storage Container (b!EXAMPLE_SECRET_VALUE_PLACEHOLDER)

  Property | Value
  ---------|-------
  id | b!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  displayName | My Application Storage Container
  containerTypeId | 1a55ba46-a673-45a4-b0d9-bd9913d06957
  createdDateTime | 2025-04-15T21:51:48Z
  ```

  </TabItem>
</Tabs>
