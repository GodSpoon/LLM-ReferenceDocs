-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# outlook report mailboxusagemailboxcount

Gets the total number of user mailboxes in your organization and how many are active each day of the reporting period.

## Usage

```sh
m365 outlook report mailboxusagemailboxcount [options]
```

## Options

```md definition-list
`-p, --period <period>`
: The length of time over which the report is aggregated. Supported values `D7`, `D30`, `D90`, `D180`.
```

<Global />

## Remarks

A mailbox is considered active if the user sent or read any email.

:::info

This command supports only csv and json output.

:::

## Examples

Gets the total number of user mailboxes in your organization and how many are active each day for the last week.

```sh
m365 outlook report mailboxusagemailboxcount --period D7
```

Gets the total number of user mailboxes in your organization and how many are active each day for the last week and exports the report data in the specified path in text format

```sh
m365 outlook report mailboxusagemailboxcount --period D7 --output text > "mailboxusagemailboxcount.txt"
```

Gets the total number of user mailboxes in your organization and how many are active each day for the last week and exports the report data in the specified path in json format

```sh
m365 outlook report mailboxusagemailboxcount --period D7 --output json > "mailboxusagemailboxcount.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-01-24",
      "Total": "146",
      "Active": "131",
      "Report Date": "2023-01-18",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  Report Refresh Date,Total,Active,Report Date,Report Period
  2023-01-24,146,131,2023-01-18,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Total,Active,Report Date,Report Period
  2023-01-24,146,131,2023-01-18,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Total,Active,Report Date,Report Period
  2023-01-24,146,131,2023-01-18,7
  ```

  </TabItem>
</Tabs>
