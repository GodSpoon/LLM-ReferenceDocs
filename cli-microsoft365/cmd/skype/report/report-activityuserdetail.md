-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# skype report activityuserdetail

Gets details about Skype for Business activity by user

## Usage

```sh
m365 skype report activityuserdetail [options]
```

## Options

```md definition-list
`-p, --period [period]`
: The length of time over which the report is aggregated. Supported values `D7`, `D30`, `D90`, `D180`.

`-d, --date [date]`
: The date for which you would like to view the users who performed any activity. Supported date format is YYYY-MM-DD. Specify the date or period, but not both
```

<Global />

## Remarks

:::info

This command supports only csv and json output.

:::

## Examples

Gets details about Skype for Business activity by user for the last week

```sh
m365 skype report activityuserdetail --period D7
```

Gets details about Skype for Business activity by user for May 1, 2019

```sh
m365 skype report activityuserdetail --date 2019-05-01
```

Gets details about Skype for Business activity by user for the last week and exports the report data in the specified path in text format

```sh
m365 skype report activityuserdetail --period D7 --output text > "activityuserdetail.txt"
```

Gets details about Skype for Business activity by user for the last week and exports the report data in the specified path in json format

```sh
m365 skype report activityuserdetail --period D7 --output json > "activityuserdetail.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-01-25",
      "User Principal Name": "john.doe@contoso.com",
      "Is Deleted": "False",
      "Deleted Date": "",
      "Last Activity Date": "2021-03-22",
      "Total Peer-to-peer Session Count": "0",
      "Total Organized Conference Count": "0",
      "Total Participated Conference Count": "0",
      "Peer-to-peer Last Activity Date": "2021-03-22",
      "Organized Conference Last Activity Date": "2021-02-15",
      "Participated Conference Last Activity Date": "2021-02-15",
      "Peer-to-peer IM Count": "0",
      "Peer-to-peer Audio Count": "0",
      "Peer-to-peer Audio Minutes": "0",
      "Peer-to-peer Video Count": "0",
      "Peer-to-peer Video Minutes": "0",
      "Peer-to-peer App Sharing Count": "0",
      "Peer-to-peer File Transfer Count": "0",
      "Organized Conference IM Count": "0",
      "Organized Conference Audio/Video Count": "0",
      "Organized Conference Audio/Video Minutes": "0",
      "Organized Conference App Sharing Count": "0",
      "Organized Conference Web Count": "0",
      "Organized Conference Dial-in/out 3rd Party Count": "0",
      "Organized Conference Dial-in/out Microsoft Count": "0",
      "Organized Conference Dial-in Microsoft Minutes": "0",
      "Organized Conference Dial-out Microsoft Minutes": "0",
      "Participated Conference IM Count": "0",
      "Participated Conference Audio/Video Count": "0",
      "Participated Conference Audio/Video Minutes": "0",
      "Participated Conference App Sharing Count": "0",
      "Participated Conference Web Count": "0",
      "Participated Conference Dial-in/out 3rd Party Count": "0",
      "Assigned Products": "MICROSOFT 365 E5+MICROSOFT POWER APPS PLAN 2 TRIAL+POWER BI (FREE)+MICROSOFT POWER AUTOMATE FREE+POWER AUTOMATE PER USER PLAN",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  Report Refresh Date,User Principal Name,Is Deleted,Deleted Date,Last Activity Date,Total Peer-to-peer Session Count,Total Organized Conference Count,Total Participated Conference Count,Peer-to-peer Last Activity Date,Organized Conference Last Activity Date,Participated Conference Last Activity Date,Peer-to-peer IM Count,Peer-to-peer Audio Count,Peer-to-peer Audio Minutes,Peer-to-peer Video Count,Peer-to-peer Video Minutes,Peer-to-peer App Sharing Count,Peer-to-peer File Transfer Count,Organized Conference IM Count,Organized Conference Audio/Video Count,Organized Conference Audio/Video Minutes,Organized Conference App Sharing Count,Organized Conference Web Count,Organized Conference Dial-in/out 3rd Party Count,Organized Conference Dial-in/out Microsoft Count,Organized Conference Dial-in Microsoft Minutes,Organized Conference Dial-out Microsoft Minutes,Participated Conference IM Count,Participated Conference Audio/Video Count,Participated Conference Audio/Video Minutes,Participated Conference App Sharing Count,Participated Conference Web Count,Participated Conference Dial-in/out 3rd Party Count,Assigned Products,Report Period
  2023-01-25,john.doe@contoso.com,False,,2021-03-22,0,0,0,2021-03-22,2021-02-15,2021-02-15,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,MICROSOFT 365 E5+MICROSOFT POWER APPS PLAN 2 TRIAL+POWER BI (FREE)+MICROSOFT POWER AUTOMATE FREE+POWER AUTOMATE PER USER PLAN,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,User Principal Name,Is Deleted,Deleted Date,Last Activity Date,Total Peer-to-peer Session Count,Total Organized Conference Count,Total Participated Conference Count,Peer-to-peer Last Activity Date,Organized Conference Last Activity Date,Participated Conference Last Activity Date,Peer-to-peer IM Count,Peer-to-peer Audio Count,Peer-to-peer Audio Minutes,Peer-to-peer Video Count,Peer-to-peer Video Minutes,Peer-to-peer App Sharing Count,Peer-to-peer File Transfer Count,Organized Conference IM Count,Organized Conference Audio/Video Count,Organized Conference Audio/Video Minutes,Organized Conference App Sharing Count,Organized Conference Web Count,Organized Conference Dial-in/out 3rd Party Count,Organized Conference Dial-in/out Microsoft Count,Organized Conference Dial-in Microsoft Minutes,Organized Conference Dial-out Microsoft Minutes,Participated Conference IM Count,Participated Conference Audio/Video Count,Participated Conference Audio/Video Minutes,Participated Conference App Sharing Count,Participated Conference Web Count,Participated Conference Dial-in/out 3rd Party Count,Assigned Products,Report Period
  2023-01-25,john.doe@contoso.com,False,,2021-03-22,0,0,0,2021-03-22,2021-02-15,2021-02-15,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,MICROSOFT 365 E5+MICROSOFT POWER APPS PLAN 2 TRIAL+POWER BI (FREE)+MICROSOFT POWER AUTOMATE FREE+POWER AUTOMATE PER USER PLAN,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,User Principal Name,Is Deleted,Deleted Date,Last Activity Date,Total Peer-to-peer Session Count,Total Organized Conference Count,Total Participated Conference Count,Peer-to-peer Last Activity Date,Organized Conference Last Activity Date,Participated Conference Last Activity Date,Peer-to-peer IM Count,Peer-to-peer Audio Count,Peer-to-peer Audio Minutes,Peer-to-peer Video Count,Peer-to-peer Video Minutes,Peer-to-peer App Sharing Count,Peer-to-peer File Transfer Count,Organized Conference IM Count,Organized Conference Audio/Video Count,Organized Conference Audio/Video Minutes,Organized Conference App Sharing Count,Organized Conference Web Count,Organized Conference Dial-in/out 3rd Party Count,Organized Conference Dial-in/out Microsoft Count,Organized Conference Dial-in Microsoft Minutes,Organized Conference Dial-out Microsoft Minutes,Participated Conference IM Count,Participated Conference Audio/Video Count,Participated Conference Audio/Video Minutes,Participated Conference App Sharing Count,Participated Conference Web Count,Participated Conference Dial-in/out 3rd Party Count,Assigned Products,Report Period
  2023-01-25,john.doe@contoso.com,False,,2021-03-22,0,0,0,2021-03-22,2021-02-15,2021-02-15,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,MICROSOFT 365 E5+MICROSOFT POWER APPS PLAN 2 TRIAL+POWER BI (FREE)+MICROSOFT POWER AUTOMATE FREE+POWER AUTOMATE PER USER PLAN,7
  ```

  </TabItem>
</Tabs>
