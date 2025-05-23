-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo orgnewssite remove

Removes a site from the list of organizational news sites

## Usage

```sh
m365 spo orgnewssite remove [options]
```

## Options

```md definition-list
`-u, --url <url>`
: Absolute URL of the site to remove.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Remove a site from the list of organizational news

```sh
m365 spo orgnewssite remove --url https://contoso.sharepoint.com/sites/site1
```

Remove a site from the list of organizational news sites, without prompting for confirmation

```sh
m365 spo orgnewssite remove --url https://contoso.sharepoint.com/sites/site1 --force
```

## Response

The command won't return a response on success.
