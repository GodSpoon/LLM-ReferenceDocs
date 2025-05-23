-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams report deviceusageusercounts

Get the number of Microsoft Teams daily unique users by device type

## Usage

```sh
m365 teams report deviceusageusercounts [options]
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

Gets the number of Microsoft Teams daily unique users by device type for the last week.

```sh
m365 teams report deviceusageusercounts --period D7
```

Gets the number of Microsoft Teams daily unique users by device type for the last week and exports the report data in the specified path in text format.

```sh
m365 teams report deviceusageusercounts --period D7 --output text > "deviceusageusercounts.txt"
```

Gets the number of Microsoft Teams daily unique users by device type for the last week and exports the report data in the specified path in json format.

```sh
m365 teams report deviceusageusercounts --period D7 --output json > "deviceusageusercounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ``` json
  [
    {
      "Report Refresh Date": "2022-10-24",
      "Web": "0",
      "Windows Phone": "0",
      "Android Phone": "0",
      "iOS": "0",
      "Mac": "0",
      "Windows": "1",
      "Chrome OS": "0",
      "Linux": "0",
      "Report Date": "2022-10-24",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ``` text
  Report Refresh Date,Web,Windows Phone,Android Phone,iOS,Mac,Windows,Chrome OS,Linux,Report Date,Report Period
  2022-10-24,0,0,0,0,0,1,0,0,2022-10-24,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ``` text
  Report Refresh Date,Web,Windows Phone,Android Phone,iOS,Mac,Windows,Chrome OS,Linux,Report Date,Report Period
  2022-10-24,0,0,0,0,0,1,0,0,2022-10-24,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Web,Windows Phone,Android Phone,iOS,Mac,Windows,Chrome OS,Linux,Report Date,Report Period
  2022-10-24,0,0,0,0,0,1,0,0,2022-10-24,7
  ```

  </TabItem>
</Tabs>
