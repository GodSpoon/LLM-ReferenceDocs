-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra m365group report activitystorage

Get the total storage used across all group mailboxes and group sites

## Usage

```sh
m365 entra m365group report activitystorage [options]
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

Get the total storage used across all group mailboxes and group sites for the last week

```sh
m365 entra m365group report activitystorage --period D7
```

Get the total storage used across all group mailboxes and group sites for the last week and exports the report data in the specified path in text format

```sh
m365 entra m365group report activitystorage --period D7 --output text > "m365groupactivitystorage.txt"
```

Get the total storage used across all group mailboxes and group sites for the last week and exports the report data in the specified path in json format

```sh
m365 entra m365group report activitystorage --period D7 --output json > "m365groupactivitystorage.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-05-31",
      "Mailbox Storage Used (Byte)": "37070516",
      "Site Storage Used (Byte)": "6521772595",
      "Report Date": "2023-05-31",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Mailbox Storage Used (Byte),Site Storage Used (Byte),Report Date,Report Period
  2023-05-31,37070516,6521772595,2023-05-31,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Mailbox Storage Used (Byte),Site Storage Used (Byte),Report Date,Report Period
  2023-05-31,37070516,6521772595,2023-05-31,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Mailbox Storage Used (Byte),Site Storage Used (Byte),Report Date,Report Period
  2023-05-31,37070516,6521772595,2023-05-31,7
  ```

  </TabItem>
</Tabs>
