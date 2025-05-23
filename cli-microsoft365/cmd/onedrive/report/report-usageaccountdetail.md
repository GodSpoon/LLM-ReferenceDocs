-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# onedrive report usageaccountdetail

Gets details about OneDrive usage by account

## Usage

```sh
m365 onedrive report usageaccountdetail [options]
```

## Options

```md definition-list
`-p, --period [period]`
: The length of time over which the report is aggregated. Supported values `D7`, `D30`, `D90`, `D180`.

`-d, --date [date]`
: The date for which you would like to view the users who performed any activity. Supported date format is YYYY-MM-DD. Specify the date or period, but not both`
```

<Global />

## Remarks

:::info

This command supports only csv and json output.

:::

## Examples

Gets details about OneDrive usage by account for the last week

```sh
m365 onedrive report usageaccountdetail --period D7
```

Gets details about OneDrive usage by account for May 1, 2019

```sh
m365 onedrive report usageaccountdetail --date 2019-05-01
```

Gets details about OneDrive usage by account for the last week and exports the report data in the specified path in text format

```sh
m365 onedrive report usageaccountdetail --period D7 --output text > "onedriveusageaccountdetail.txt"
```

Gets details about OneDrive usage by account for the last week and exports the report data in the specified path in json format

```sh
m365 onedrive report usageaccountdetail --period D7 --output json > "onedriveusageaccountdetail.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-05-20",
      "Site URL": "93212C12CBFBD450189A52F29CF6397F",
      "Owner Display Name": "24C1B29099C8749194796DFEF8B50A40",
      "Is Deleted": "False",
      "Last Activity Date": "2022-12-27",
      "File Count": "128",
      "Active File Count": "0",
      "Storage Used (Byte)": "104122210",
      "Storage Allocated (Byte)": "1099511627776",
      "Owner Principal Name": "30B283368E548933B1D03A64A6B14A89",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Site URL,Owner Display Name,Is Deleted,Last Activity Date,File Count,Active File Count,Storage Used (Byte),Storage Allocated (Byte),Owner Principal Name,Report Period
  2023-05-20,93212C12CBFBD450189A52F29CF6397F,24C1B29099C8749194796DFEF8B50A40,False,2022-12-27,128,0,104122210,1099511627776,30B283368E548933B1D03A64A6B14A89,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Site URL,Owner Display Name,Is Deleted,Last Activity Date,File Count,Active File Count,Storage Used (Byte),Storage Allocated (Byte),Owner Principal Name,Report Period
  2023-05-20,93212C12CBFBD450189A52F29CF6397F,24C1B29099C8749194796DFEF8B50A40,False,2022-12-27,128,0,104122210,1099511627776,30B283368E548933B1D03A64A6B14A89,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Site URL,Owner Display Name,Is Deleted,Last Activity Date,File Count,Active File Count,Storage Used (Byte),Storage Allocated (Byte),Owner Principal Name,Report Period
  2023-05-20,93212C12CBFBD450189A52F29CF6397F,24C1B29099C8749194796DFEF8B50A40,False,2022-12-27,128,0,104122210,1099511627776,30B283368E548933B1D03A64A6B14A89,7
  ```

  </TabItem>
</Tabs>
