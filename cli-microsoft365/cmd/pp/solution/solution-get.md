-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp solution get

Gets a specific solution in a given environment.

## Usage

```sh
m365 pp solution get [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment.

`-i --id [id]`
: The ID of the solution. Specify either `id` or `name` but not both.

`-n, --name [name]`
: The unique name (not the display name) of the solution. Specify either `id` or `name` but not both.

`--asAdmin`
: Run the command as admin for environments you do not have explicitly assigned permissions to.
```

<Global />

## Examples

Gets a specific solution in a specific environment based on name.

```sh
m365 pp solution get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "Default"
```

Gets a specific solution in a specific environment based on name as Admin.

```sh
m365 pp solution get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "Default" --asAdmin
```

Gets a specific solution in a specific environment based on id.

```sh
m365 pp solution get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --id "ee62fd63-e49e-4c09-80de-8fae1b9a427e"
```

Gets a specific solution in a specific environment based on id as Admin.

```sh
m365 pp solution get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --id "ee62fd63-e49e-4c09-80de-8fae1b9a427e" --asAdmin
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "solutionid": "fd140aaf-4df4-11dd-bd17-0019b9312238",
    "uniquename": "Default",
    "version": "1.0",
    "installedon": "2021-10-01T21:29:10Z",
    "solutionpackageversion": null,
    "friendlyname": "Default Solution",
    "versionnumber": 860055,
    "publisherid": {
      "friendlyname": "Default Publisher for org6633049a",
      "publisherid": "d21aab71-79e7-11dd-8874-00188b01e34f"
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  friendlyname          : Default Solution
  installedon           : 2021-10-01T21:29:10Z
  publisherid           : {"friendlyname":"Default Publisher for org6633049a","publisherid":"d21aab71-79e7-11dd-8874-00188b01e34f"}
  solutionid            : fd140aaf-4df4-11dd-bd17-0019b9312238
  solutionpackageversion: null
  uniquename            : Default
  version               : 1.0
  versionnumber         : 860055
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  uniquename,version,publisher
  Default,1.0,Default Publisher for org6633049a
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pp solution get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --id "ee62fd63-e49e-4c09-80de-8fae1b9a427e"

  Date: 9/1/2023

  Property | Value
  ---------|-------
  uniquename | Crc00f1
  version | 1.0.0.0
  publisher | CDS Default Publisher
  ```

  </TabItem>
</Tabs>
