-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo app get

Gets information about the specific app from the specified app catalog

## Usage

```sh
m365 spo app get [options]
```

## Options

```md definition-list
`-i, --id [id]`
: ID of the app to retrieve information for. Specify the `id` or the `name` but not both.

`-n, --name [name]`
: Name of the app to retrieve information for. Specify the `id` or the `name` but not both.

`-u, --appCatalogUrl [appCatalogUrl]`
: URL of the tenant or site collection app catalog. It must be specified when the scope is `sitecollection`.

`-s, --appCatalogScope [appCatalogScope]`
: Scope of the app catalog. Allowed values: `tenant`, `sitecollection`. Defaults to `tenant`.
```

<Global />

## Remarks

When getting information about an app from the tenant app catalog, it's not necessary to specify the tenant app catalog URL. When the URL is not specified, the CLI will try to resolve the URL itself. Specifying the app catalog URL is required when you want to get information about an app from a site collection app catalog.

When specifying site collection app catalog, you can specify the URL either with our without the _AppCatalog_ part, for example `https://contoso.sharepoint.com/sites/team-a/AppCatalog` or `https://contoso.sharepoint.com/sites/team-a`. CLI will accept both formats.

## Examples

Return details about the app with the specified ID available in the tenant app catalog.

```sh
m365 spo app get --id b2307a39-e878-458b-bc90-03bc578531d6
```

Return details about the app with the specified name available in the tenant app catalog. Will try to detect the app catalog URL.

```sh
m365 spo app get --name solution.sppkg
```

Return details about the app with the specified name available in the tenant app catalog using the specified app catalog URL.

```sh
m365 spo app get --name solution.sppkg --appCatalogUrl https://contoso.sharepoint.com/sites/apps
```

Return details about the app with the specified ID available in the site collection app catalog of the specified site.

```sh
m365 spo app get --id b2307a39-e878-458b-bc90-03bc578531d6 --appCatalogScope sitecollection --appCatalogUrl https://contoso.sharepoint.com/sites/site1
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "AadAppId": "48535560-3cc0-442e-a1b4-94c084b3ff59",
    "AadPermissions": "Microsoft Graph, Directory.ReadWrite.All",
    "AppCatalogVersion": "1.6.0.0",
    "CanUpgrade": false,
    "CDNLocation": "SharePoint Online",
    "ContainsTenantWideExtension": false,
    "CurrentVersionDeployed": true,
    "Deployed": true,
    "ErrorMessage": "No errors.",
    "ID": "b05196d4-65a3-4ee3-bf92-4acfb7a05cd7",
    "InstalledVersion": "",
    "IsClientSideSolution": true,
    "IsEnabled": true,
    "IsPackageDefaultSkipFeatureDeployment": true,
    "IsValidAppPackage": true,
    "ProductId": "1e5954e2-fc1c-4501-8678-27a6bd013422",
    "ShortDescription": "spfx description",
    "SkipDeploymentFeature": false,
    "StoreAssetId": "",
    "SupportsTeamsTabs": true,
    "ThumbnailUrl": "",
    "Title": "spfx-client-side-solution"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  AadAppId                             : 48535560-3cc0-442e-a1b4-94c084b3ff59
  AadPermissions                       : Microsoft Graph, Directory.ReadWrite.All
  AppCatalogVersion                    : 1.6.0.0
  CDNLocation                          : SharePoint Online
  CanUpgrade                           : false
  ContainsTenantWideExtension          : false
  CurrentVersionDeployed               : true
  Deployed                             : true
  ErrorMessage                         : No errors.
  ID                                   : b05196d4-65a3-4ee3-bf92-4acfb7a05cd7
  InstalledVersion                     :
  IsClientSideSolution                 : true
  IsEnabled                            : true
  IsPackageDefaultSkipFeatureDeployment: true
  IsValidAppPackage                    : true
  ProductId                            : 1e5954e2-fc1c-4501-8678-27a6bd013422
  ShortDescription                     : spfx description
  SkipDeploymentFeature                : false
  StoreAssetId                         :
  SupportsTeamsTabs                    : true
  ThumbnailUrl                         :
  Title                                : spfx-client-side-solution
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  AadAppId,AadPermissions,AppCatalogVersion,CanUpgrade,CDNLocation,ContainsTenantWideExtension,CurrentVersionDeployed,Deployed,ErrorMessage,ID,InstalledVersion,IsClientSideSolution,IsEnabled,IsPackageDefaultSkipFeatureDeployment,IsValidAppPackage,ProductId,ShortDescription,SkipDeploymentFeature,StoreAssetId,SupportsTeamsTabs,ThumbnailUrl,Title
  48535560-3cc0-442e-a1b4-94c084b3ff59,"Microsoft Graph, Directory.ReadWrite.All",1.6.0.0,,SharePoint Online,,1,1,No errors.,b05196d4-65a3-4ee3-bf92-4acfb7a05cd7,,1,1,1,1,1e5954e2-fc1c-4501-8678-27a6bd013422,spfx description,,,1,,spfx-client-side-solution
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo app get --id "b05196d4-65a3-4ee3-bf92-4acfb7a05cd7"

  Date: 10/2/2023

  ## spfx-client-side-solution (b05196d4-65a3-4ee3-bf92-4acfb7a05cd7)

  Property | Value
  ---------|-------
  AadAppId | 48535560-3cc0-442e-a1b4-94c084b3ff59
  AadPermissions | Microsoft Graph, Directory.ReadWrite.All
  AppCatalogVersion | 1.6.0.0
  CanUpgrade | false
  CDNLocation | SharePoint Online
  ContainsTenantWideExtension | false
  CurrentVersionDeployed | true
  Deployed | true
  ErrorMessage | No errors.
  ID | b05196d4-65a3-4ee3-bf92-4acfb7a05cd7
  InstalledVersion |
  IsClientSideSolution | true
  IsEnabled | true
  IsPackageDefaultSkipFeatureDeployment | true
  IsValidAppPackage | true
  ProductId | 1e5954e2-fc1c-4501-8678-27a6bd013422
  ShortDescription | spfx description
  SkipDeploymentFeature | false
  StoreAssetId |
  SupportsTeamsTabs | true
  ThumbnailUrl |
  Title | spfx-client-side-solution
  ```

  </TabItem>
</Tabs>

## More information

- Application Lifecycle Management (ALM) APIs: [https://learn.microsoft.com/sharepoint/dev/apis/alm-api-for-spfx-add-ins](https://learn.microsoft.com/sharepoint/dev/apis/alm-api-for-spfx-add-ins)
