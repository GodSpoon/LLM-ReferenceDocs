-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo site appcatalog add

Creates a site collection app catalog in the specified site

## Usage

```sh
m365 spo site appcatalog add [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: URL of the site collection where the app catalog should be added
```

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Add a site collection app catalog to the specified site

```sh
m365 spo site appcatalog add --siteUrl https://contoso.sharepoint.com/sites/site
```

## Response

The command won't return a response on success.

## More information

- Use the site collection app catalog: [https://learn.microsoft.com/sharepoint/dev/general-development/site-collection-app-catalog](https://learn.microsoft.com/sharepoint/dev/general-development/site-collection-app-catalog)
