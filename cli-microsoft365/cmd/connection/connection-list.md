-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# connection list

Show the list of available connections

## Usage

```sh
m365 connection list [options]
```

## Options

<Global />

## Remarks

If you are logged in to Microsoft 365 with multiple identities, this command will show you a list of users and/or applications used to sign in.  

## Examples

Show the list of available identities used to sign in to Microsoft 365

```sh
m365 connection list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "name": "028de82d-7fd9-476e-a9fd-be9714280ff3",
      "connectedAs": "alexw@contoso.com",
      "authType": "DeviceCode",
      "active": true
    },
    {
      "name": "acd6df42-10a9-4315-8928-53334f1c9d01",
      "connectedAs": "Contoso Application",
      "authType": "Secret",
      "active": false
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  name                                  connectedAs          authType    active
  ------------------------------------  -------------------  ----------  ------
  028de82d-7fd9-476e-a9fd-be9714280ff3  alexw@contoso.com    DeviceCode  true
  acd6df42-10a9-4315-8928-53334f1c9d01  Contoso Application  Secret      false
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  name,connectedAs,authType,active
  028de82d-7fd9-476e-a9fd-be9714280ff3,alexw@contoso.com,DeviceCode,true
  acd6df42-10a9-4315-8928-53334f1c9d01,Contoso Application,Secret,false
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # connection list

  Date: 7/2/2023

  ## 028de82d-7fd9-476e-a9fd-be9714280ff3

  Property | Value
  ---------|-------
  name | 028de82d-7fd9-476e-a9fd-be9714280ff3
  connectedAs | alexw@contoso.com
  authType | DeviceCode
  active | true

  ## acd6df42-10a9-4315-8928-53334f1c9d01

  Property | Value
  ---------|-------
  name | acd6df42-10a9-4315-8928-53334f1c9d01
  connectedAs | Contoso Application
  authType | Secret
  active | false
  ```

  </TabItem>
</Tabs>
