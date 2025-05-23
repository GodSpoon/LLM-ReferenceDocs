-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# outlook report mailappusageappsusercounts

Gets the count of unique users per email app

## Usage

```sh
m365 outlook report mailappusageappsusercounts [options]
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

Gets the count of unique users per email app for the last week

```sh
m365 outlook report mailappusageappsusercounts --period D7
```

Gets the count of unique users per email app for the last week and exports the report data in the specified path in text format

```sh
m365 outlook report mailappusageappsusercounts --period D7 --output text > "mailappusageappsusercounts.txt"
```

Gets the count of unique users per email app for the last week and exports the report data in the specified path in json format

```sh
m365 outlook report mailappusageappsusercounts --period D7 --output json > "mailappusageappsusercounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-01-25",
      "Mail For Mac": "",
      "Outlook For Mac": "6",
      "Outlook For Windows": "108",
      "Outlook For Mobile": "61",
      "Other For Mobile": "",
      "Outlook For Web": "2",
      "POP3 App": "",
      "IMAP4 App": "",
      "SMTP App": "",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  Report Refresh Date,Mail For Mac,Outlook For Mac,Outlook For Windows,Outlook For Mobile,Other For Mobile,Outlook For Web,POP3 App,IMAP4 App,SMTP App,Report Period
  2023-01-25,,6,108,61,,2,,,,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Mail For Mac,Outlook For Mac,Outlook For Windows,Outlook For Mobile,Other For Mobile,Outlook For Web,POP3 App,IMAP4 App,SMTP App,Report Period
  2023-01-25,,6,108,61,,2,,,,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Mail For Mac,Outlook For Mac,Outlook For Windows,Outlook For Mobile,Other For Mobile,Outlook For Web,POP3 App,IMAP4 App,SMTP App,Report Period
  2023-01-25,,6,108,61,,2,,,,7
  ```

  </TabItem>
</Tabs>
