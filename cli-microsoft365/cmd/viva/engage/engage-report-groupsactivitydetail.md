-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage report groupsactivitydetail

Gets details about Viva Engage groups activity by group

## Usage

```sh
m365 viva engage report groupsactivitydetail [options]
```

## Options

```md definition-list
`-p, --period [period]`
: The length of time over which the report is aggregated. Supported values `D7`, `D30`, `D90`, `D180`.

`-d, --date [date]`
: The date for which you would like to view the users who performed any activity. Supported date format is `YYYY-MM-DD`.
```

<Global />

## Remarks

As this report is only available for the past 28 days, date parameter value should be a date from that range.

:::info

This command supports only csv and json output.

:::

## Examples

Gets details about Viva Engage groups activity by group for the last week

```sh
m365 viva engage report groupsactivitydetail --period D7
```

Gets details about Viva Engage groups activity by group for July 1, 2019

```sh
m365 viva engage report groupsactivitydetail --date 2019-07-01
```

Gets details about Viva Engage groups activity by group for the last week and exports the report data in the specified path in text format

```sh
m365 viva engage report groupsactivitydetail --period D7 --output text > "groupsactivitydetail.txt"
```

Gets details about Viva Engage groups activity by group for the last week and exports the report data in the specified path in json format

```sh
m365 viva engage report groupsactivitydetail --period D7 --output json > "groupsactivitydetail.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2022-11-10",
      "Group Display Name": "7D3654B07E126BBD0D18174368FC243F",
      "Is Deleted": "False",
      "Owner Principal Name": "",
      "Last Activity Date": "",
      "Group Type": "public",
      "Office 365 Connected": "No",
      "Member Count": "3",
      "Posted Count": "",
      "Read Count": "",
      "Liked Count": "",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Group Display Name,Is Deleted,Owner Principal Name,Last Activity Date,Group Type,Office 365 Connected,Member Count,Posted Count,Read Count,Liked Count,Report Period
  2022-11-10,7D3654B07E126BBD0D18174368FC243F,False,,,public,No,3,,,,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Group Display Name,Is Deleted,Owner Principal Name,Last Activity Date,Group Type,Office 365 Connected,Member Count,Posted Count,Read Count,Liked Count,Report Period
  2022-11-10,7D3654B07E126BBD0D18174368FC243F,False,,,public,No,3,,,,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Group Display Name,Is Deleted,Owner Principal Name,Last Activity Date,Group Type,Office 365 Connected,Member Count,Posted Count,Read Count,Liked Count,Report Period
  2022-11-10,7D3654B07E126BBD0D18174368FC243F,False,,,public,No,3,,,,7
  ```

  </TabItem>
</Tabs>
