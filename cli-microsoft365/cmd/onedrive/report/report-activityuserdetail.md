-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# onedrive report activityuserdetail

Gets details about OneDrive activity by user

## Usage

```sh
m365 onedrive report activityuserdetail [options]
```

## Options

```md definition-list
`-p, --period [period]`
: The length of time over which the report is aggregated. Supported values `D7`, `D30`, `D90`, `D180`.

`-d, --date [date]`
: The date for which you would like to view the users who performed any activity. Supported date format is YYYY-MM-DD. Specify the date or period, but not both`
```

<Global />

## Remarks

:::info

This command supports only csv and json output.

:::

## Examples

Gets details about OneDrive activity by user for the last week

```sh
m365 onedrive report activityuserdetail --period D7
```

Gets details about OneDrive activity by user for May 1, 2019

```sh
m365 onedrive report activityuserdetail --date 2019-05-01
```

Gets details about OneDrive activity by user for the last week and exports the report data in the specified path in text format

```sh
m365 onedrive report activityuserdetail --period D7 --output text > "onedriveactivityuserdetail.txt"
```

Gets details about OneDrive activity by user for the last week and exports the report data in the specified path in json format

```sh
m365 onedrive report activityuserdetail --period D7 --output json > "onedriveactivityuserdetail.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-05-20",
      "User Principal Name": "30B283368E548933B1D03A64A6B14A89",
      "Is Deleted": "False",
      "Deleted Date": "",
      "Last Activity Date": "2022-12-27",
      "Viewed Or Edited File Count": "0",
      "Synced File Count": "0",
      "Shared Internally File Count": "0",
      "Shared Externally File Count": "0",
      "Assigned Products": "MICROSOFT POWER APPS PLAN 2 TRIAL+POWER VIRTUAL AGENTS VIRAL TRIAL+MICROSOFT POWER AUTOMATE FREE+POWER BI (FREE)+OFFICE 365 E3 DEVELOPER",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,User Principal Name,Is Deleted,Deleted Date,Last Activity Date,Viewed Or Edited File Count,Synced File Count,Shared Internally File Count,Shared Externally File Count,Assigned Products,Report Period
  2023-05-20,30B283368E548933B1D03A64A6B14A89,False,,2022-12-27,0,0,0,0,MICROSOFT POWER APPS PLAN 2 TRIAL+POWER VIRTUAL AGENTS VIRAL TRIAL+MICROSOFT POWER AUTOMATE FREE+POWER BI (FREE)+OFFICE 365 E3 DEVELOPER,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,User Principal Name,Is Deleted,Deleted Date,Last Activity Date,Viewed Or Edited File Count,Synced File Count,Shared Internally File Count,Shared Externally File Count,Assigned Products,Report Period
  2023-05-20,30B283368E548933B1D03A64A6B14A89,False,,2022-12-27,0,0,0,0,MICROSOFT POWER APPS PLAN 2 TRIAL+POWER VIRTUAL AGENTS VIRAL TRIAL+MICROSOFT POWER AUTOMATE FREE+POWER BI (FREE)+OFFICE 365 E3 DEVELOPER,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,User Principal Name,Is Deleted,Deleted Date,Last Activity Date,Viewed Or Edited File Count,Synced File Count,Shared Internally File Count,Shared Externally File Count,Assigned Products,Report Period
  2023-05-20,30B283368E548933B1D03A64A6B14A89,False,,2022-12-27,0,0,0,0,MICROSOFT POWER APPS PLAN 2 TRIAL+POWER VIRTUAL AGENTS VIRAL TRIAL+MICROSOFT POWER AUTOMATE FREE+POWER BI (FREE)+OFFICE 365 E3 DEVELOPER,7
  ```

  </TabItem>
</Tabs>
