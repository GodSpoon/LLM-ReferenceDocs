-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp solution publisher list

Lists publishers in a given environment.

## Usage

```sh
m365 pp solution publisher list [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment.

`--includeMicrosoftPublishers`
: (deprecated. Use option `withMicrosoftPublishers` instead) Include the Microsoft Publishers.

`--withMicrosoftPublishers`
: Include the Microsoft Publishers.

`--asAdmin`
: Run the command as admin for environments you do not have explicitly assigned permissions to.
```

<Global />

## Examples

List all publishers in a specific environment.

```sh
m365 pp solution publisher list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"
```

List all publishers in a specific environment as Admin.

```sh
m365 pp solution publisher list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --asAdmin
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "publisherid": "00000001-0000-0000-0000-00000000005a",
      "uniquename": "Cree38e",
      "friendlyname": "CDS Default Publisher",
      "versionnumber": 1074060,
      "isreadonly": false,
      "description": null,
      "customizationprefix": "cr6c3",
      "customizationoptionvalueprefix": 43186
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  publisherid                           uniquename                     friendlyname
  ------------------------------------  -----------------------------  ----------------------------------
  00000001-0000-0000-0000-00000000005a  Cree38e                        CDS Default Publisher
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  publisherid,uniquename,friendlyname
  00000001-0000-0000-0000-00000000005a,Cree38e,CDS Default Publisher
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pp solution publisher list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"
  
  Date: 9/1/2023

  Property | Value
  ---------|-------
  publisherid | 00000001-0000-0000-0000-00000000005a
  uniquename | Cree38e
  friendlyname | CDS Default Publisher
  versionnumber | 1074060
  isreadonly | false
  description | null
  customizationprefix | cr6c3
  customizationoptionvalueprefix | 43186
  ```

  </TabItem>
</Tabs>
