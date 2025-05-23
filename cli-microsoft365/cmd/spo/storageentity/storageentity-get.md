-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo storageentity get

Get details for the specified tenant property

## Usage

```sh
m365 spo storageentity get [options]
```

## Options

```md definition-list
`-k, --key <key>`
: Name of the tenant property to retrieve
```

<Global />

## Remarks

Tenant properties are stored in the app catalog site associated with the site to which you are currently connected. When retrieving the specified tenant property, SharePoint will automatically find the associated app catalog and try to retrieve the property from it.

## Examples

Show the value, description and comment of the _AnalyticsId_ tenant property

```sh
m365 spo storageentity get -k AnalyticsId
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Key": "AnalyticsId",
    "Value": "123",
    "Description": "Web analytics ID",
    "Comment": "Use on all sites"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Comment    : Use on all sites
  Description: Web analytics ID
  Key        : AnalyticsId
  Value      : 123
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Key,Value,Description,Comment
  AnalyticsId,123,Web analytics ID,Use on all sites
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo storageentity get --key "AnalyticsId"

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
