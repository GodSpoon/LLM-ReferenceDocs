-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo app retract

Retracts the specified app from the specified app catalog

## Usage

```sh
m365 spo app retract [options]
```

## Options

```md definition-list
`-i, --id <id>`
: ID of the app to retract. Needs to be available in the app catalog.

`-u, --appCatalogUrl [appCatalogUrl]`
: URL of the tenant or site collection app catalog. It must be specified when the scope is `sitecollection`.

`-s, --appCatalogScope [appCatalogScope]`
: Scope of the app catalog. Allowed values: `tenant`, `sitecollection`. Defaults to `tenant`.

`-f, --force`
: Don't prompt for confirming retracting the app.
```

<Global />

## Remarks

When getting information about an app from the tenant app catalog, it's not necessary to specify the tenant app catalog URL. When the URL is not specified, the CLI will try to resolve the URL itself. Specifying the app catalog URL is required when you want to get information about an app from a site collection app catalog.

When specifying site collection app catalog, you can specify the URL either with our without the _AppCatalog_ part, for example `https://contoso.sharepoint.com/sites/team-a/AppCatalog` or `https://contoso.sharepoint.com/sites/team-a`. CLI will accept both formats.

If the app with the specified ID doesn't exist in the app catalog, the command will fail with an error.

## Examples

Retract the specified app from the tenant app catalog. Try to resolve the URL of the tenant app catalog automatically. Additionally, will prompt for confirmation before actually retracting the app.

```sh
m365 spo app retract --id 058140e3-0e37-44fc-a1d3-79c487d371a3
```

Retract the specified app from the tenant app catalog. Additionally, will prompt for confirmation before actually retracting the app.

```sh
m365 spo app retract --id 058140e3-0e37-44fc-a1d3-79c487d371a3 --appCatalogUrl https://contoso.sharepoint.com/sites/apps
```

Retract the specified app from the tenant app catalog. Try to resolve the URL of the tenant app catalog automatically. Will not prompt for confirmation before retracting the app.

```sh
m365 spo app retract --id 058140e3-0e37-44fc-a1d3-79c487d371a3 --force
```

Retract the specified app from a site collection app catalog of the specified site.

```sh
m365 spo app retract --id d95f8c94-67a1-4615-9af8-361ad33be93c --appCatalogScope sitecollection --appCatalogUrl https://contoso.sharepoint.com/sites/site1
```

## Response

The command won't return a response on success.

## More information

- Application Lifecycle Management (ALM) APIs: [https://learn.microsoft.com/sharepoint/dev/apis/alm-api-for-spfx-add-ins](https://learn.microsoft.com/sharepoint/dev/apis/alm-api-for-spfx-add-ins)
