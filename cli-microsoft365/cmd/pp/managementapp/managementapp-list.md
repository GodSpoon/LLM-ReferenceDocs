-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp managementapp list

Lists management applications for Power Platform

## Usage

```sh
m365 pp managementapp list [options]
```

## Options

<Global />

## Examples

Lists management applications for Power Platform

```sh
m365 pp managementapp list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "applicationId":"31359c7f-bd7e-475c-86db-fdb8c937548e"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  applicationId
  ------------------------------------
  31359c7f-bd7e-475c-86db-fdb8c937548e
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  applicationId
  31359c7f-bd7e-475c-86db-fdb8c937548e
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pp managementapp list

  Date: 9/1/2023

  Property | Value
  ---------|-------
  applicationId | 31359c7f-bd7e-475c-86db-fdb8c937548e
  ```

  </TabItem>
</Tabs>
