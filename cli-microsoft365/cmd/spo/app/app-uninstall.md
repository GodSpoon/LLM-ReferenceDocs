-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo app uninstall

Uninstalls an app from the site

## Usage

```sh
m365 spo app uninstall [options]
```

## Options

```md definition-list
`-i, --id <id>`
: ID of the app to uninstall.

`-s, --siteUrl <siteUrl>`
: Absolute URL of the site to uninstall the app from.

`--appCatalogScope [appCatalogScope]`
: Scope of the app catalog. Allowed values: `tenant`, `sitecollection`. Defaults to `tenant`.

`-f, --force`
: Don't prompt for confirming uninstalling the app.
```

<Global />

## Remarks

If the app with the specified ID doesn't exist in the app catalog, the command will fail with an error.

## Examples

Uninstall the app with the specified ID from the specified  site.

```sh
m365 spo app uninstall --id b2307a39-e878-458b-bc90-03bc578531d6 --siteUrl https://contoso.sharepoint.com
```

Uninstall the app with the specified ID from the specified site without prompting for confirmation.

```sh
m365 spo app uninstall --id b2307a39-e878-458b-bc90-03bc578531d6 --siteUrl https://contoso.sharepoint.com --force
```

Uninstall the app with the specified ID from the specified site where the app is deployed to the site collection app catalog.

```sh
m365 spo app uninstall --id b2307a39-e878-458b-bc90-03bc578531d6 --siteUrl https://contoso.sharepoint.com --appCatalogScope sitecollection
```

## Response

The command won't return a response on success.

## More information

- Application Lifecycle Management (ALM) APIs: [https://learn.microsoft.com/sharepoint/dev/apis/alm-api-for-spfx-add-ins](https://learn.microsoft.com/sharepoint/dev/apis/alm-api-for-spfx-add-ins)
