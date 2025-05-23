-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage report deviceusagedistributionusercounts

Gets the number of users by device type

## Usage

```sh
m365 viva engage report deviceusagedistributionusercounts [options]
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

Gets the number of users by device type for the last week

```sh
m365 viva engage report deviceusagedistributionusercounts --period D7
```

Gets the number of users by device type for the last week and exports the report data in the specified path in text format

```sh
m365 viva engage report deviceusagedistributionusercounts --period D7 --output text > "deviceusagedistributionusercounts.txt"
```

Gets the number of users by device type for the last week and exports the report data in the specified path in json format

```sh
m365 viva engage report deviceusagedistributionusercounts --period D7 --output json > "deviceusagedistributionusercounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2022-11-09",
      "Web": "77",
      "Windows Phone": "5",
      "Android Phone": "1",
      "iPhone": "7",
      "iPad": "6",
      "Other": "108",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Web,Windows Phone,Android Phone,iPhone,iPad,Other,Report Period
  2022-11-09,77,5,1,7,6,108,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Web,Windows Phone,Android Phone,iPhone,iPad,Other,Report Period
  2022-11-09,77,5,1,7,6,108,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Web,Windows Phone,Android Phone,iPhone,iPad,Other,Report Period
  2022-11-09,77,5,1,7,6,108,7
  ```

  </TabItem>
</Tabs>
