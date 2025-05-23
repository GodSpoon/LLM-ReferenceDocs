-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo serviceprincipal grant add

Grants the service principal permission to the specified API

## Usage

```sh
m365 spo serviceprincipal grant add [options]
```

## Alias

```sh
m365 spo sp grant add
```

## Options

```md definition-list
`-r, --resource <resource>`
: The name of the resource for which permissions should be granted.

`-s, --scope <scope>`
: The name of the permission that should be granted.
```

<Global />

## Remarks

:::info

To use this command you must be a Global administrator.

:::

## Examples

Grant the service principal permission to read email using the Microsoft Graph

```sh
m365 spo serviceprincipal grant add --resource 'Microsoft Graph' --scope 'Mail.Read'
```

Grant the service principal permission to a custom API

```sh
m365 spo serviceprincipal grant add --resource 'contoso-api' --scope 'user_impersonation'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "ClientId": "6004a642-185c-479a-992a-15d1c23e2229",
    "ConsentType": "AllPrincipals",
    "IsDomainIsolated": false,
    "ObjectId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "PackageName": null,
    "Resource": "Microsoft Graph",
    "ResourceId": "a46b0017-21e2-4db1-bc69-ca63576a38d6",
    "Scope": "Mail.Read"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  ClientId        : 6004a642-185c-479a-992a-15d1c23e2229
  ConsentType     : AllPrincipals
  IsDomainIsolated: false
  ObjectId        : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  PackageName     : null
  Resource        : Microsoft Graph
  ResourceId      : a46b0017-21e2-4db1-bc69-ca63576a38d6
  Scope           : Mail.Read
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ClientId,ConsentType,IsDomainIsolated,ObjectId,PackageName,Resource,ResourceId,Scope
  6004a642-185c-479a-992a-15d1c23e2229,AllPrincipals,,EXAMPLE_SECRET_VALUE_PLACEHOLDER,,Microsoft Graph,a46b0017-21e2-4db1-bc69-ca63576a38d6,Mail.Read
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo serviceprincipal grant add --resource "Microsoft Graph" --scope "Mail.Read"

  Date: 5/7/2023

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  ClientId | cc416be1-2e3f-45e6-beb1-8ba290858bff
  ConsentType | AllPrincipals
  IsDomainIsolated | false
  ObjectId | 4WtBzD8u5kW-sYuikIWL\_8ZYTP5mJB1LnC6OT4Ibr94
  Resource | Microsoft Graph
  ResourceId | fe4c58c6-2466-4b1d-9c2e-8e4f821bafde
  Scope | Mail.Read
  ```

  </TabItem>
</Tabs>
