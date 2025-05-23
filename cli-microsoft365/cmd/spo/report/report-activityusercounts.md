-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo report activityusercounts

Gets the trend in the number of active users

## Usage

```sh
m365 spo report activityusercounts [options]
```

## Options

```md definition-list
`-p, --period <period>`
: The length of time over which the report is aggregated. Supported values `D7`, `D30`, `D90`, `D180`.
```

<Global />

## Remarks

A user is considered active if he or she has executed a file activity (save, sync, modify, or share) or visited a page within the specified time period

:::info

This command supports only csv and json output.

:::

## Examples

Gets the trend in the number of active users for the last week

```sh
m365 spo report activityusercounts --period D7
```

Gets the trend in the number of active users for the last week and exports the report data in the specified path in text format

```sh
m365 spo report activityusercounts --period D7 --output text > "activityusercounts.txt"
```

Gets the trend in the number of active users for the last week and exports the report data in the specified path in json format

```sh
m365 spo report activityusercounts --period D7 --output json > "activityusercounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2022-11-26",
      "Visited Page": "1",
      "Viewed Or Edited": "1",
      "Synced": "",
      "Shared Internally": "",
      "Shared Externally": "",
      "Report Date": "2022-11-26",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Visited Page,Viewed Or Edited,Synced,Shared Internally,Shared Externally,Report Date,Report Period
  2022-11-26,1,1,,,,2022-11-26,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Visited Page,Viewed Or Edited,Synced,Shared Internally,Shared Externally,Report Date,Report Period
  2022-11-26,1,1,,,,2022-11-26,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Visited Page,Viewed Or Edited,Synced,Shared Internally,Shared Externally,Report Date,Report Period
  2023-05-04,1,1,,,,2023-05-04,7
  ```

  </TabItem>
</Tabs>
