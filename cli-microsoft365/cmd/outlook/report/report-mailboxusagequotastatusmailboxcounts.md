-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# outlook report mailboxusagequotastatusmailboxcounts

Gets the count of user mailboxes in each quota category

## Usage

```sh
m365 outlook report mailboxusagequotastatusmailboxcounts [options]
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

Gets the count of user mailboxes in each quota category for the last week

```sh
m365 outlook report mailboxusagequotastatusmailboxcounts --period D7
```

Gets the count of user mailboxes in each quota category for the last week and exports the report data in the specified path in text format

```sh
m365 outlook report mailboxusagequotastatusmailboxcounts --period D7 --output text > "EXAMPLE_SECRET_VALUE_PLACEHOLDER"
```

Gets the count of user mailboxes in each quota category for the last week and exports the report data in the specified path in json format

```sh
m365 outlook report mailboxusagequotastatusmailboxcounts --period D7 --output json > "EXAMPLE_SECRET_VALUE_PLACEHOLDER"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-01-24",
      "Under Limit": "146",
      "Warning Issued": "0",
      "Send Prohibited": "0",
      "Send/Receive Prohibited": "0",
      "Indeterminate": "0",
      "Report Date": "2023-01-18",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  Report Refresh Date,Under Limit,Warning Issued,Send Prohibited,Send/Receive Prohibited,Indeterminate,Report Date,Report Period
  2023-01-24,146,0,0,0,0,2023-01-18,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Under Limit,Warning Issued,Send Prohibited,Send/Receive Prohibited,Indeterminate,Report Date,Report Period
  2023-01-24,146,0,0,0,0,2023-01-18,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Under Limit,Warning Issued,Send Prohibited,Send/Receive Prohibited,Indeterminate,Report Date,Report Period
  2023-01-24,146,0,0,0,0,2023-01-18,7
  ```

  </TabItem>
</Tabs>
