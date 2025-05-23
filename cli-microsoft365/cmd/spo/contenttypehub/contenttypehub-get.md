-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo contenttypehub get

Returns the URL of the SharePoint Content Type Hub of the Tenant

## Usage

```sh
m365 spo contenttypehub get [options]
```

## Options

<Global />

## Examples
  
Retrieve the Content Type Hub URL

```sh
m365 spo contenttypehub get
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "ContentTypePublishingHub": "https://contoso.sharepoint.com/sites/contentTypeHub"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  ContentTypePublishingHub: https://contoso.sharepoint.com/sites/contentTypeHub
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ContentTypePublishingHub
  https://contoso.sharepoint.com/sites/contentTypeHub
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo contenttypehub get

  Date: 10/2/2023

  Property | Value
  ---------|-------
  ContentTypePublishingHub | https://contoso.sharepoint.com/sites/contentTypeHub
  ```

  </TabItem>
</Tabs>
