-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo tenant appcatalogurl get

Gets the URL of the tenant app catalog

## Usage

```sh
m365 spo tenant appcatalogurl get [options]
```

## Options

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Get the URL of the tenant app catalog

```sh
m365 spo tenant appcatalogurl get
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  "https://contoso.sharepoint.com/sites/apps"
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  https://contoso.sharepoint.com/sites/apps
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  https://contoso.sharepoint.com/sites/apps
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  https://contoso.sharepoint.com/sites/apps
  ```

  </TabItem>
</Tabs>
