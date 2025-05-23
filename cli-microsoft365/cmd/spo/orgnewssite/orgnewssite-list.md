-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo orgnewssite list

Lists all organizational news sites

## Usage

```sh
m365 spo orgnewssite list [options]
```

## Options

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

List all organizational news sites

```sh
m365 spo orgnewssite list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    "https://contoso.sharepoint.com/sites/contosoNews"
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  https://contoso.sharepoint.com/sites/contosoNews
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  https://contoso.sharepoint.com/sites/contosoNews
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  https://contoso.sharepoint.com/sites/contosoNews
  ```

  </TabItem>
</Tabs>
