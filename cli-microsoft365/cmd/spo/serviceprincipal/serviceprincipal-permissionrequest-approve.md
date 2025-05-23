-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo serviceprincipal permissionrequest approve

Approves the specified permission request

## Usage

```sh
m365 spo serviceprincipal permissionrequest approve [options]
```

## Alias

```sh
m365 spo sp permissionrequest approve
```

## Options

```md definition-list
`-i, --id <id>`
: ID of the permission request to approve.

`--all`
: approve all pending permission requests.

`--resource [resource]`
: The resource of the permissions requests to approve.
```

<Global />

## Remarks

:::info

The admin role that's required to approve permissions depends on the API. To approve permissions to any of the third-party APIs registered in the tenant, the application administrator role is sufficient. To approve permissions for Microsoft Graph or any other Microsoft API, the Global Administrator role is required.

:::

The permission request you want to approve is denoted using its `ID`. You can retrieve it using the [spo serviceprincipal permissionrequest list](./EXAMPLE_SECRET_VALUE_PLACEHOLDER) command.

## Examples

Approve permission request

```sh
m365 spo serviceprincipal permissionrequest approve --id 4dc4c043-25ee-40f2-81d3-b3bf63da7538
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
    "Scope": "Reports.Read.All"
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
  Scope           : Directory.ReadWrite.All
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ClientId,ConsentType,IsDomainIsolated,ObjectId,PackageName,Resource,ResourceId,Scope
  6004a642-185c-479a-992a-15d1c23e2229,AllPrincipals,false,EXAMPLE_SECRET_VALUE_PLACEHOLDER,null,Microsoft Graph,a46b0017-21e2-4db1-bc69-ca63576a38d6,Directory.ReadWrite.All
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo serviceprincipal permissionrequest approve --id "ecc2f667-e219-4c65-908e-957d68244d0c"

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
  Scope | Calendars.Read
  ```

  </TabItem>
</Tabs>
