-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# external connection list

Lists external connections

## Usage

```sh
m365 external connection list [options]
```

## Alias

```sh
m365 search externalconnection list
```

## Options

<Global />

## Examples

List external connections.

```sh
m365 external connection list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "CLITest",
      "name": "CLI-Test",
      "description": "CLI Test",
      "state": "draft",
      "configuration": {
        "authorizedApps": [
          "31359c7f-bd7e-475c-86db-fdb8c937548e"
        ],
        "authorizedAppIds": [
          "31359c7f-bd7e-475c-86db-fdb8c937548e"
        ]
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id       name      state
  -------  --------  -----
  CLITest  CLI-Test  draft
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,name,state
  CLITest,CLI-Test,draft
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # external connection list

  Date: 2022-09-05

  ## CLI-Test (CLITest)

  Property | Value
  ---------|-------
  id | CLITest
  name | CLI-Test
  description | CLI Test
  state | draft
  ```

  </TabItem>
</Tabs>
