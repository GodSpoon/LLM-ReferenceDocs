-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage report deviceusageusercounts

Gets the number of daily users by device type

## Usage

```sh
m365 viva engage report deviceusageusercounts [options]
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

Gets the number of daily users by device type for the last week

```sh
m365 viva engage report deviceusageusercounts --period D7
```

Gets the number of daily users by device type for the last week and exports the report data in the specified path in text format

```sh
m365 viva engage report deviceusageusercounts --period D7 --output text > "deviceusageusercounts.txt"
```

Gets the number of daily users by device type for the last week and exports the report data in the specified path in json format

```sh
m365 viva engage report deviceusageusercounts --period D7 --output json > "deviceusageusercounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2022-11-09",
      "Web": "4",
      "Windows Phone": "5",
      "Android Phone": "6",
      "iPhone": "3",
      "iPad": "3",
      "Other": "60",
      "Report Date": "2022-11-09",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Web,Windows Phone,Android Phone,iPhone,iPad,Other,Report Date,Report Period
  2022-11-09,4,5,6,3,3,60,2022-11-09,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Web,Windows Phone,Android Phone,iPhone,iPad,Other,Report Date,Report Period
  2022-11-09,4,5,6,3,3,60,2022-11-09,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Web,Windows Phone,Android Phone,iPhone,iPad,Other,Report Date,Report Period
  2022-11-09,4,5,6,3,3,60,2022-11-09,7
  ```

  </TabItem>
</Tabs>
