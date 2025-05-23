-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# external connection get

Allow the administrator to get a specific external connection

## Usage

```sh
m365 external connection get [options]
```

## Alias

```sh
m365 search externalconnection get
```

## Options

```md definition-list
`-i, --id [id]`
: ID of the External Connection to get. Specify either `id` or `name`.

`-n, --name [name]`
: Name of the External Connection to get. Specify either `id` or `name`.
```

<Global />

## Examples

Get the External Connection by its id.

```sh
m365 external connection get --id "MyApp"
```

Get the External Connection by its name.

```sh
m365 external connection get --name "Test"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
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
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  configuration: {"authorizedApps":["31359c7f-bd7e-475c-86db-fdb8c937548e"],"authorizedAppIds":["31359c7f-bd7e-475c-86db-fdb8c937548e"]}
  description  : CLI Test
  id           : CLITest
  name         : CLI-Test
  state        : draft
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,name,description,state,configuration
  CLITest,CLI-Test,CLI Test,draft,"{""authorizedApps"":[""31359c7f-bd7e-475c-86db-fdb8c937548e""],""authorizedAppIds"":[""31359c7f-bd7e-475c-86db-fdb8c937548e""]}"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # external connection get --id "CLITest"

  Date: 2022-11-05

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
