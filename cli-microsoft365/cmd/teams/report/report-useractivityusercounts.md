-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams report useractivityusercounts

Get the number of Microsoft Teams users by activity type. The activity types are number of teams chat messages, private chat messages, calls, or meetings

## Usage

```sh
m365 teams report useractivityusercounts [options]
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

Gets the number of Microsoft Teams users by activity type for the last week.

```sh
m365 teams report useractivityusercounts --period D7
```

Gets the number of Microsoft Teams users by activity type for the last week and exports the report data in the specified path in text format.

```sh
m365 teams report useractivityusercounts --period D7 --output text > "useractivityusercounts.txt"
```

Gets the number of Microsoft Teams users by activity type for the last week and exports the report data in the specified path in json format.

```sh
m365 teams report useractivityusercounts --period D7 --output json > "useractivityusercounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ``` json
  [
    {
      "Report Refresh Date": "2022-10-28",
      "Report Date": "2022-10-28",
      "Team Chat Messages": "0",
      "Private Chat Messages": "0",
      "Calls": "0",
      "Meetings": "0",
      "Other Actions": "0",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ``` text
  Report Refresh Date,Report Date,Team Chat Messages,Private Chat Messages,Calls,Meetings,Other Actions,Report Period
  2022-10-28,2022-10-28,0,0,0,0,0,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ``` text
  Report Refresh Date,Report Date,Team Chat Messages,Private Chat Messages,Calls,Meetings,Other Actions,Report Period
  2022-10-28,2022-10-28,0,0,0,0,0,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Report Date,Team Chat Messages,Private Chat Messages,Calls,Meetings,Other Actions,Report Period
  2022-10-28,2022-10-28,0,0,0,0,0,7
  ```

  </TabItem>
</Tabs>
