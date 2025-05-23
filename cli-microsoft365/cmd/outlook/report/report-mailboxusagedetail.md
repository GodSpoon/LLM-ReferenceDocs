-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# outlook report mailboxusagedetail

Gets details about mailbox usage

## Usage

```sh
m365 outlook report mailboxusagedetail [options]
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

Gets details about mailbox usage for the last week

```sh
m365 outlook report mailboxusagedetail --period D7
```

Gets details about mailbox usage for the last week and exports the report data in the specified path in text format

```sh
m365 outlook report mailboxusagedetail --period D7 --output text > "mailboxusagedetail.txt"
```

Gets details about mailbox usage for the last week and exports the report data in the specified path in json format

```sh
m365 outlook report mailboxusagedetail --period D7 --output json > "mailboxusagedetail.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-01-24",
      "User Principal Name": "john.doe@contoso.com",
      "Display Name": "John Doe",
      "Is Deleted": "False",
      "Deleted Date": "",
      "Created Date": "2023-01-18",
      "Last Activity Date": "2023-01-24",
      "Item Count": "191",
      "Storage Used (Byte)": "5719031",
      "Issue Warning Quota (Byte)": "105226698752",
      "Prohibit Send Quota (Byte)": "106300440576",
      "Prohibit Send/Receive Quota (Byte)": "107374182400",
      "Deleted Item Count": "25",
      "Deleted Item Size (Byte)": "582157",
      "Deleted Item Quota (Byte)": "32212254720",
      "Has Archive": "False",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  Report Refresh Date,User Principal Name,Display Name,Is Deleted,Deleted Date,Created Date,Last Activity Date,Item Count,Storage Used (Byte),Issue Warning Quota (Byte),Prohibit Send Quota (Byte),Prohibit Send/Receive Quota (Byte),Deleted Item Count,Deleted Item Size (Byte),Deleted Item Quota (Byte),Has Archive,Report Period
  2023-01-24,john.doe@contoso.com,John Doe,False,,2023-01-18,2023-01-24,191,5719031,105226698752,106300440576,107374182400,25,582157,32212254720,False,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,User Principal Name,Display Name,Is Deleted,Deleted Date,Created Date,Last Activity Date,Item Count,Storage Used (Byte),Issue Warning Quota (Byte),Prohibit Send Quota (Byte),Prohibit Send/Receive Quota (Byte),Deleted Item Count,Deleted Item Size (Byte),Deleted Item Quota (Byte),Has Archive,Report Period
  2023-01-24,john.doe@contoso.com,John Doe,False,,2023-01-18,2023-01-24,191,5719031,105226698752,106300440576,107374182400,25,582157,32212254720,False,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,User Principal Name,Display Name,Is Deleted,Deleted Date,Created Date,Last Activity Date,Item Count,Storage Used (Byte),Issue Warning Quota (Byte),Prohibit Send Quota (Byte),Prohibit Send/Receive Quota (Byte),Deleted Item Count,Deleted Item Size (Byte),Deleted Item Quota (Byte),Has Archive,Report Period
  2023-01-24,john.doe@contoso.com,John Doe,False,,2023-01-18,2023-01-24,191,5719031,105226698752,106300440576,107374182400,25,582157,32212254720,False,7
  ```

  </TabItem>
</Tabs>
