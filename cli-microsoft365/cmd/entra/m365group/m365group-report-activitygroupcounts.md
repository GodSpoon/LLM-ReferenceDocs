-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra m365group report activitygroupcounts

Get the daily total number of groups and how many of them were active based on email conversations, Viva Engage posts, and SharePoint file activities.

## Usage

```sh
m365 entra m365group report activitygroupcounts [options]
```

## Options

```md definition-list
`-p, --period <period>`
: The length of time over which the report is aggregated. Supported values `D7`, `D30`, `D90`, `D180`.

`--outputFile [outputFile]`
: Path to the file where the Microsoft 365 Groups activities report should be stored in.
```

<Global />

## Remarks

:::info

This command supports only csv and json output.

:::

## Examples

Get the daily total number of groups and how many of them were active based on activities for the last week

```sh
m365 entra m365group report activitygroupcounts --period D7
```

Get the daily total number of groups and how many of them were active based on activities for the last week and exports the report data in the specified path in text format

```sh
m365 entra m365group report activitygroupcounts --period D7 --output text > "m365groupactivitygroupcounts.txt"
```

Get the daily total number of groups and how many of them were active based on activities for the last week and exports the report data in the specified path in json format

```sh
m365 entra m365group report activitygroupcounts --period D7 --output json > "m365groupactivitygroupcounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-05-31",
      "Total": "24",
      "Active": "0",
      "Report Date": "2023-05-31",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Total,Active,Report Date,Report Period
  2023-05-31,24,0,2023-05-31,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Total,Active,Report Date,Report Period
  2023-05-31,24,0,2023-05-31,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Total,Active,Report Date,Report Period
  2023-05-31,24,0,2023-05-31,7
  ```

  </TabItem>
</Tabs>
