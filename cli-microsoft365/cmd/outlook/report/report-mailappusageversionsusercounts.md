-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# outlook report mailappusageversionsusercounts

Gets the count of unique users by Outlook desktop version.

## Usage

```sh
m365 outlook report mailappusageversionsusercounts [options]
```

## Remarks

:::info

This command supports only csv and json output.

:::

## Options

```md definition-list
`-p, --period <period>`
: The length of time over which the report is aggregated. Supported values `D7`, `D30`, `D90`, `D180`.
```

<Global />

## Examples

Gets the count of unique users by Outlook desktop version for the last week

```sh
m365 outlook report mailappusageversionsusercounts --period D7
```

Gets the count of unique users by Outlook desktop version for the last week and exports the report data in the specified path in text format

```sh
m365 outlook report mailappusageversionsusercounts --period D7 --output text > "mailappusageversionsusercounts.txt"
```

Gets the count of unique users by Outlook desktop version for the last week and exports the report data in the specified path in json format

```sh
m365 outlook report mailappusageversionsusercounts --period D7 --output json > "mailappusageversionsusercounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-01-25",
      "Outlook 2016": "",
      "Outlook 2013": "",
      "Outlook 2010": "",
      "Outlook 2007": "",
      "Undetermined": "",
      "Report Period": "7",
      "Outlook M365": "108",
      "Outlook 2019": ""
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  Report Refresh Date,Outlook 2016,Outlook 2013,Outlook 2010,Outlook 2007,Undetermined,Report Period,Outlook M365,Outlook 2019
  2023-01-25,,,,,,7,108,
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Outlook 2016,Outlook 2013,Outlook 2010,Outlook 2007,Undetermined,Report Period,Outlook M365,Outlook 2019
  2023-01-25,,,,,,7,108,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Outlook 2016,Outlook 2013,Outlook 2010,Outlook 2007,Undetermined,Report Period,Outlook M365,Outlook 2019
  2023-01-25,,,,,,7,108,
  ```

  </TabItem>
</Tabs>
