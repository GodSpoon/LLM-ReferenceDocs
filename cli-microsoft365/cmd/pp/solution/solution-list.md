-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp solution list

Lists solutions in a given environment.

## Usage

```sh
m365 pp solution list [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment

`--asAdmin`
: Run the command as admin for environments you do not have explicitly assigned permissions to.
```

<Global />

## Examples

List all solutions in a specific environment

```sh
m365 pp solution list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"
```

List all solutions in a specific environment as Admin

```sh
m365 pp solution list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --asAdmin
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "solutionid": "00000001-0000-0000-0001-00000000009b",
      "uniquename": "Crc00f1",
      "version": "1.0.0.0",
      "installedon": "2021-10-01T21:54:14Z",
      "solutionpackageversion": null,
      "friendlyname": "Common Data Services Default Solution",
      "versionnumber": 860052,
      "publisherid": {
        "friendlyname": "CDS Default Publisher",
        "publisherid": "00000001-0000-0000-0000-00000000005a"
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  uniquename  version    publisher
  ----------  ---------  ---------------------
  Crc00f1     1.0.0.0    CDS Default Publisher
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  uniquename,version,publisher
  Crc00f1,1.0.0.0,CDS Default Publisher
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pp solution list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

  Date: 9/1/2023

  Property | Value
  ---------|-------
  uniquename | Crc00f1
  version | 1.0.0.0
  publisher | CDS Default Publisher
  ```

  </TabItem>
</Tabs>
