-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo site appcatalog list

List all site collection app catalogs within the tenant

## Usage

```sh
m365 spo site appcatalog list [options]
```

## Options

<Global />

## Remarks

:::info

To use this command you need to have at least read permissions on the SharePoint root site.

:::

## Examples

List all site collection app catalogs within the tenant

```sh
m365 spo site appcatalog list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "AbsoluteUrl": "https://contoso.sharepoint.com/sites/site1",
      "ErrorMessage": "Success",
      "SiteID": "9798e615-b586-455e-8486-84913f492c49"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  AbsoluteUrl                                          SiteID
  ---------------------------------------------------  ------------------------------------
  https://contoso.sharepoint.com/sites/site1           9798e615-b586-455e-8486-84913f492c49
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  AbsoluteUrl,SiteID
  https://contoso.sharepoint.com/sites/site1,9798e615-b586-455e-8486-84913f492c49
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo site appcatalog list

  Date: 2023-06-21

  Property | Value
  ---------|-------
  AbsoluteUrl | https://contoso.sharepoint.com/sites/site1
  SiteID | 9798e615-b586-455e-8486-84913f492c49
  ```

  </TabItem>
</Tabs>
