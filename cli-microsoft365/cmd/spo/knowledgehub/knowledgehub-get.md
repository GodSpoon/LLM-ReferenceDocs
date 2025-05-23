-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo knowledgehub get

Gets the Knowledge Hub Site URL for your tenant

## Usage

```sh
m365 spo knowledgehub get [options]
```

## Options

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Gets the Knowledge Hub Site URL for your tenant.

```sh
m365 spo knowledgehub get
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  "https://contoso.sharepoint.com"
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  https://contoso.sharepoint.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  https://contoso.sharepoint.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  https://contoso.sharepoint.com
  ```

  </TabItem>
</Tabs>
