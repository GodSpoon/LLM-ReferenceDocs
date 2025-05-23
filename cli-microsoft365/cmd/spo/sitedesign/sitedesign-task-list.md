-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo sitedesign task list

Lists site designs scheduled for execution on the specified site

## Usage

```sh
m365 spo sitedesign task list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site for which to list site designs scheduled for execution
```

<Global />

## Examples

List site designs scheduled for execution on the specified site

```sh
m365 spo sitedesign task list --webUrl https://contoso.sharepoint.com/sites/team-a
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "ID": "378ba758-cd39-4221-8d63-ff5de9ddac80",
      "LogonName": "i:0#.f|membership|john@contoso.onmicrosoft.com",
      "SiteDesignID": "00281728-3bc1-41d3-92b6-8fc493dcf4cc",
      "SiteDesignStore": 0,
      "SiteID": "5fc2ea61-7204-41be-9d05-d44f017f958b",
      "WebID": "1c6a5768-89b1-4a68-8c85-9f8db4609bcf"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  ID                                    SiteDesignID                          LogonName
  ------------------------------------  ------------------------------------  ---------------------------------------------
  d35cee75-19b5-4575-9ddb-e4c37e619095  00281728-3bc1-41d3-92b6-8fc493dcf4cc  i:0#.f|membership|john@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ID,LogonName,SiteDesignID,SiteDesignStore,SiteID,WebID
  573e1244-9f09-4969-9299-6a4feb4aaeb5,i:0#.f|membership|john@contoso.onmicrosoft.com,00281728-3bc1-41d3-92b6-8fc493dcf4cc,0,5fc2ea61-7204-41be-9d05-d44f017f958b,1c6a5768-89b1-4a68-8c85-9f8db4609bcf
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo sitedesign task list --webUrl "https://contoso.sharepoint.com/teams/team1"

  Date: 2023-06-22

  ## d35cee75-19b5-4575-9ddb-e4c37e619095

  Property | Value
  ---------|-------
  ID | d35cee75-19b5-4575-9ddb-e4c37e619095
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
