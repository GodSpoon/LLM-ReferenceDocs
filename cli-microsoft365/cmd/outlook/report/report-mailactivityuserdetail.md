-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# outlook report mailactivityuserdetail

Gets details about email activity users have performed

## Usage

```sh
m365 outlook report mailactivityuserdetail [options]
```

## Remarks

:::info

This command supports only csv and json output.

:::

## Options

```md definition-list
`-p, --period [period]`
: The length of time over which the report is aggregated. Supported values `D7`, `D30`, `D90`, `D180`.

`-d, --date [date]`
: The date for which you would like to view the users who performed any activity. Supported date format is YYYY-MM-DD. Specify the date or period, but not both
```

<Global />

## Examples

Gets details about email activity users have performed for the last week

```sh
m365 outlook report mailactivityuserdetail --period D7
```

Gets details about email activity users have performed for May 1st, 2019

```sh
m365 outlook report mailactivityuserdetail --date 2019-05-01
```

Gets details about email activity users have performed for the last week and exports the report data in the specified path in text format

```sh
m365 outlook report mailactivityuserdetail --period D7 --output text > "mailactivityuserdetail.txt"
```

Gets details about email activity users have performed for the last week and exports the report data in the specified path in json format

```sh
m365 outlook report mailactivityuserdetail --period D7 --output json > "mailactivityuserdetail.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-01-24",
      "User Principal Name": "5535B4D580981B19AD1942C38063507F",
      "Display Name": "F8C53518381F605C8FBA65C52CB43A1D",
      "Is Deleted": "False",
      "Deleted Date": "",
      "Last Activity Date": "2022-11-29",
      "Send Count": "0",
      "Receive Count": "0",
      "Read Count": "0",
      "Meeting Created Count": "0",
      "Meeting Interacted Count": "0",
      "Assigned Products": "OFFICE 365 E5+MICROSOFT POWER AUTOMATE FREE+MICROSOFT POWER APPS PLAN 2 TRIAL+POWER BI (FREE)",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  Report Refresh Date,User Principal Name,Display Name,Is Deleted,Deleted Date,Last Activity Date,Send Count,Receive Count,Read Count,Meeting Created Count,Meeting Interacted Count,Assigned Products,Report Period
  2023-01-24,5535B4D580981B19AD1942C38063507F,F8C53518381F605C8FBA65C52CB43A1D,False,,2022-11-29,0,0,0,0,0,OFFICE 365 E5+MICROSOFT POWER AUTOMATE FREE+MICROSOFT POWER APPS PLAN 2 TRIAL+POWER BI (FREE),7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,User Principal Name,Display Name,Is Deleted,Deleted Date,Last Activity Date,Send Count,Receive Count,Read Count,Meeting Created Count,Meeting Interacted Count,Assigned Products,Report Period
  2023-01-24,5535B4D580981B19AD1942C38063507F,F8C53518381F605C8FBA65C52CB43A1D,False,,2022-11-29,0,0,0,0,0,OFFICE 365 E5+MICROSOFT POWER AUTOMATE FREE+MICROSOFT POWER APPS PLAN 2 TRIAL+POWER BI (FREE),7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,User Principal Name,Display Name,Is Deleted,Deleted Date,Last Activity Date,Send Count,Receive Count,Read Count,Meeting Created Count,Meeting Interacted Count,Assigned Products,Report Period
  2023-01-24,5535B4D580981B19AD1942C38063507F,F8C53518381F605C8FBA65C52CB43A1D,False,,2022-11-29,0,0,0,0,0,OFFICE 365 E5+MICROSOFT POWER AUTOMATE FREE+MICROSOFT POWER APPS PLAN 2 TRIAL+POWER BI (FREE),7
  ```

  </TabItem>
</Tabs>
