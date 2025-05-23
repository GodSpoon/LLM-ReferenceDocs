-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams report deviceusageuserdetail

Gets detail about Microsoft Teams device usage by user

## Usage

```sh
m365 teams report deviceusageuserdetail [options]
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

Gets information about Microsoft Teams device usage by user for the last week.

```sh
m365 teams report deviceusageuserdetail --period D7
```

Gets information about Microsoft Teams device usage by user for July 1, 2019.

```sh
m365 teams report deviceusageuserdetail --date 2019-07-01
```

Gets information about Microsoft Teams device usage by user for the last week and exports the report data in the specified path in text format.

```sh
m365 teams report deviceusageuserdetail --period D7 --output text > "deviceusageuserdetail.txt"
```

Gets information about Microsoft Teams device usage by user for the last week and exports the report data in the specified path in json format.

```sh
m365 teams report deviceusageuserdetail --period D7 --output json > "deviceusageuserdetail.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ``` json
  [
    {
      "Report Refresh Date": "2022-10-24",
      "User Id": "00000000-0000-0000-0000-000000000000",
      "User Principal Name": "77E5979DD60BA6EAA53E814DBEEEFA5F",
      "Last Activity Date": "",
      "Is Deleted": "False",
      "Deleted Date": "",
      "Used Web": "No",
      "Used Windows Phone": "No",
      "Used iOS": "No",
      "Used Mac": "No",
      "Used Android Phone": "No",
      "Used Windows": "No",
      "Used  Chrome OS": "No",
      "Used Linux": "No",
      "Is Licensed": "Yes",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ``` text
  Report Refresh Date,User Id,User Principal Name,Last Activity Date,Is Deleted,Deleted Date,Used Web,Used Windows Phone,Used iOS,Used Mac,Used Android Phone,Used Windows,Used  Chrome OS,Used Linux,Is Licensed,Report Period
  2022-10-24,00000000-0000-0000-0000-000000000000,77E5979DD60BA6EAA53E814DBEEEFA5F,,False,,No,No,No,No,No,No,No,No,Yes,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ``` text
  Report Refresh Date,User Id,User Principal Name,Last Activity Date,Is Deleted,Deleted Date,Used Web,Used Windows Phone,Used iOS,Used Mac,Used Android Phone,Used Windows,Used  Chrome OS,Used Linux,Is Licensed,Report Period
  2022-10-24,00000000-0000-0000-0000-000000000000,77E5979DD60BA6EAA53E814DBEEEFA5F,,False,,No,No,No,No,No,No,No,No,Yes,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,User Id,User Principal Name,Last Activity Date,Is Deleted,Deleted Date,Used Web,Used Windows Phone,Used iOS,Used Mac,Used Android Phone,Used Windows,Used  Chrome OS,Used Linux,Is Licensed,Report Period
  2022-10-24,00000000-0000-0000-0000-000000000000,77E5979DD60BA6EAA53E814DBEEEFA5F,,False,,No,No,No,No,No,No,No,No,Yes,7
  ```

  </TabItem>
</Tabs>
