-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# tenant report servicesusercounts

Gets the count of users by activity type and service.

## Usage

```sh
m365 tenant report servicesusercounts [options]
```

## Options

```md definition-list
`-p, --period <period>`
: The length of time over which the report is aggregated. Supported values `D7`, `D30`, `D90`, `D180`.
```

<Global />

## Remarks

:::info

This command supports only csv and json output.

:::

## Examples

Gets the count of users by activity type and service for the last week

```sh
m365 tenant report servicesusercounts --period D7
```

Gets the count of users by activity type and service for the last week and exports the report data in the specified path in text format

```sh
m365 tenant report servicesusercounts --period D7 --output text > "servicesusercounts.txt"
```

Gets the count of users by activity type and service for the last week and exports the report data in the specified path in json format

```sh
m365 tenant report servicesusercounts --period D7 --output json > "servicesusercounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2022-10-23",
      "Exchange Active": "1",
      "Exchange Inactive": "23",
      "OneDrive Active": "1",
      "OneDrive Inactive": "23",
      "SharePoint Active": "1",
      "SharePoint Inactive": "23",
      "Skype For Business Active": "0",
      "Skype For Business Inactive": "24",
      "Yammer Active": "0",
      "Yammer Inactive": "24",
      "Teams Active": "1",
      "Teams Inactive": "23",
      "Office 365 Active": "2",
      "Office 365 Inactive": "22",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Exchange Active,Exchange Inactive,OneDrive Active,OneDrive Inactive,SharePoint Active,SharePoint Inactive,Skype For Business Active,Skype For Business Inactive,Yammer Active,Yammer Inactive,Teams Active,Teams Inactive,Office 365 Active,Office 365 Inactive,Report Period
  2022-10-23,1,23,1,23,1,23,0,24,0,24,1,23,2,22,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Exchange Active,Exchange Inactive,OneDrive Active,OneDrive Inactive,SharePoint Active,SharePoint Inactive,Skype For Business Active,Skype For Business Inactive,Yammer Active,Yammer Inactive,Teams Active,Teams Inactive,Office 365 Active,Office 365 Inactive,Report Period
  2022-10-23,1,23,1,23,1,23,0,24,0,24,1,23,2,22,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Exchange Active,Exchange Inactive,OneDrive Active,OneDrive Inactive,SharePoint Active,SharePoint Inactive,Skype For Business Active,Skype For Business Inactive,Yammer Active,Yammer Inactive,Teams Active,Teams Inactive,Office 365 Active,Office 365 Inactive,Report Period
  2022-10-23,1,23,1,23,1,23,0,24,0,24,1,23,2,22,7
  ```

  </TabItem>
</Tabs>
