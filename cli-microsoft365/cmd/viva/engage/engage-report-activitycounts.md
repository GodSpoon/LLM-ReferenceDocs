-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage report activitycounts

Gets the trends on the amount of Viva Engage activity in your organization by how many messages were posted, read, and liked

## Usage

```sh
m365 viva engage report activitycounts [options]
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

Gets the trends on the amount of Viva Engage activity in your organization by how many messages were posted, read, and liked for the last week

```sh
m365 viva engage report activitycounts --period D7
```

Gets the trends on the amount of Viva Engage activity in your organization by how many messages were posted, read, and liked for the last week and exports the report data in the specified path in text format

```sh
m365 viva engage report activitycounts --period D7 --output text > "activitycounts.txt"
```

Gets the trends on the amount of Viva Engage activity in your organization by how many messages were posted, read, and liked for the last week and exports the report data in the specified path in json format

```sh
m365 viva engage report activitycounts --period D7 --output json > "activitycounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2022-11-09",
      "Liked": "12",
      "Posted": "6",
      "Read": "435",
      "Report Date": "2022-11-09",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Liked,Posted,Read,Report Date,Report Period
  2022-11-09,12,6,435,2022-11-09,90
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Liked,Posted,Read,Report Date,Report Period
  2022-11-09,12,6,435,2022-11-09,90
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Liked,Posted,Read,Report Date,Report Period
  2022-11-09,12,6,435,2022-11-09,90
  ```

  </TabItem>
</Tabs>
