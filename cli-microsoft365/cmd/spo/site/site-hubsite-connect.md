-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo site hubsite connect

Connects the specified site collection to the given hub site

## Usage

```sh
m365 spo site hubsite connect [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: The URL of the site collection to connect to the hub site

`-i, --id <id>`
: The ID of the hub site to which to connect the site collection
```

<Global />

## Remarks

If the specified site collection is already connected to a hub site, it will be disconnected and connected to the newly specified hub site.

If the specified `id` doesn't point to a valid hub site, you will get a `ResourceNotFoundException` error.

## Examples

Connect a specific site collection to a hub site

```sh
m365 spo site hubsite connect --siteUrl https://contoso.sharepoint.com/sites/contoso-sales --id 255a50b2-527f-4413-8485-57f4c17a24d1
```

## Response

The command won't return a response on success.

## More information

- SharePoint hub sites new in Microsoft 365: [https://techcommunity.microsoft.com/t5/SharePoint-Blog/SharePoint-hub-sites-new-in-Office-365/ba-p/109547](https://techcommunity.microsoft.com/t5/SharePoint-Blog/SharePoint-hub-sites-new-in-Office-365/ba-p/109547)
