-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra resourcenamespace list

Get a list of the RBAC resource namespaces and their properties

## Usage

```sh
m365 entra resourcenamespace list [options]
```

## Options

<Global />

## Remarks

:::warning

The command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

## Examples

Retrieve all resource namespaces.

```sh
m365 entra resourcenamespace list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "microsoft.directory",
      "name": "microsoft.directory"
    },
    {
      "id": "microsoft.aad.b2c",
      "name": "microsoft.aad.b2c"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                     name
  --------------------   --------------------
  microsoft.directory    microsoft.directory
  microsoft.aad.b2c      microsoft.aad.b2c
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,name
  microsoft.directory,microsoft.directory
  microsoft.aad.b2c,microsoft.aad.b2c
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra resourcenamespace list

  Date: 1/31/2025

  ## microsoft.directory (microsoft.directory)

  Property | Value
  ---------|-------
  id | microsoft.directory
  name | microsoft.directory

  ## microsoft.aad.b2c (microsoft.aad.b2c)

  Property | Value
  ---------|-------
  id | microsoft.aad.b2c
  name | microsoft.aad.b2c
  ```
  
  </TabItem>
</Tabs>
