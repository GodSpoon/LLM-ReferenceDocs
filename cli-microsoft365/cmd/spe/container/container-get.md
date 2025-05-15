-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spe container get

Gets a container of a specific container type

## Usage

```sh
m365 spe container get [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The Id of the container instance.
```

<Global />

## Examples

Gets a container of a specific type.

```sh
m365 spe container get --id "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "displayName": "My Application Storage Container",
    "description": "Description of My Application Storage Container",
    "containerTypeId": "91710488-5756-407f-9046-fbe5f0b4de73",
    "status": "active",
    "createdDateTime": "2021-11-24T15:41:52.347Z",
    "settings": {
      "isOcrEnabled": false
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id              : b!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  displayName     : My Application Storage Container
  description     : Description of My Application Storage Container
  containerTypeId : 91710488-5756-407f-9046-fbe5f0b4de73
  status          : active
  createdDateTime : 2021-11-24T15:41:52.347Z
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,description,containerTypeId,status,createdDateTime
  b!EXAMPLE_SECRET_VALUE_PLACEHOLDER,My Application Storage Container,Description of My Application Storage Container,91710488-5756-407f-9046-fbe5f0b4de73,active,2021-11-24T15:41:52.347Z
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spe container get --id "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER"

  Date: 14/03/2024

  ## My Application Storage Container (b!EXAMPLE_SECRET_VALUE_PLACEHOLDER)

  Property | Value
  ---------|-------
  id | b!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  displayName | My Application Storage Container
  description | Description of My Application Storage Container
  containerTypeId | 91710488-5756-407f-9046-fbe5f0b4de73
  status | active
  createdDateTime | 2021-11-24T15:41:52.347Z
  ```

  </TabItem>
</Tabs>
