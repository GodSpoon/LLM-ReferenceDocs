-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# onedrive report usagefilecounts

Gets the total number of files across all sites and how many are active files

## Usage

```sh
m365 onedrive report usagefilecounts [options]
```

## Options

```md definition-list
`-p, --period <period>`
: The length of time over which the report is aggregated. Supported values `D7`, `D30`, `D90`, `D180`.
```

<Global />

## Remarks

A file is considered active if it has been saved, synced, modified, or shared within the specified time period.

:::info

This command supports only csv and json output.

:::

## Examples

Gets the total number of files across all sites and how many are active files for the last week

```sh
m365 onedrive report usagefilecounts --period D7
```

Gets the total number of files across all sites and how many are active files for the last week and exports the report data in the specified path in text format

```sh
m365 onedrive report usagefilecounts --period D7 --output text > "usagefilecounts.txt"
```

Gets the total number of files across all sites and how many are active files for the last week and exports the report data in the specified path in json format

```sh
m365 onedrive report usagefilecounts --period D7 --output json > "usagefilecounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-05-20",
      "Site Type": "All",
      "Total": "128",
      "Active": "0",
      "Report Date": "2023-05-20",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Site Type,Total,Active,Report Date,Report Period
  2023-05-20,All,128,0,2023-05-20,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Site Type,Total,Active,Report Date,Report Period
  2023-05-20,All,128,0,2023-05-20,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Site Type,Total,Active,Report Date,Report Period
  2023-05-20,All,128,0,2023-05-20,7
  ```

  </TabItem>
</Tabs>
