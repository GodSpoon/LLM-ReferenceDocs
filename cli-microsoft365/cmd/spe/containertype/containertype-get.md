-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spe containertype get

Get a specific Container Type

## Usage

```sh
m365 containertype get [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The Id of the Container Type. Specify either id or name but not both.

`-n, --name [name]`
: The Container Type name. Specify either id or name but not both.
```

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Gets Container Type by id

```sh
m365 spe containertype get --id '4ec4aefd-4fa3-0e4a-20c3-6e68389e7138'
```

Gets Container Type by name

```sh
m365 spe containertype get --name 'test container'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "_ObjectType_": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "ApplicationRedirectUrl": null,
    "AzureSubscriptionId": "/Guid(00000000-0000-0000-0000-000000000000)/",
    "ContainerTypeId": "/Guid(073269af-f1d2-042d-2ef5-5bdd6ac83115)/",
    "CreationDate": null,
    "DisplayName": "test1",
    "ExpiryDate": null,
    "IsBillingProfileRequired": true,
    "OwningAppId": "/Guid(df4085cc-9a38-4255-badc-5c5225610475)/",
    "OwningTenantId": "/Guid(00000000-0000-0000-0000-000000000000)/",
    "Region": null,
    "ResourceGroup": null,
    "SPContainerTypeBillingClassification": 0
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
ContainerTypeId                               DisplayName                                    OwningAppId                                 
--------------------------------------------  ---------------------------------------------  --------------------------------------------
/Guid(073269af-f1d2-042d-2ef5-5bdd6ac83115)/  test1                                          /Guid(df4085cc-9a38-4255-badc-5c5225610475)/
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  _ObjectType_,ApplicationRedirectUrl,AzureSubscriptionId,ContainerTypeId,CreationDate,DisplayName,ExpiryDate,IsBillingProfileRequired,OwningAppId,OwningTenantId,Region,ResourceGroup,SPContainerTypeBillingClassification
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,,/Guid(00000000-0000-0000-0000-000000000000)/,/Guid(073269af-f1d2-042d-2ef5-5bdd6ac83115)/,,test1,,1,/Guid(df4085cc-9a38-4255-badc-5c5225610475)/,/Guid(00000000-0000-0000-0000-000000000000)/,,,0
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spe containertype list 

  Date: 5/11/2024

  ## test1

  Property | Value
  ---------|-------
  \_ObjectType\_ | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  AzureSubscriptionId | /Guid(00000000-0000-0000-0000-000000000000)/
  ContainerTypeId | /Guid(073269af-f1d2-042d-2ef5-5bdd6ac83115)/
  DisplayName | test1
  IsBillingProfileRequired | true
  OwningAppId | /Guid(df4085cc-9a38-4255-badc-5c5225610475)/
  OwningTenantId | /Guid(00000000-0000-0000-0000-000000000000)/
  SPContainerTypeBillingClassification | 0
  ```

  </TabItem>
</Tabs>

## More information

In SharePoint Embedded, all files and documents are stored in Containers, and each Container is identified by a Container Type.

Container Type is a property stamped on every Container instance. Each Container Type is owned by one Application, and each Application can own only one Container Type.

The primary function of a Container Type is to manage the application workload that can access the Containers. Container Type defines the access permissions an Application has towards all Containers of that type, including create, read, write, delete containers; manage container permissions, etc.

More information about SharePoint Embedded and the limits can be found at the following location: [SharePoint Embedded](https://learn.microsoft.com/en-us/sharepoint/dev/embedded/concepts/app-concepts/containertypes#EXAMPLE_SECRET_VALUE_PLACEHOLDER)
