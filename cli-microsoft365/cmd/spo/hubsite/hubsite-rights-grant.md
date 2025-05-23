-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo hubsite rights grant

Grants permissions to join the hub site for one or more principals

## Usage

```sh
m365 spo hubsite rights grant [options]
```

## Options

```md definition-list
`-u, --hubSiteUrl <hubSiteUrl>`
: The URL of the hub site to grant rights on.

`-p, --principals <principals>`
: Comma-separated list of principals to grant join rights. Principals can be users or mail-enabled security groups in the form of `alias` or `alias@<domain name>.com`.

`-r, --rights <rights>`
: Rights to grant to principals. Available values `Join`.
```

<Global />

## Remarks

:::info

To use this command you must be a Global or SharePoint administrator.

:::

## Examples

Grant user with specific alias, permission to join sites to the hub site with specific URL.

```sh
m365 spo hubsite rights grant --hubSiteUrl https://contoso.sharepoint.com/sites/sales --principals PattiF --rights Join
```

Grant users with specific aliases, permission to join sites to the hub site with specific URL.

```sh
m365 spo hubsite rights grant --hubSiteUrl https://contoso.sharepoint.com/sites/sales --principals "PattiF,AdeleV" --rights Join
```

Grant user with specific email, permission to join sites to the hub site with specific URL.

```sh
m365 spo hubsite rights grant --hubSiteUrl https://contoso.sharepoint.com/sites/sales --principals PattiF@contoso.com --rights Join
```

## Response

The command won't return a response on success.

## More information

- SharePoint hub sites new in Microsoft 365: [https://techcommunity.microsoft.com/t5/SharePoint-Blog/SharePoint-hub-sites-new-in-Office-365/ba-p/109547](https://techcommunity.microsoft.com/t5/SharePoint-Blog/SharePoint-hub-sites-new-in-Office-365/ba-p/109547)
