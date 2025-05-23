-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# onedrive report usageaccountcounts

Gets the trend in the number of active OneDrive for Business sites

## Usage

```sh
m365 onedrive report usageaccountcounts [options]
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

## Remarks

Any site on which users viewed, modified, uploaded, downloaded, shared, or synced files is considered an active site

## Examples

Gets the trend in the number of active OneDrive for Business sites for the last week

```sh
m365 onedrive report usageaccountcounts --period D7
```

Gets the trend in the number of active OneDrive for Business sites for the last week and exports the report data in the specified path in text format

```sh
m365 onedrive report usageaccountcounts --period D7 --output text > "usageaccountcounts.txt"
```

Gets the trend in the number of active OneDrive for Business sites for the last week and exports the report data in the specified path in json format

```sh
m365 onedrive report usageaccountcounts --period D7 --output json > "usageaccountcounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-05-20",
      "Site Type": "All",
      "Total": "1",
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
  2023-05-20,All,1,0,2023-05-20,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Site Type,Total,Active,Report Date,Report Period
  2023-05-20,All,1,0,2023-05-20,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Site Type,Total,Active,Report Date,Report Period
  2023-05-20,All,1,0,2023-05-20,7
  ```

  </TabItem>
</Tabs>
