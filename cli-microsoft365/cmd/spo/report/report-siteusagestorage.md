-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo report siteusagestorage

Gets the trend of storage allocated and consumed during the reporting period

## Usage

```sh
m365 spo report siteusagestorage [options]
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

Gets the trend of storage allocated and consumed during the last week

```sh
m365 spo report siteusagestorage --period D7
```

Gets the trend of storage allocated and consumed during the last week and exports the report data in the specified path in text format

```sh
m365 spo report siteusagestorage --period D7 --output text > "siteusagestorage.txt"
```

Gets the trend of storage allocated and consumed during the last week and exports the report data in the specified path in json format

```sh
m365 spo report siteusagestorage --period D7 --output json > "siteusagestorage.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2022-11-26",
      "Site Type": "All",
      "Storage Used (Byte)": "2348104595",
      "Report Date": "2022-11-26",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Site Type,Storage Used (Byte),Report Date,Report Period
  2022-11-26,All,2348104595,2022-11-26,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Site Type,Storage Used (Byte),Report Date,Report Period
  2022-11-26,All,2348104595,2022-11-26,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Site Type,Storage Used (Byte),Report Date,Report Period
  2023-05-04,All,272942096,2023-05-04,7
  ```

  </TabItem>
</Tabs>
