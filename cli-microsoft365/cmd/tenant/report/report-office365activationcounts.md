-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# tenant report office365activationcounts

Get the count of Microsoft 365 activations on desktops and devices

## Usage

```sh
m365 tenant report office365activationcounts [options]
```

## Options

<Global />

## Remarks

:::info

This command supports only csv and json output.

:::

## Examples

Get the count of Microsoft 365 activations on desktops and devices

```sh
m365 tenant report office365activationcounts
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2022-10-25",
      "Product Type": "MICROSOFT 365 APPS FOR ENTERPRISE",
      "Windows": 5,
      "Mac": 0,
      "Android": 0,
      "iOS": 0,
      "Windows 10 Mobile": 0
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Product Type,Windows,Mac,Android,iOS,Windows 10 Mobile
  2022-10-25,MICROSOFT 365 APPS FOR ENTERPRISE,5,0,0,0,0
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Product Type,Windows,Mac,Android,iOS,Windows 10 Mobile
  2022-10-25,MICROSOFT 365 APPS FOR ENTERPRISE,5,0,0,0,0
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Product Type,Windows,Mac,Android,iOS,Windows 10 Mobile
  2022-10-25,MICROSOFT 365 APPS FOR ENTERPRISE,5,0,0,0,0
  ```

  </TabItem>
</Tabs>
