-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo homesite list

Lists all home sites

## Usage

```sh
m365 spo homesite list [options]
```

## Alias

```sh
m365 spo tenant homesite list [options]
```

## Options

<Global />

## Examples

List all home sites

```sh
m365 spo homesite list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Audiences": [
        {
          "Email": "ColumnSearchable@contoso.onmicrosoft.com",
          "Id": "978b5280-4f80-47ea-a1db-b0d1d2fb1ba4",
          "Title": "ColumnSearchable Members"
        }
      ],
      "IsInDraftMode": false,
      "IsVivaBackendSite": false,
      "SiteId": "431d7819-4aaf-49a1-b664-b2fe9e609b63",
      "TargetedLicenseType": 2,
      "Title": "The Landing",
      "Url": "https://contoso.sharepoint.com/sites/TheLanding",
      "VivaConnectionsDefaultStart": true,
      "WebId": "626c1724-8ac8-45d5-af87-c07c752fab75"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Url                                              Title        
  -----------------------------------------------  -----------
  https://contoso.sharepoint.com/sites/TheLanding  The Landing       
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  IsInDraftMode,IsVivaBackendSite,SiteId,TargetedLicenseType,Title,Url,VivaConnectionsDefaultStart,WebId
  0,0,431d7819-4aaf-49a1-b664-b2fe9e609b63,2,The Landing,https://contoso.sharepoint.com/sites/TheLanding,1,626c1724-8ac8-45d5-af87-c07c752fab75
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo homesite list 

  Date: 11/18/2024

  Property | Value
  ---------|-------
  IsInDraftMode | false
  IsVivaBackendSite | false
  SiteId | 431d7819-4aaf-49a1-b664-b2fe9e609b63
  TargetedLicenseType | 2
  Title | The Landing
  Url | https://contoso.sharepoint.com/sites/TheLanding
  VivaConnectionsDefaultStart | true
  WebId | 626c1724-8ac8-45d5-af87-c07c752fab75
  ```
  </TabItem>
</Tabs>

## More information

- SharePoint home sites [Viva Connections set up](https://learn.microsoft.com/en-us/viva/connections/set-up-admin-center)
