-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo hubsite unregister

Unregisters the specified site collection as a hub site

## Usage

```sh
m365 spo hubsite unregister [options]
```

## Options

```md definition-list
`-u, --url <url>`
: URL of the site collection.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::info

To use this command you must be a Global or SharePoint administrator.

:::

If the specified site collection is not registered as a hub site, you will get a `hubSiteId` error.

## Examples

Unregister the site collection with specific URL. as a hub site. Will prompt for confirmation before unregistering the hub site.

```sh
m365 spo hubsite unregister --url https://contoso.sharepoint.com/sites/sales
```

Unregister the site collection with specific URL. as a hub site without prompting for confirmation.

```sh
m365 spo hubsite unregister --url https://contoso.sharepoint.com/sites/sales --force
```

## Response

The command won't return a response on success.

## More information

- SharePoint hub sites new in Microsoft 365: [https://techcommunity.microsoft.com/t5/SharePoint-Blog/SharePoint-hub-sites-new-in-Office-365/ba-p/109547](https://techcommunity.microsoft.com/t5/SharePoint-Blog/SharePoint-hub-sites-new-in-Office-365/ba-p/109547)
