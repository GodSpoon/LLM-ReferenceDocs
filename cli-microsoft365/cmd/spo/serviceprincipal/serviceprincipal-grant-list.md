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
      "IsDomainIsolated": false,
      "ObjectId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "PackageName": null,
      "Resource": "Windows Azure Active Directory",
      "ResourceId": "b0c1505e-d1fa-4215-a3ac-5e3141b8d3b1",
      "Scope": "User.Read"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  IsDomainIsolated  ObjectId                                     PackageName  Resource                        ResourceId                            Scope
  ----------------  -------------------------------------------  -----------  ------------------------------  ------------------------------------  --------------------------
  false             EXAMPLE_SECRET_VALUE_PLACEHOLDER  null         Windows Azure Active Directory  b0c1505e-d1fa-4215-a3ac-5e3141b8d3b1  User.Read
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  IsDomainIsolated,ObjectId,PackageName,Resource,ResourceId,Scope
  ,EXAMPLE_SECRET_VALUE_PLACEHOLDER,,Windows Azure Active Directory,b0c1505e-d1fa-4215-a3ac-5e3141b8d3b1,User.Read
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo serviceprincipal grant list 

  Date: 5/7/2023

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  IsDomainIsolated | false
  ObjectId | 4WtBzD8u5kW-sYuikIWL\_8ZYTP5mJB1LnC6OT4Ibr94
  Resource | Microsoft Graph
  ResourceId | fe4c58c6-2466-4b1d-9c2e-8e4f821bafde
  Scope | Mail.Read
  ```

  </TabItem>
</Tabs>
