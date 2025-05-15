-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo app add

Adds an app to the specified SharePoint Online app catalog

## Usage

```sh
m365 spo app add [options]
```

## Options

```md definition-list
`-p, --filePath <filePath>`
: Absolute or relative path to the solution package file to add to the app catalog.

`--overwrite`
: Set to overwrite the existing package file.

`-s, --appCatalogScope [appCatalogScope]`
: Scope of the app catalog. Allowed values: `tenant`, `sitecollection`. Defaults to `tenant`.

`-u, --appCatalogUrl [appCatalogUrl]`
: The URL of the app catalog where the solution package will be added. It must be specified when the scope is `sitecollection`.
```

<Global />

## Remarks

When specifying the path to the app package file you can use both relative and absolute paths. Note, that `~` in the path, will not be resolved and will most likely result in an error.

When adding an app to the tenant app catalog, it's not necessary to specify the tenant app catalog URL. When the URL is not specified, the CLI will try to resolve the URL itself. Specifying the app catalog URL is required when you want to add the app to a site collection app catalog.

When specifying site collection app catalog, you can specify the URL either with our without the _AppCatalog_ part, for example `https://contoso.sharepoint.com/sites/team-a/AppCatalog` or `https://contoso.sharepoint.com/sites/team-a`. CLI will accept both formats.

If you try to upload a package that already exists in the app catalog without specifying the `--overwrite` option, the command will fail with an error stating that the specified package already exists.

## Examples

Add the package to the tenant app catalog.

```sh
m365 spo app add --filePath /Users/pnp/spfx/sharepoint/solution/spfx.sppkg
```

Overwrite the package in the tenant app catalog with the newer version.

```sh
m365 spo app add --filePath sharepoint/solution/spfx.sppkg --overwrite
```

Add the package to the site collection app catalog of the specified site.

```sh
m365 spo app add --filePath c:\spfx.sppkg --appCatalogScope sitecollection --appCatalogUrl https://contoso.sharepoint.com/sites/site1
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "CheckInComment": "",
    "CheckOutType": 2,
    "ContentTag": "{EXAMPLE-GUID-PLACEHOLDER},2,1",
    "CustomizedPageStatus": 0,
    "ETag": "\"{EXAMPLE-GUID-PLACEHOLDER},2\"",
    "Exists": true,
    "ExistsAllowThrowForPolicyFailures": true,
    "IrmEnabled": false,
    "Length": "757211",
    "Level": 1,
    "LinkingUri": null,
    "LinkingUrl": "",
    "MajorVersion": 1,
    "MinorVersion": 0,
    "Name": "spfx.sppkg",
    "ServerRelativeUrl": "/sites/apps/AppCatalog/spfx.sppkg",
    "TimeCreated": "2023-10-02T06:53:30Z",
    "TimeLastModified": "2023-10-02T06:53:30Z",
    "Title": "spfx-client-side-solution",
    "UIVersion": 512,
    "UIVersionLabel": "1.0",
    "UniqueId": "EXAMPLE-GUID-PLACEHOLDER"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  EXAMPLE-GUID-PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  CheckInComment,CheckOutType,ContentTag,CustomizedPageStatus,ETag,Exists,ExistsAllowThrowForPolicyFailures,IrmEnabled,Length,Level,LinkingUrl,MajorVersion,MinorVersion,Name,ServerRelativeUrl,TimeCreated,TimeLastModified,Title,UIVersion,UIVersionLabel,UniqueId
  ,2,"{EXAMPLE-GUID-PLACEHOLDER},2,1",0,"""{EXAMPLE-GUID-PLACEHOLDER},2""",1,1,,757211,1,,1,0,spfx.sppkg,/sites/apps/AppCatalog/spfx.sppkg,2023-10-02T06:55:12Z,2023-10-02T06:55:12Z,spfx-client-side-solution,512,1.0,EXAMPLE-GUID-PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo app add --filePath "C:\SPFx\sharepoint\solution\spfx.sppkg"

  Date: 10/2/2023

  ## spfx-client-side-solution (EXAMPLE-GUID-PLACEHOLDER)

  Property | Value
  ---------|-------
  CheckInComment |
  CheckOutType | 2
  ContentTag | {EXAMPLE-GUID-PLACEHOLDER},2,1
  CustomizedPageStatus | 0
  ETag | "{EXAMPLE-GUID-PLACEHOLDER},2"
  Exists | true
  ExistsAllowThrowForPolicyFailures | true
  IrmEnabled | false
  Length | 757211
  Level | 1
  LinkingUrl |
  MajorVersion | 1
  MinorVersion | 0
  Name | spfx.sppkg
  ServerRelativeUrl | /sites/apps/AppCatalog/spfx.sppkg
  TimeCreated | 2023-10-02T06:56:02Z
  TimeLastModified | 2023-10-02T06:56:02Z
  Title | spfx-client-side-solution
  UIVersion | 512
  UIVersionLabel | 1.0
  UniqueId | EXAMPLE-GUID-PLACEHOLDER
  ```

  </TabItem>
</Tabs>

## More information

- Application Lifecycle Management (ALM) APIs: [https://learn.microsoft.com/sharepoint/dev/apis/alm-api-for-spfx-add-ins](https://learn.microsoft.com/sharepoint/dev/apis/alm-api-for-spfx-add-ins)
