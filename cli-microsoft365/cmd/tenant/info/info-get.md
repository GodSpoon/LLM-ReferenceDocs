-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# tenant info get

Gets information about any tenant

## Usage

```sh
m365 tenant info get [options]
```

## Options

```md definition-list
`-d, --domainName [domainName]`
: The primary domain name of a tenant. Optionally specify either `domainName` or `tenantId` but not both. If none are specified, the tenantId of the currently signed-in user is used.

`-i, --tenantId [tenantId]`
: The unique tenant identifier of a tenant. Optionally specify either `domainName` or `tenantId` but not both. If none are specified, the tenantId of the currently signed-in user is used.
```

<Global />

## Remarks

If no domain name or tenantId is specified, the command will return the tenant information of the currently signed in user.

## Examples

Get tenant information for the currently signed in user.

```sh
m365 tenant info get
```

Get tenant information for the Contoso tenant.

```sh
m365 tenant info get --domainName contoso.com
```

Get tenant information by id.

```sh
m365 tenant info get --tenantId e65b162c-6f87-4eb1-a24e-1b37d3504663
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "tenantId": "e65b162c-6f87-4eb1-a24e-1b37d3504663",
    "federationBrandName": null,
    "displayName": "Contoso",
    "defaultDomainName": "contoso.com"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  defaultDomainName   : contoso.com
  displayName         : Contoso
  federationBrandName : null
  tenantId            : e65b162c-6f87-4eb1-a24e-1b37d3504663
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  tenantId,displayName,defaultDomainName
  e65b162c-6f87-4eb1-a24e-1b37d3504663,Contoso,contoso.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # tenant info get

  Date: 9/14/2023

  ## Contoso

  Property | Value
  ---------|-------
  tenantId | e65b162c-6f87-4eb1-a24e-1b37d3504663
  displayName | Contoso
  defaultDomainName | contoso.com
  ```

  </TabItem>
</Tabs>
