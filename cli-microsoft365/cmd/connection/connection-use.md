-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# connection use

Activate the specified Microsoft 365 tenant connection

## Usage

```sh
m365 connection use [options]
```

## Options

```md definition-list
`-n, --name [name]`
: The name of the connection to switch to.
```

<Global />

## Remarks

:::tip

If you haven't disabled the "prompt" setting, running this command without options will show a list of available connections. You can then select the connection to activate it.

:::

You can update the name of a connection by running [m365 connection set](connection-set.mdx).

## Examples

Switch to a different connection

```sh
m365 connection use --name '6e70c8ea-571d-4daf-bc48-9e1b49ac3390'
```

Switch to another connection by a custom connection name

```sh
m365 connection use --name 'myworkaccount'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "connectedAs": "alexw@contoso.com",
    "connectedName": "028de82d-7fd9-476e-a9fd-be9714280ff3",
    "authType": "DeviceCode",
    "appId": "31359c7f-bd7e-475c-86db-fdb8c937548e",
    "appTenant": "common",
    "cloudType": "Public"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  appId      : 31359c7f-bd7e-475c-86db-fdb8c937548e
  appTenant  : common
  authType   : DeviceCode
  cloudType  : Public
  connectionName : 028de82d-7fd9-476e-a9fd-be9714280ff3
  connectedAs: alexw@contoso.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  connectionName,connectedAs,authType,appId,appTenant,cloudType
  alexw@contoso.com,028de82d-7fd9-476e-a9fd-be9714280ff3,DeviceCode,31359c7f-bd7e-475c-86db-fdb8c937548e,common,Public
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # connection use

  Date: 7/2/2023

  Property | Value
  ---------|-------
  connectedAs | alexw@contoso.com
  connectionName | 028de82d-7fd9-476e-a9fd-be9714280ff3
  authType | DeviceCode
  appId | 31359c7f-bd7e-475c-86db-fdb8c937548e
  appTenant | common
  cloudType | Public
  ```

  </TabItem>
</Tabs>
