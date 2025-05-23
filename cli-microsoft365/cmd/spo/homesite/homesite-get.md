-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo homesite get

Gets information about the Home Site

## Usage

```sh
m365 spo homesite get [options]
```

## Options

<Global />

## Examples

Get information about the Home Site.

```sh
m365 spo homesite get
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "SiteId": "af80c11f-0138-4d72-bb37-514542c3aabb",
    "WebId": "6f90666d-b0e7-40c3-991f-4ab051d00a70",
    "LogoUrl": "https://contoso.sharepoint.com/sites/intra/siteassets/work.png",
    "Title": "Intranet",
    "Url": "https://contoso.sharepoint.com/sites/intra"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  LogoUrl: https://contoso.sharepoint.com/sites/intra/siteassets/work.png
  SiteId : af80c11f-0138-4d72-bb37-514542c3aabb
  Title  : Intranet
  Url    : https://contoso.sharepoint.com/sites/intra
  WebId  : 6f90666d-b0e7-40c3-991f-4ab051d00a70
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  SiteId,WebId,LogoUrl,Title,Url
  af80c11f-0138-4d72-bb37-514542c3aabb,6f90666d-b0e7-40c3-991f-4ab051d00a70,https://contoso.sharepoint.com/sites/intra/siteassets/work.png,Intranet,https://contoso.sharepoint.com/sites/intra
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo homesite get

  Date: 2/20/2023

  ## Intranet (https://contoso.sharepoint.com/sites/intra)

  Property | Value
  ---------|-------
  IsInDraftMode | false
  SiteId | af80c11f-0138-4d72-bb37-514542c3aabb
  WebId |6f90666d-b0e7-40c3-991f-4ab051d00a70
  LogoUrl | https://contoso.sharepoint.com/sites/intra/siteassets/work.png
  Title | Intranet
  Url | https://contoso.sharepoint.com/sites/intra
  ```

  </TabItem>
</Tabs>

## More information

- SharePoint home sites: a landing for your organization on the intelligent intranet: [https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/EXAMPLE_SECRET_VALUE_PLACEHOLDER/ba-p/621933](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/EXAMPLE_SECRET_VALUE_PLACEHOLDER/ba-p/621933)
