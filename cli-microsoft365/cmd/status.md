-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# status

Shows Microsoft 365 login status

## Usage

```sh
m365 status [options]
```

## Options

<Global />

## Remarks

If you are logged in to Microsoft 365, the `status` command will show you information about the user or application name used to sign in and the details about the stored refresh and access tokens and their expiration date and time when run in debug mode.

## Examples

Show the information about the current login to the Microsoft 365

```sh
m365 status
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "connectionName": "dd8b99a7-77c6-4238-a609-396d27844921",
    "connectedAs": "john.doe@contoso.onmicrosoft.com",
    "authType": "DeviceCode",
    "appId": "31359c7f-bd7e-475c-86db-fdb8c937548e",
    "appTenant": "common",
    "cloudType": "Public"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  appId         : 31359c7f-bd7e-475c-86db-fdb8c937548e
  appTenant     : common
  authType      : DeviceCode
  cloudType     : Public
  connectedAs   : john.doe@contoso.onmicrosoft.com
  connectionName: dd8b99a7-77c6-4238-a609-396d27844921
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  connectionName,connectedAs,authType,appId,appTenant,cloudType
  dd8b99a7-77c6-4238-a609-396d27844921,john.doe@contoso.onmicrosoft.com,DeviceCode,31359c7f-bd7e-475c-86db-fdb8c937548e,common,Public
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # status

  Date: 7/2/2023

  Property | Value
  ---------|-------
  connectionName | dd8b99a7-77c6-4238-a609-396d27844921
  connectedAs | john.doe@contoso.onmicrosoft.com
  authType | DeviceCode
  appId | 31359c7f-bd7e-475c-86db-fdb8c937548e
  appTenant | common
  cloudType | Public
  ```

  </TabItem>
</Tabs>
