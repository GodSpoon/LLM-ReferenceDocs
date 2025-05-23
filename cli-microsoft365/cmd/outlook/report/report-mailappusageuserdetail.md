-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# outlook report mailappusageuserdetail

Gets details about which activities users performed on the various email apps

## Usage

```sh
m365 outlook report mailappusageuserdetail [options]
```

## Remarks

:::info

This command supports only csv and json output.

:::

## Options

```md definition-list
`-p, --period [period]`
: The length of time over which the report is aggregated. Supported values `D7`, `D30`, `D90`, `D180`.

`-d, --date [date]`
: The date for which you would like to view the users who performed any activity. Supported date format is YYYY-MM-DD. Specify the date or period, but not both
```

<Global />

## Examples

Gets details about which activities users performed on the various email apps for the last week

```sh
m365 outlook report mailappusageuserdetail --period D7
```

Gets details about which activities users performed on the various email apps for May 1st, 2019

```sh
m365 outlook report mailappusageuserdetail --date 2019-05-01
```

Gets details about which activities users performed on the various email apps for the last week and exports the report data in the specified path in text format

```sh
m365 outlook report mailappusageuserdetail --period D7 --output text > "mailappusageuserdetail.txt"
```

Gets details about which activities users performed on the various email apps for the last week and exports the report data in the specified path in json format

```sh
m365 outlook report mailappusageuserdetail --period D7 --output json > "mailappusageuserdetail.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-01-25",
      "User Principal Name": "john.doe@contoso.com",
      "Display Name": "John Doe",
      "Is Deleted": "False",
      "Deleted Date": "",
      "Last Activity Date": "2023-01-25",
      "Mail For Mac": "",
      "Outlook For Mac": "",
      "Outlook For Windows": "ProPlus",
      "Outlook For Mobile": "",
      "Other For Mobile": "",
      "Outlook For Web": "",
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
  Report Refresh Date,User Principal Name,Display Name,Is Deleted,Deleted Date,Last Activity Date,Mail For Mac,Outlook For Mac,Outlook For Windows,Outlook For Mobile,Other For Mobile,Outlook For Web,POP3 App,IMAP4 App,SMTP App,Report Period
  2023-01-25,john.doe@contoso.com,John Doe,False,,2023-01-25,,,ProPlus,,,,,,,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,User Principal Name,Display Name,Is Deleted,Deleted Date,Last Activity Date,Mail For Mac,Outlook For Mac,Outlook For Windows,Outlook For Mobile,Other For Mobile,Outlook For Web,POP3 App,IMAP4 App,SMTP App,Report Period
  2023-01-25,john.doe@contoso.com,John Doe,False,,2023-01-25,,,ProPlus,,,,,,,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,User Principal Name,Display Name,Is Deleted,Deleted Date,Last Activity Date,Mail For Mac,Outlook For Mac,Outlook For Windows,Outlook For Mobile,Other For Mobile,Outlook For Web,POP3 App,IMAP4 App,SMTP App,Report Period
  2023-01-25,john.doe@contoso.com,John Doe,False,,2023-01-25,,,ProPlus,,,,,,,7
  ```

  </TabItem>
</Tabs>
