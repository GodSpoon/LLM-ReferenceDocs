-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo report siteusagesitecounts

Gets the total number of files across all sites and the number of active files

## Usage

```sh
m365 spo report siteusagesitecounts [options]
```

## Options

```md definition-list
`-p, --period <period>`
: The length of time over which the report is aggregated. Supported values `D7`, `D30`, `D90`, `D180`.
```

<Global />

## Remarks

A file (user or system) is considered active if it has been saved, synced, modified, or shared within the specified time period.

:::info

This command supports only csv and json output.

:::

## Examples

Gets the total number of files across all sites and the number of active files for the last week

```sh
m365 spo report siteusagesitecounts --period D7
```

Gets the total number of files across all sites and the number of active files for the last week and exports the report data in the specified path in text format

```sh
m365 spo report siteusagesitecounts --period D7 --output text > "siteusagesitecounts.txt"
```

Gets the total number of files across all sites and the number of active files for the last week and exports the report data in the specified path in json format

```sh
m365 spo report siteusagesitecounts --period D7 --output json > "siteusagesitecounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2022-11-26",
      "Site Type": "All",
      "Total": "159",
      "Active": "2",
      "Report Date": "2022-11-26",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Site Type,Total,Active,Report Date,Report Period
  2022-11-26,All,159,2,2022-11-26,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Site Type,Total,Active,Report Date,Report Period
  2022-11-26,All,159,2,2022-11-26,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Site Type,Total,Active,Report Date,Report Period
  2023-05-04,All,33,3,2023-05-04,7
  ```

  </TabItem>
</Tabs>
