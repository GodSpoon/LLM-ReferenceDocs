-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo tenant recyclebinitem list

Returns all modern and classic site collections in the tenant scoped recycle bin

## Usage

```sh
m365 spo tenant recyclebinitem list [options]
```

## Options

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Returns all modern and classic site collections in the tenant scoped recycle bin

```sh
m365 spo tenant recyclebinitem list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "_ObjectType_": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "_ObjectIdentity_": "ec4abfa0-00a9-6000-a541-3b7e72f845bb|908bed80-a04a-4433-b4a0-883d9847d110:1e852b49-bf4b-4ba5-bcd4-a8c4706c8ed4\
DeletedSiteProperties\
https%3a%2f%2fcontoso.sharepoint.com%2fteams%2fteam1",
      "DaysRemaining": 21,
      "DeletionTime": "/Date(2023,3,12,8,9,55,260)/",
      "SiteId": "/Guid(0031a568-a081-4157-a3ab-0946a9da7f6e)/",
      "Status": "Recycled",
      "StorageMaximumLevel": 1048576,
      "Url": "https://contoso.sharepoint.com/teams/team1",
      "UserCodeMaximumLevel": 300
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  DaysRemaining  DeletionTime                                                      Url
  -------------  ----------------------------------------------------------------  -------------------------------------------------
  21             Wed Apr 12 2023 08:09:55 GMT+0200 (Central European Summer Time)  https://contoso.sharepoint.com/teams/team1
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  _ObjectType_,_ObjectIdentity_,DaysRemaining,SiteId,Status,StorageMaximumLevel,Url,UserCodeMaximumLevel
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,"044bbfa0-b029-6000-c2a5-1f2125b3d4e5|908bed80-a04a-4433-b4a0-883d9847d110:1e852b49-bf4b-4ba5-bcd4-a8c4706c8ed4
  DeletedSiteProperties
  https%3a%2f%2fcontoso.sharepoint.com%2fteams%2fteam1",21,/Guid(0031a568-a081-4157-a3ab-0946a9da7f6e)/,Recycled,1048576,https://contoso.sharepoint.com/teams/team1,300
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo tenant recyclebinitem list

  Date: 2023-06-22

  ## https://contoso.sharepoint.com/teams/team1

  Property | Value
  ---------|-------
  \_ObjectType\_ | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  \_ObjectIdentity\_ | 7b4bbfa0-105c-6000-c2a5-147216eaad59\|908bed80-a04a-4433-b4a0-883d9847d110:1e852b49-bf4b-4ba5-bcd4-a8c4706c8ed4<br>DeletedSiteProperties<br>https%3a%2f%2fcontoso.sharepoint.com%2fteams%2fteam1
  DaysRemaining | 21
  SiteId | /Guid(0031a568-a081-4157-a3ab-0946a9da7f6e)/
  Status | Recycled
  StorageMaximumLevel | 1048576
  Url | https://contoso.sharepoint.com/teams/team1
  UserCodeMaximumLevel | 300
  ```

  </TabItem>
</Tabs>
