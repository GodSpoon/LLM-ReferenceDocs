-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo storageentity list

Lists tenant properties stored on the specified SharePoint Online app catalog

## Usage

```sh
m365 spo storageentity list [options]
```

## Options

```md definition-list
`-u, --appCatalogUrl <appCatalogUrl>`
: URL of the app catalog site
```

<Global />

## Remarks

Tenant properties are stored in the app catalog site. To list all tenant properties, you have to specify the absolute URL of the app catalog site. If you specify an incorrect URL, or the site at the given URL is not an app catalog site, no properties will be retrieved.

## Examples

List all tenant properties stored in the _https://contoso.sharepoint.com/sites/appcatalog_ app catalog site

```sh
m365 spo storageentity list -u https://contoso.sharepoint.com/sites/appcatalog
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Key": "AnalyticsId",
      "Value": "123",
      "Description": "Web analytics ID",
      "Comment": "Use on all sites"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Key                                 Value                                                               Description                           Comment         
  ----------------------------------  ------------------------------------------------------------------  ------------------------------------  ----------------
  AnalyticsId                         123                                                                 Web analytics ID                      Use on all sites
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Key,Value,Description
  AnalyticsId,123,Web analytics ID
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo storageentity list --appCatalogUrl "https://contoso.sharepoint.com/sites/apps"

  Date: 2023-06-22

  Property | Value
  ---------|-------
  Key | AnalyticsId
  Value | 123
  Description | Web analytics ID
  Comment | Use on all sites
  ```

  </TabItem>
</Tabs>

## More information

- SharePoint Framework Tenant Properties: [https://learn.microsoft.com/sharepoint/dev/spfx/tenant-properties](https://learn.microsoft.com/sharepoint/dev/spfx/tenant-properties)
