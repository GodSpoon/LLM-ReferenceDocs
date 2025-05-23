-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo app instance list

Retrieve apps installed in a site

## Usage

```sh
m365 spo app instance list [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: URL of the site collection to retrieve the apps for.
```

<Global />

## Examples

Return a list of installed apps on the specified site.

```sh
m365 spo app instance list --siteUrl https://contoso.sharepoint.com/sites/site1
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "AppId": "03b4df10-320f-4d0f-8622-93822f9e0913",
      "AppPrincipalId": "i:0i.t|ms.sp.int|82e6f5ac-b560-4b2a-9966-fd6f05514a1c@de348bc7-1aeb-4406-8cb3-97db021cadb4",
      "AppSource": 2,
      "AppStatus": 4,
      "AppType": 3,
      "AssetId": null,
      "BaseTemplate": -1,
      "ChildCount": -1,
      "ContentMarket": null,
      "CustomSettingsUrl": null,
      "Description": "",
      "IsCorporateCatalogSite": false,
      "LastModified": "2022-07-15 06:00",
      "LastModifiedDate": "2022-07-15T13:00:30.113Z",
      "ProductId": "350f641f-cd1b-4274-819b-099f1ea66acc",
      "Target": "",
      "Thumbnail": "https://contoso.sharepoint.com/sites/site1/_layouts/15/images/spstorefrontappdefault.96x96x32.png",
      "Title": "helloworld-client-side-solution",
      "Version": ""
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Title                                           AppId
  ----------------------------------------------  ------------------------------------
  helloworld-client-side-solution                 03b4df10-320f-4d0f-8622-93822f9e0913
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  AppId,AppPrincipalId,AppSource,AppStatus,AppType,BaseTemplate,ChildCount,Description,IsCorporateCatalogSite,LastModified,LastModifiedDate,ProductId,Target,Thumbnail,Title,Version
  03b4df10-320f-4d0f-8622-93822f9e0913,i:0i.t|ms.sp.int|82e6f5ac-b560-4b2a-9966-fd6f05514a1c@de348bc7-1aeb-4406-8cb3-97db021cadb4,2,4,3,-1,-1,,,2022-07-15 06:00,2022-07-15T13:00:30.113Z,350f641f-cd1b-4274-819b-099f1ea66acc,,https://contoso.sharepoint.com/sites/site1/_layouts/15/images/spstorefrontappdefault.96x96x32.png,helloworld-client-side-solution,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo app instance list --siteUrl "https://contoso.sharepoint.com/sites/site1"

  Date: 10/2/2023

  ## helloworld-client-side-solution

  Property | Value
  ---------|-------
  AppId | 03b4df10-320f-4d0f-8622-93822f9e0913
  AppPrincipalId | i:0i.t\|ms.sp.int\|82e6f5ac-b560-4b2a-9966-fd6f05514a1c@de348bc7-1aeb-4406-8cb3-97db021cadb4
  AppSource | 2
  AppStatus | 4
  AppType | 3
  BaseTemplate | -1
  ChildCount | -1
  Description |
  IsCorporateCatalogSite | false
  LastModified | 2022-07-15 06:00
  LastModifiedDate | 2022-07-15T13:00:30.113Z
  ProductId | 350f641f-cd1b-4274-819b-099f1ea66acc
  Target |
  Thumbnail | https://contoso.sharepoint.com/sites/site1/\_layouts/15/images/spstorefrontappdefault.96x96x32.png
  Title | helloworld-client-side-solution
  Version |
  ```

  </TabItem>
</Tabs>
