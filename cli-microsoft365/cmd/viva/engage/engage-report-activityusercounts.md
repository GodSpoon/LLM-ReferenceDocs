-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage report activityusercounts

Gets the trends on the number of unique users who posted, read, and liked Viva Engage messages

## Usage

```sh
m365 viva engage report activityusercounts [options]
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

Gets the trends on the number of unique users who posted, read, and liked Viva Engage messages for the last week

```sh
m365 viva engage report activityusercounts --period D7
```

Gets the trends on the number of unique users who posted, read, and liked Viva Engage messages for the last week and exports the report data in the specified path in text format

```sh
m365 viva engage report activityusercounts --period D7 --output text > "activityusercounts.txt"
```

Gets the trends on the number of unique users who posted, read, and liked Viva Engage messages for the last week and exports the report data in the specified path in json format

```sh
m365 viva engage report activityusercounts --period D7 --output json > "activityusercounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2022-11-09",
      "Liked": "9",
      "Posted": "5",
      "Read": "64",
      "Report Date": "2022-11-09",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Liked,Posted,Read,Report Date,Report Period
  2022-11-09,9,5,64,2022-11-09,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Liked,Posted,Read,Report Date,Report Period
  2022-11-09,9,5,64,2022-11-09,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Liked,Posted,Read,Report Date,Report Period
  2022-11-09,9,5,64,2022-11-09,7
  ```

  </TabItem>
</Tabs>
