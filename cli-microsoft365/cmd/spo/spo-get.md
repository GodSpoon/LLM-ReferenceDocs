-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo get

Gets the context URL for the root SharePoint site collection and SharePoint tenant admin site

## Usage

```sh
m365 spo get [options]
```

## Options

<Global />

## Remarks

CLI for Microsoft 365 automatically discovers the URL of the root SharePoint site collection/SharePoint tenant admin site (whichever is needed to run the particular command). Using this command you can see which URLs the CLI has discovered.

## Examples

Get the context URL for the root SharePoint site collection and SharePoint tenant admin site

```sh
m365 spo get --output json
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "SpoUrl": "https://contoso.sharepoint.com"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  SpoUrl: https://contoso.sharepoint.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  SpoUrl
  https://contoso.sharepoint.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo get 

  Date: 4/10/2023

  Property | Value
  ---------|-------
  SpoUrl | https://contoso.sharepoint.com
  ```

  </TabItem>
</Tabs>
