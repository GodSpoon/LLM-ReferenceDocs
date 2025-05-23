-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo sitedesign task get

Gets information about the specified site design scheduled for execution

## Usage

```sh
m365 spo sitedesign task get [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The ID of the site design task to get information for
```

<Global />

## Examples

Get information about the specified site design scheduled for execution

```sh
m365 spo sitedesign task get --id 6ec3ca5b-d04b-4381-b169-61378556d76e
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "ID": "4ca76dd4-8a15-4012-99df-3b9375e9b62b",
    "LogonName": "i:0#.f|membership|john@contoso.onmicrosoft.com",
    "SiteDesignID": "00281728-3bc1-41d3-92b6-8fc493dcf4cc",
    "SiteDesignStore": 0,
    "SiteID": "5fc2ea61-7204-41be-9d05-d44f017f958b",
    "WebID": "1c6a5768-89b1-4a68-8c85-9f8db4609bcf"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  ID             : 4ca76dd4-8a15-4012-99df-3b9375e9b62b
  LogonName      : i:0#.f|membership|john@contoso.onmicrosoft.com
  SiteDesignID   : 00281728-3bc1-41d3-92b6-8fc493dcf4cc
  SiteDesignStore: 0
  SiteID         : 5fc2ea61-7204-41be-9d05-d44f017f958b
  WebID          : 1c6a5768-89b1-4a68-8c85-9f8db4609bcf
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ID,LogonName,SiteDesignID,SiteDesignStore,SiteID,WebID
  4ca76dd4-8a15-4012-99df-3b9375e9b62b,i:0#.f|membership|john@contoso.onmicrosoft.com,00281728-3bc1-41d3-92b6-8fc493dcf4cc,0,5fc2ea61-7204-41be-9d05-d44f017f958b,1c6a5768-89b1-4a68-8c85-9f8db4609bcf
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo sitedesign task get --id "4ca76dd4-8a15-4012-99df-3b9375e9b62b"

  Date: 2023-06-22

  ## 4ca76dd4-8a15-4012-99df-3b9375e9b62b

  Property | Value
  ---------|-------
  ID | 4ca76dd4-8a15-4012-99df-3b9375e9b62b
  LogonName | i:0#.f\|membership\|john@contoso.onmicrosoft.com
  SiteDesignID | 00281728-3bc1-41d3-92b6-8fc493dcf4cc
  SiteDesignStore | 0
  SiteID | 5fc2ea61-7204-41be-9d05-d44f017f958b
  WebID | 1c6a5768-89b1-4a68-8c85-9f8db4609bcf
  ```

  </TabItem>
</Tabs>

## More information

- SharePoint site design and site script overview: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)
