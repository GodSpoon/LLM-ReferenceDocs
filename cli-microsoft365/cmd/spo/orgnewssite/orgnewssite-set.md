-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo orgnewssite set

Marks site as an organizational news site

## Usage

```sh
m365 spo orgnewssite set [options]
```

## Options

```md definition-list
`-u, --url <url>`
: The URL of the site to mark as an organizational news site.
```

<Global />

## Remarks

Using the `-u, --url` option you can specify which site to add to the list of organizational news sites.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::
    
## Examples

Set a site as an organizational news site

```sh
m365 spo orgnewssite set --url https://contoso.sharepoint.com/sites/site1
```

## Response

The command won't return a response on success.
