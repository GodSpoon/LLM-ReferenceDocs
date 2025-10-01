-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo serviceprincipal grant list

Lists permissions granted to the service principal

## Usage

```sh
m365 spo serviceprincipal grant list [options]
```

## Alias

```sh
m365 spo sp grant list
```

## Options

<Global />

## Remarks

:::info

To use this command you must be a Global administrator.

:::

## Examples

List all permissions granted to the service principal

```sh
m365 spo serviceprincipal grant list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "clientId": "1e551032-3e2d-4d6b-9392-9b25451313a0",
      "consentType": "AllPrincipals",
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "principalId": null,
      "resourceId": "cd143b5c-7693-42ec-89fb-377e8e97a8ff",
      "scope": "User.Read"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  clientId                              consentType    id                                           principalId  resourceId                            scope                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
  ------------------------------------  -------------  -------------------------------------------  -----------  ------------------------------------  ----------
  1e551032-3e2d-4d6b-9392-9b25451313a0  AllPrincipals  EXAMPLE_SECRET_VALUE_PLACEHOLDER  null         cd143b5c-7693-42ec-89fb-377e8e97a8ff  User.Read
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  clientId,consentType,id,principalId,resourceId,scope
  1e551032-3e2d-4d6b-9392-9b25451313a0,AllPrincipals,EXAMPLE_SECRET_VALUE_PLACEHOLDER,,cd143b5c-7693-42ec-89fb-377e8e97a8ff,User.Read
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo serviceprincipal grant list 

  Date: 7/8/2025

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  clientId | 1e551032-3e2d-4d6b-9392-9b25451313a0
  consentType | AllPrincipals
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  resourceId | cd143b5c-7693-42ec-89fb-377e8e97a8ff
  scope | User.Read
  ```

  </TabItem>
</Tabs>
