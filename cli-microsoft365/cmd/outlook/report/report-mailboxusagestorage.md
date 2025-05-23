-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# outlook report mailboxusagestorage

Gets the amount of mailbox storage used in your organization

## Usage

```sh
m365 outlook report mailboxusagestorage [options]
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

Gets the amount of mailbox storage used in your organization for the last week

```sh
m365 outlook report mailboxusagestorage --period D7
```

Gets the amount of mailbox storage used in your organization for the last week and exports the report data in the specified path in text format

```sh
m365 outlook report mailboxusagestorage --period D7 --output text > "mailboxusagestorage.txt"
```

Gets the amount of mailbox storage used in your organization for the last week and exports the report data in the specified path in json format

```sh
m365 outlook report mailboxusagestorage --period D7 --output json > "mailboxusagestorage.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-01-24",
      "Storage Used (Byte)": "791481624264",
      "Report Date": "2023-01-18",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  Report Refresh Date,Storage Used (Byte),Report Date,Report Period
  2023-01-24,791481624264,2023-01-18,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Storage Used (Byte),Report Date,Report Period
  2023-01-24,791481624264,2023-01-18,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Storage Used (Byte),Report Date,Report Period
  2023-01-24,791481624264,2023-01-18,7
  ```

  </TabItem>
</Tabs>
