-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo site inplacerecordsmanagement set

Activates or deactivates in-place records management for a site collection

## Usage

```sh
m365 spo site inplacerecordsmanagement set [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: The URL of the site on which to activate or deactivate in-place records management

`--enabled <enabled>`
: Set to `true` to activate in-place records management and to `false` to deactivate it
```

<Global />

## Examples

Activates in-place records management for site _https://contoso.sharepoint.com/sites/team-a_

```sh
m365 spo site inplacerecordsmanagement set --siteUrl https://contoso.sharepoint.com/sites/team-a --enabled true
```

Deactivates in-place records management for site _https://contoso.sharepoint.com/sites/team-a_

```sh
m365 spo site inplacerecordsmanagement set --siteUrl https://contoso.sharepoint.com/sites/team-a --enabled false
```

## Response

The command won't return a response on success.
