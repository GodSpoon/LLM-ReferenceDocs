-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# outlook report mailappusageusercounts

Gets the count of unique users that connected to Exchange Online using any email app

## Usage

```sh
m365 outlook report mailappusageusercounts [options]
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

Gets the count of unique users that connected to Exchange Online using any email app for the last week

```sh
m365 outlook report mailappusageusercounts --period D7
```

Gets the count of unique users that connected to Exchange Online using any email app for the last week and exports the report data in the specified path in text format

```sh
m365 outlook report mailappusageusercounts --period D7 --output text > "mailappusageusercounts.txt"
```

Gets the count of unique users that connected to Exchange Online using any email app for the last week and exports the report data in the specified path in json format

```sh
m365 outlook report mailappusageusercounts --period D7 --output json > "mailappusageusercounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-01-25",
      "Mail For Mac": "",
      "Outlook For Mac": "2",
      "Outlook For Windows": "99",
      "Outlook For Mobile": "46",
      "Other For Mobile": "",
      "Outlook For Web": "",
      "POP3 App": "",
      "IMAP4 App": "",
      "SMTP App": "",
      "Report Date": "2023-01-19",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  Report Refresh Date,Mail For Mac,Outlook For Mac,Outlook For Windows,Outlook For Mobile,Other For Mobile,Outlook For Web,POP3 App,IMAP4 App,SMTP App,Report Date,Report Period
  2023-01-25,,2,99,46,,,,,,2023-01-19,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Mail For Mac,Outlook For Mac,Outlook For Windows,Outlook For Mobile,Other For Mobile,Outlook For Web,POP3 App,IMAP4 App,SMTP App,Report Date,Report Period
  2023-01-25,,2,99,46,,,,,,2023-01-19,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Mail For Mac,Outlook For Mac,Outlook For Windows,Outlook For Mobile,Other For Mobile,Outlook For Web,POP3 App,IMAP4 App,SMTP App,Report Date,Report Period
  2023-01-25,,2,99,46,,,,,,2023-01-19,7
  ```

  </TabItem>
</Tabs>
