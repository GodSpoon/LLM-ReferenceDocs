-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# context option list

List all options added to the context

## Usage

```sh
m365 context option list [options]
```

## Options

<Global />

## Examples

List all options added to the context

```sh
m365 context option list
```

## Response

The responses below are an example. The output may differ based on the contents of the context file

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "url": "https://contoso.sharepoint.com",
    "list": "list name"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  list: list name
  url : https://contoso.sharepoint.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  url,list
  https://contoso.sharepoint.com,list name
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # context option list

  Date: 7/2/2023

  ## https://contoso.sharepoint.com

  Property | Value
  ---------|-------
  url | https://contoso.sharepoint.com
  list | list name
  ```

  </TabItem>
</Tabs>
