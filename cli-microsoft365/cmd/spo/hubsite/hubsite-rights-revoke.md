-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo hubsite rights revoke

Revokes rights to join sites to the specified hub site for one or more principals

## Usage

```sh
m365 spo hubsite rights revoke [options]
```

## Options

```md definition-list
`-u, --hubSiteUrl <hubSiteUrl>`
: The URL of the hub site to revoke rights on.

`-p, --principals <principals>`
: Comma-separated list of principals to revoke join rights. Principals can be users or mail-enabled security groups in the form of `alias` or `alias@<domain name>.com`.

`-f, --force`
: Don't prompt for confirming revoking rights
```

<Global />

## Remarks

:::info

To use this command you must be a Global or SharePoint administrator.

:::

## Examples

Revoke rights to join sites to the hub site with specific URL. from user with specific alias. Will prompt for confirmation before revoking the rights.

```sh
m365 spo hubsite rights revoke --hubSiteUrl https://contoso.sharepoint.com/sites/sales --principals PattiF
```

Revoke rights to join sites to the hub site with specific URL. from user with specific aliases without prompting for confirmation.

```sh
m365 spo hubsite rights revoke --hubSiteUrl https://contoso.sharepoint.com/sites/sales --principals "PattiF,AdeleV" --force
```

## Response

The command won't return a response on success.

## More information

- SharePoint hub sites new in Microsoft 365: [https://techcommunity.microsoft.com/t5/SharePoint-Blog/SharePoint-hub-sites-new-in-Office-365/ba-p/109547](https://techcommunity.microsoft.com/t5/SharePoint-Blog/SharePoint-hub-sites-new-in-Office-365/ba-p/109547)
