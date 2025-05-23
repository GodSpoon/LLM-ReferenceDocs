-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# onedrive report usagestorage

Gets the trend on the amount of storage you are using in OneDrive for Business

## Usage

```sh
m365 onedrive report usagestorage [options]
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

Gets the trend on the amount of storage you are using in OneDrive for Business for the last week

```sh
m365 onedrive report usagestorage --period D7
```

Gets the trend on the amount of storage you are using in OneDrive for Business for the last week and exports the report data in the specified path in text format

```sh
m365 onedrive report usagestorage --period D7 --output text > "usagestorage.txt"
```

Gets the trend on the amount of storage you are using in OneDrive for Business for the last week and exports the report data in the specified path in json format

```sh
m365 onedrive report usagestorage --period D7 --output json > "usagestorage.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-05-20",
      "Site Type": "OneDrive",
      "Storage Used (Byte)": "104122210",
      "Report Date": "2023-05-20",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Site Type,Storage Used (Byte),Report Date,Report Period
  2023-05-20,OneDrive,104122210,2023-05-20,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Site Type,Storage Used (Byte),Report Date,Report Period
  2023-05-20,OneDrive,104122210,2023-05-20,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Site Type,Storage Used (Byte),Report Date,Report Period
  2023-05-20,OneDrive,104122210,2023-05-20,7
  ```

  </TabItem>
</Tabs>
