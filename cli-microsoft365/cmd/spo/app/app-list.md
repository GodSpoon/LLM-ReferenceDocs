-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo app list

Lists apps from the specified app catalog

## Usage

```sh
m365 spo app list [options]
```

## Options

```md definition-list
`-s, --appCatalogScope [appCatalogScope]`
: Target app catalog. Allowed values: `tenant`, `sitecollection`. Defaults to `tenant`.

`-u, --appCatalogUrl [appCatalogUrl]`
: URL of the tenant or site collection app catalog. It must be specified when the scope is `sitecollection`.
```

<Global />

## Remarks

When listing information about apps available in the tenant app catalog, it's not necessary to specify the tenant app catalog URL. When the URL is not specified, the CLI will try to resolve the URL itself. Specifying the app catalog URL is required when you want to list information about apps in a site collection app catalog.

When specifying site collection app catalog, you can specify the URL either with our without the _AppCatalog_ part, for example `https://contoso.sharepoint.com/sites/team-a/AppCatalog` or `https://contoso.sharepoint.com/sites/team-a`. CLI will accept both formats.

When using the text output type (default), the command lists only the values of the `Title`, `ID`, `Deployed` and `AppCatalogVersion` properties of the app. When setting the output type to JSON, all available properties are included in the command output.

## Examples

Return the list of available apps from the tenant app catalog. Show the installed version in the site if applicable.

```sh
m365 spo app list
```

Return the list of available apps from a site collection app catalog of the specified site.

```sh
m365 spo app list --appCatalogScope sitecollection --appCatalogUrl https://contoso.sharepoint.com/sites/site1
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
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
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Title                                                         ID                                    Deployed  AppCatalogVersion
  ------------------------------------------------------------  ------------------------------------  --------  -----------------
  spfx-client-side-solution                    b05196d4-65a3-4ee3-bf92-4acfb7a05cd7  true      1.6.0.0
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  AadAppId,AppCatalogVersion,CanUpgrade,CDNLocation,ContainsTenantWideExtension,CurrentVersionDeployed,Deployed,ErrorMessage,ID,InstalledVersion,IsClientSideSolution,IsEnabled,IsPackageDefaultSkipFeatureDeployment,IsValidAppPackage,ProductId,ShortDescription,SkipDeploymentFeature,StoreAssetId,SupportsTeamsTabs,ThumbnailUrl,Title
  48535560-3cc0-442e-a1b4-94c084b3ff59,1.6.0.0,,SharePoint Online,,1,1,No errors.,b05196d4-65a3-4ee3-bf92-4acfb7a05cd7,,1,1,1,1,1e5954e2-fc1c-4501-8678-27a6bd013422,spfx description,,,1,,spfx-client-side-solution
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo app list

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
