-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spe containertype add

Creates a new Container Type for your app

## Usage

```sh
m365 spe containertype add [options]
```

## Options

```md definition-list
`-n, --name <name>`
: Container type name.

`--applicationId <applicationId>`
: Application ID of the Microsoft Entra ID app that will be the owner of the Container Type.

`--trial`
: Specify if the Container Type should be a trial.

`--azureSubscriptionId [azureSubscriptionId]`
: Azure Subscription Id. Required unless the `trial` option was specified.

`--resourceGroup [resourceGroup]`
: Azure Resource group for billing. Required unless the `trial` option was specified.

`--region [region]`
: Region. Required unless the `trial` option was specified.
```

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

:::note

You can only create one Trial container type per tenant, a single application registration can only contain one container type and a tenant can contain a maximum of five containers types in total.

:::

## Examples

Adds a new trial Container Type

```sh
m365 spe containertype add --name 'trial container' --applicationId '1b3b8660-9a44-4a7c-9c02-657f3ff5d5ac' --trial
```

Adds a new Container Type using a standard Container Type.

```sh
m365 spe containertype add --name 'standard container' --applicationId '1b3b8660-9a44-4a7c-9c02-657f3ff5d5ac' --azureSubscriptionId 'f08575e2-36c4-407f-a891-eabae23f66bc' --region 'West Europe' --resourceGroup 'Standard group'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "AzureSubscriptionId": "f08575e2-36c4-407f-a891-eabae23f66bc",
    "ContainerTypeId": "c33cfee5-c9b6-0a2a-02ee-060693a57f37",
    "CreationDate": "3/11/2024 2:38:56 PM",
    "DisplayName": "standard container",
    "ExpiryDate": null,
    "IsBillingProfileRequired": true,
    "OwningAppId": "1b3b8660-9a44-4a7c-9c02-657f3ff5d5ac",
    "OwningTenantId": "e1dd4023-a656-480a-8a0e-c1b1eec51e1d",
    "Region": "West Europe",
    "ResourceGroup": "Standard group",
    "SPContainerTypeBillingClassification": "Standard"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  AzureSubscriptionId                 : f08575e2-36c4-407f-a891-eabae23f66bc
  ContainerTypeId                     : 331f3b15-b4f6-05e0-05de-2d8c370462b3
  CreationDate                        : 3/11/2024 2:47:16 PM
  DisplayName                         : Standard container
  ExpiryDate                          : null
  IsBillingProfileRequired            : false
  OwningAppId                         : 1b3b8660-9a44-4a7c-9c02-657f3ff5d5ac
  OwningTenantId                      : e1dd4023-a656-480a-8a0e-c1b1eec51e1d
  Region                              : West Europe
  ResourceGroup                       : Standard group
  SPContainerTypeBillingClassification: Standard
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  AzureSubscriptionId,ContainerTypeId,CreationDate,DisplayName,ExpiryDate,IsBillingProfileRequired,OwningAppId,OwningTenantId,Region,ResourceGroup,SPContainerTypeBillingClassification
  f08575e2-36c4-407f-a891-eabae23f66bc,331f3b15-b4f6-05e0-05de-2d8c370462b3,3/11/2024 2:48:13 PM,Standard container,,,1b3b8660-9a44-4a7c-9c02-657f3ff5d5ac,e1dd4023-a656-480a-8a0e-c1b1eec51e1d,West Europe,Standard group,Standard
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spe containertype add --name 'Standard container' --applicationId '1b3b8660-9a44-4a7c-9c02-657f3ff5d5ac' --azureSubscriptionId 'f08575e2-36c4-407f-a891-eabae23f66bc' --region 'West Europe' --resourceGroup 'Standard group'

  Date: 11/03/2024

  ## Standard container

  Property | Value
  ---------|-------
  AzureSubscriptionId | f08575e2-36c4-407f-a891-eabae23f66bc
  ContainerTypeId | 331f3b15-b4f6-05e0-05de-2d8c370462b3
  CreationDate | 3/11/2024 2:49:16 PM
  DisplayName | Standard Container
  IsBillingProfileRequired | false
  OwningAppId | 1b3b8660-9a44-4a7c-9c02-657f3ff5d5ac
  OwningTenantId | e1dd4023-a656-480a-8a0e-c1b1eec51e1d
  Region | West Europe
  ResourceGroup | Standard group
  SPContainerTypeBillingClassification | Standard
  ```

  </TabItem>
</Tabs>

## More information

In SharePoint Embedded, all files and documents are stored in Containers, and each Container is identified by a Container Type.

Container Type is a property stamped on every Container instance. Each Container Type is owned by one Application, and each Application can own only one Container Type.

The primary function of a Container Type is to manage the application workload that can access the Containers. Container Type defines the access permissions an Application has towards all Containers of that type, including create, read, write, delete containers; manage container permissions, etc.

More information about SharePoint Embedded and the limits can be found at the following location: [SharePoint Embedded](https://learn.microsoft.com/en-us/sharepoint/dev/embedded/concepts/app-concepts/containertypes#EXAMPLE_SECRET_VALUE_PLACEHOLDER)
