-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo app deploy

Deploys the specified app in the specified app catalog

## Usage

```sh
m365 spo app deploy [options]
```

## Options

```md definition-list
`-i, --id [id]`
: ID of the app to deploy. Specify the `id` or the `name` but not both.

`-n, --name [name]`
: Name of the app to deploy. Specify the `id` or the `name` but not both.

`-u, --appCatalogUrl [appCatalogUrl]`
: URL of the tenant or site collection app catalog. It must be specified when the scope is `sitecollection`.

`--skipFeatureDeployment`
: If the app supports tenant-wide deployment, deploy it to the whole tenant.

`-s, --appCatalogScope [appCatalogScope]`
: Scope of the app catalog. Allowed values: `tenant`, `sitecollection`. Defaults to `tenant`.
```

<Global />

## Remarks

When deploying an app in the tenant app catalog, it's not necessary to specify the tenant app catalog URL. When the URL is not specified, the CLI will try to resolve the URL itself. Specifying the app catalog URL is required when you want to deploy the app in a site collection app catalog.

When specifying site collection app catalog, you can specify the URL either with our without the _AppCatalog_ part, for example `https://contoso.sharepoint.com/sites/team-a/AppCatalog` or `https://contoso.sharepoint.com/sites/team-a`. CLI will accept both formats.

If the app with the specified ID doesn't exist in the app catalog, the command will fail with an error. Before you can deploy an app, you have to add it to the app catalog first using the [spo app add](./app-add.mdx) command.

## Examples

Deploy the specified app in the tenant app catalog. Try to resolve the URL of the tenant app catalog automatically.

```sh
m365 spo app deploy --id 058140e3-0e37-44fc-a1d3-79c487d371a3
```

Deploy the specified app in the site collection app catalog of the specified site.

```sh
m365 spo app deploy --id 058140e3-0e37-44fc-a1d3-79c487d371a3 --appCatalogScope sitecollection --appCatalogUrl https://contoso.sharepoint.com/sites/site1
```

Deploy the app with the specified name in the tenant app catalog. Try to resolve the URL of the tenant app catalog automatically.

```sh
m365 spo app deploy --name solution.sppkg
```

Deploy the specified app in the tenant app catalog.

```sh
m365 spo app deploy --id 058140e3-0e37-44fc-a1d3-79c487d371a3 --appCatalogUrl https://contoso.sharepoint.com/sites/apps
```

Deploy the specified app to the whole tenant at once. Features included in the solution will not be activated.

```sh
m365 spo app deploy --id 058140e3-0e37-44fc-a1d3-79c487d371a3 --skipFeatureDeployment
```

## Response

The command won't return a response on success.

## More information

- Application Lifecycle Management (ALM) APIs: [https://learn.microsoft.com/sharepoint/dev/apis/alm-api-for-spfx-add-ins](https://learn.microsoft.com/sharepoint/dev/apis/alm-api-for-spfx-add-ins)
