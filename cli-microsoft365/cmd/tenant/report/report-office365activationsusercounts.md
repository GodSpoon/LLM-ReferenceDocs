-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# tenant report office365activationsusercounts

Get the count of users that are enabled and those that have activated the Office subscription on desktop or devices or shared computers

## Usage

```sh
m365 tenant report office365activationsusercounts [options]
```

## Options

<Global />

## Remarks

:::info

This command supports only csv and json output.

:::

## Examples

Get the count of users that are enabled and those that have activated the Office subscription on desktop or devices or shared computers

```sh
m365 tenant report office365activationsusercounts
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2022-10-25",
      "Product Type": "MICROSOFT 365 APPS FOR ENTERPRISE",
      "Assigned": 24,
      "Activated": 5,
      "Shared Computer Activation": 0
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Product Type,Assigned,Activated,Shared Computer Activation
  2022-10-25,MICROSOFT 365 APPS FOR ENTERPRISE,24,5,0
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Product Type,Assigned,Activated,Shared Computer Activation
  2022-10-25,MICROSOFT 365 APPS FOR ENTERPRISE,24,5,0
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Product Type,Assigned,Activated,Shared Computer Activation
  2022-10-25,MICROSOFT 365 APPS FOR ENTERPRISE,24,5,0
  ```

  </TabItem>
</Tabs>
