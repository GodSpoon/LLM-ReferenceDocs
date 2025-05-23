-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spfx project permissions grant

Grant API permissions defined in the current SPFx project

## Usage

```sh
m365 spfx project permissions grant [options]
```

## Options

<Global />

## Remarks

:::info

Run this command in the folder where the project is located from where you want to grant the permissions.

:::

This command grant the permissions defined in: _package-solution.json_.

## Examples

Grant API permissions requested in the current SPFx project

```sh
m365 spfx project permissions grant
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
  # spfx project permissions grant

  Date: 2/17/2023

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  ClientId | 6004a642-185c-479a-992a-15d1c23e2229
  ConsentType | AllPrincipals
  IsDomainIsolated | false
  ObjectId | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  PackageName | null
  Resource | Microsoft Graph
  ResourceId | a46b0017-21e2-4db1-bc69-ca63576a38d6
  Scope | Mail.Read
  ```

  </TabItem>
</Tabs>
