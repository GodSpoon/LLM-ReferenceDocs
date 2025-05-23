-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo sitedesign run list

Lists information about site designs applied to the specified site

## Usage

```sh
m365 spo sitedesign run list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site for which to list applied site designs

`-i, --siteDesignId [siteDesignId]`
: The ID of the site design for which to display information
```

<Global />

## Examples

List site designs applied to the specified site

```sh
m365 spo sitedesign run list --webUrl https://contoso.sharepoint.com/sites/team-a
```

List information about the specified site design applied to the specified site

```sh
m365 spo sitedesign run list --webUrl https://contoso.sharepoint.com/sites/team-a --siteDesignId 6ec3ca5b-d04b-4381-b169-61378556d76e
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "ActionTrigger": 0,
      "ID": "8d41a2b7-ffb9-487c-994a-d25cf1b74f6a",
      "InvokedBy": "John",
      "SiteDesignID": "00281728-3bc1-41d3-92b6-8fc493dcf4cc",
      "SiteDesignTitle": "Contoso team site",
      "SiteDesignVersion": 1,
      "SiteID": "5fc2ea61-7204-41be-9d05-d44f017f958b",
      "StartTime": "1687422166000",
      "WebID": "1c6a5768-89b1-4a68-8c85-9f8db4609bcf"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  ID                                    SiteDesignID                          SiteDesignTitle    StartTime
  ------------------------------------  ------------------------------------  -----------------  --------------------
  8d41a2b7-ffb9-487c-994a-d25cf1b74f6a  00281728-3bc1-41d3-92b6-8fc493dcf4cc  Contoso team site  2023-06-22, 10:22:46
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ActionTrigger,ID,InvokedBy,SiteDesignID,SiteDesignTitle,SiteDesignVersion,SiteID,StartTime,WebID
  0,8d41a2b7-ffb9-487c-994a-d25cf1b74f6a,John,00281728-3bc1-41d3-92b6-8fc493dcf4cc,Contoso team site,1,5fc2ea61-7204-41be-9d05-d44f017f958b,"2023-06-22, 10:22:46",1c6a5768-89b1-4a68-8c85-9f8db4609bcf
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo sitedesign run list --webUrl "https://contoso.sharepoint.com/teams/team1"

  Date: 2023-06-22

  ## 8d41a2b7-ffb9-487c-994a-d25cf1b74f6a

  Property | Value
  ---------|-------
  ActionTrigger | 0
  ID | 8d41a2b7-ffb9-487c-994a-d25cf1b74f6a
  InvokedBy | John
  SiteDesignID | 00281728-3bc1-41d3-92b6-8fc493dcf4cc
  SiteDesignTitle | Contoso team site
  SiteDesignVersion | 1
  SiteID | 5fc2ea61-7204-41be-9d05-d44f017f958b
  StartTime | 2023-06-22, 10:22:46
  WebID | 1c6a5768-89b1-4a68-8c85-9f8db4609bcf
  ```

  </TabItem>
</Tabs>

## More information

- SharePoint site design and site script overview: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)
