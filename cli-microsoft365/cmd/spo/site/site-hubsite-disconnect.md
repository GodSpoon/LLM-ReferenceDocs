-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo site hubsite disconnect

Disconnects the specified site collection from its hub site

## Usage

```sh
m365 spo site hubsite disconnect [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: URL of the site collection to disconnect from its hub site

`-f, --force`
: Don't prompt for confirmation
```

<Global />

## Examples

Disconnect a specific site collection from its hub site. Will prompt for confirmation before disconnecting from the hub site.

```sh
m365 spo site hubsite disconnect --siteUrl https://contoso.sharepoint.com/sites/sales
```

Disconnect a specific site collection from its hub site without prompting for confirmation.

```sh
m365 spo site hubsite disconnect --siteUrl https://contoso.sharepoint.com/sites/sales --force
```

## Response

The command won't return a response on success.

## More information

- SharePoint hub sites new in Microsoft 365: [https://techcommunity.microsoft.com/t5/SharePoint-Blog/SharePoint-hub-sites-new-in-Office-365/ba-p/109547](https://techcommunity.microsoft.com/t5/SharePoint-Blog/SharePoint-hub-sites-new-in-Office-365/ba-p/109547)
