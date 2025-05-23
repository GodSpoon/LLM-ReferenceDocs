-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage report groupsactivitygroupcounts

Gets the total number of groups that existed and how many included group conversation activity

## Usage

```sh
m365 viva engage report groupsactivitygroupcounts [options]
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

Gets the total number of groups that existed and how many included group conversation activity for the last week

```sh
m365 viva engage report groupsactivitygroupcounts --period D7
```

Gets the total number of groups that existed and how many included group conversation activity for the last week and exports the report data in the specified path in text format

```sh
m365 viva engage report groupsactivitygroupcounts --period D7 --output text > "groupsactivitygroupcounts.txt"
```

Gets the total number of groups that existed and how many included group conversation activity for the last week and exports the report data in the specified path in json format

```sh
m365 viva engage report groupsactivitygroupcounts --period D7 --output json > "groupsactivitygroupcounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2022-11-04",
      "Total": "1",
      "Active": "0",
      "Report Date": "2022-11-04",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Total,Active,Report Date,Report Period
  2022-11-10,1,0,2022-11-10,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Total,Active,Report Date,Report Period
  2022-11-10,1,0,2022-11-10,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Total,Active,Report Date,Report Period
  2022-11-10,1,0,2022-11-10,7
  ```

  </TabItem>
</Tabs>
