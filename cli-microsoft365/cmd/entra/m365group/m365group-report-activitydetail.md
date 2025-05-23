-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra m365group report activitydetail

Get details about Microsoft 365 Groups activity by group.

## Usage

```sh
m365 entra m365group report activitydetail [options]
```

## Options

```md definition-list
`-p, --period [period]`
: The length of time over which the report is aggregated. Supported values `D7`, `D30`, `D90`, `D180`. Specify the `period` or `date`, but not both.

`-d, --date [date]`
: The date for which you would like to view the users who performed any activity. Supported date format is `YYYY-MM-DD`. Specify the `date` or `period`, but not both.

`--outputFile [outputFile]`
: Path to the file where the Microsoft 365 Groups activity by group report should be stored in
```

<Global />

## Remarks

:::info

This command supports only csv and json output.

:::

## Examples

Get details about Microsoft 365 Groups activity by group for the last week

```sh
m365 entra m365group report activitydetail --period D7
```

Get details about Microsoft 365 Groups activity by group for September 09, 2019

```sh
m365 entra m365group report activitydetail --date 2019-09-28
```

Get details about Microsoft 365 Groups activity by group for the last week and exports the report data in the specified path in text format

```sh
m365 entra m365group report activitydetail --period D7 --output text > "m365groupactivitydetail.txt"
```

Get details about Microsoft 365 Groups activity by group for the last week and exports the report data in the specified path in json format

```sh
m365 entra m365group report activitydetail --period D7 --output json > "m365groupactivitydetail.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-05-31",
      "Group Display Name": "7D3654B07E126BBD0D18174368FC243F",
      "Is Deleted": "False",
      "Owner Principal Name": "550802505126139905D733891825A254",
      "Last Activity Date": "",
      "Group Type": "Public",
      "Member Count": "1",
      "External Member Count": "0",
      "Exchange Received Email Count": "",
      "SharePoint Active File Count": "",
      "Yammer Posted Message Count": "",
      "Yammer Read Message Count": "",
      "Yammer Liked Message Count": "",
      "Exchange Mailbox Total Item Count": "5",
      "Exchange Mailbox Storage Used (Byte)": "203448",
      "SharePoint Total File Count": "0",
      "SharePoint Site Storage Used (Byte)": "1455831",
      "Group Id": "00000000-0000-0000-0000-000000000000",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Group Display Name,Is Deleted,Owner Principal Name,Last Activity Date,Group Type,Member Count,External Member Count,Exchange Received Email Count,SharePoint Active File Count,Yammer Posted Message Count,Yammer Read Message Count,Yammer Liked Message Count,Exchange Mailbox Total Item Count,Exchange Mailbox Storage Used (Byte),SharePoint Total File Count,SharePoint Site Storage Used (Byte),Group Id,Report Period
  2023-05-31,7D3654B07E126BBD0D18174368FC243F,False,550802505126139905D733891825A254,,Public,1,0,,,,,,5,203448,0,1455831,00000000-0000-0000-0000-000000000000,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Group Display Name,Is Deleted,Owner Principal Name,Last Activity Date,Group Type,Member Count,External Member Count,Exchange Received Email Count,SharePoint Active File Count,Yammer Posted Message Count,Yammer Read Message Count,Yammer Liked Message Count,Exchange Mailbox Total Item Count,Exchange Mailbox Storage Used (Byte),SharePoint Total File Count,SharePoint Site Storage Used (Byte),Group Id,Report Period
  2023-05-31,7D3654B07E126BBD0D18174368FC243F,False,550802505126139905D733891825A254,,Public,1,0,,,,,,5,203448,0,1455831,00000000-0000-0000-0000-000000000000,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Group Display Name,Is Deleted,Owner Principal Name,Last Activity Date,Group Type,Member Count,External Member Count,Exchange Received Email Count,SharePoint Active File Count,Yammer Posted Message Count,Yammer Read Message Count,Yammer Liked Message Count,Exchange Mailbox Total Item Count,Exchange Mailbox Storage Used (Byte),SharePoint Total File Count,SharePoint Site Storage Used (Byte),Group Id,Report Period
  2023-05-31,7D3654B07E126BBD0D18174368FC243F,False,550802505126139905D733891825A254,,Public,1,0,,,,,,5,203448,0,1455831,00000000-0000-0000-0000-000000000000,7
  ```

  </TabItem>
</Tabs>
