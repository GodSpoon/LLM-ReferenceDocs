-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# tenant report activeusercounts

Gets the count of daily active users in the reporting period by product.

## Usage

```sh
m365 tenant report activeusercounts [options]
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

Gets the count of daily active users in the reporting period by product for the last week

```sh
m365 tenant report activeusercounts --period D7
```

Gets the count of daily active users in the reporting period by product for the last week and exports the report data in the specified path in text format

```sh
m365 tenant report activeusercounts --period D7 --output text > "activeusercounts.txt"
```

Gets the count of daily active users in the reporting period by product for the last week and exports the report data in the specified path in json format

```sh
m365 tenant report activeusercounts --period D7 --output json > "activeusercounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2022-10-25",
      "Office 365": "1",
      "Exchange": "5",
      "OneDrive": "4",
      "SharePoint": "3",
      "Skype For Business": "2",
      "Yammer": "3",
      "Teams": "1",
      "Report Date": "2022-10-19",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Office 365,Exchange,OneDrive,SharePoint,Skype For Business,Yammer,Teams,Report Date,Report Period
  2022-10-25,1,5,4,3,2,3,1,2022-10-19,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Office 365,Exchange,OneDrive,SharePoint,Skype For Business,Yammer,Teams,Report Date,Report Period
  2022-10-25,1,5,4,3,2,3,1,2022-10-19,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Office 365,Exchange,OneDrive,SharePoint,Skype For Business,Yammer,Teams,Report Date,Report Period
  2022-10-25,1,5,4,3,2,3,1,2022-10-19,7
  ```

  </TabItem>
</Tabs>
