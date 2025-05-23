-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# skype report activityusercounts

Gets the trends on how many unique users organized and participated in conference sessions held in your organization through Skype for Business. The report also includes the number of peer-to-peer sessions

## Usage

```sh
m365 skype report activityusercounts [options]
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

Gets the trends on how many unique users organized and participated in conference sessions held in your organization through Skype for Business. The report also includes the number of peer-to-peer sessions for the last week

```sh
m365 skype report activityusercounts --period D7
```

Gets the trends on how many unique users organized and participated in conference sessions held in your organization through Skype for Business. The report also includes the number of peer-to-peer sessions for the last week and exports the report data in the specified path in text format

```sh
m365 skype report activityusercounts --period D7 --output text > "activityusercounts.txt"
```

Gets the trends on how many unique users organized and participated in conference sessions held in your organization through Skype for Business. The report also includes the number of peer-to-peer sessions for the last week and exports the report data in the specified path in json format

```sh
m365 skype report activityusercounts --period D7 --output json > "activityusercounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-01-25",
      "Report Date": "2023-01-19",
      "Report Period": "7",
      "Peer-to-peer": "0",
      "Organized": "0",
      "Participated": "0"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  Report Refresh Date,Report Date,Report Period,Peer-to-peer,Organized,Participated
  2023-01-25,2023-01-19,7,0,0,0
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Report Date,Report Period,Peer-to-peer,Organized,Participated
  2023-01-25,2023-01-19,7,0,0,0
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Report Date,Report Period,Peer-to-peer,Organized,Participated
  2023-01-25,2023-01-19,7,0,0,0
  ```

  </TabItem>
</Tabs>
