-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo app install

Installs an app from the specified app catalog in the site

## Usage

```sh
m365 spo app install [options]
```

## Options

```md definition-list
`-i, --id <id>`
: ID of the app to install.

`-s, --siteUrl <siteUrl>`
: Absolute URL of the site to install the app in.

`--appCatalogScope [appCatalogScope]`
: Scope of the app catalog. Allowed values: `tenant`, `sitecollection`. Defaults to `tenant`.
```

<Global />

## Remarks

If the app with the specified ID doesn't exist in the app catalog, the command will fail with an error. Before you can install app in a site, you have to add it to the tenant or site collection app catalog first using the [spo app add](./app-add.mdx) command.

## Examples

Install the app with the specified ID in the specified site.

```sh
m365 spo app install --id b2307a39-e878-458b-bc90-03bc578531d6 --siteUrl https://contoso.sharepoint.com
```

Install the app with the specified ID in the specified site from site collection app catalog.

```sh
m365 spo app install --id b2307a39-e878-458b-bc90-03bc578531d6 --siteUrl https://contoso.sharepoint.com --appCatalogScope sitecollection
```

## Response

The command won't return a response on success.

## More information

- Application Lifecycle Management (ALM) APIs: [https://learn.microsoft.com/sharepoint/dev/apis/alm-api-for-spfx-add-ins](https://learn.microsoft.com/sharepoint/dev/apis/alm-api-for-spfx-add-ins)
