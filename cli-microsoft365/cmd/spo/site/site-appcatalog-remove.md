-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo site appcatalog remove

Removes site collection app catalog from the specified site

## Usage

```sh
m365 spo site appcatalog remove [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: URL of the site collection containing the app catalog to disable.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

While the command uses the term *'remove'*, like its equivalent PowerShell cmdlet, it does not remove the special library **Apps for SharePoint** from the site collection. Instead, it disables the site collection app catalog in that site. Packages deployed to the app catalog are not available within the site collection.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::
    
## Examples

Remove the site collection app catalog from specified site.

```sh
m365 spo site appcatalog remove --siteUrl https://contoso.sharepoint/sites/site
```

Remove the site collection app catalog from specified site without prompting for confirmation.

```sh
m365 spo site appcatalog remove --siteUrl https://contoso.sharepoint/sites/site --force
```

## Response

The command won't return a response on success.

## More information

- Use the site collection app catalog: [https://learn.microsoft.com/sharepoint/dev/general-development/site-collection-app-catalog](https://learn.microsoft.com/sharepoint/dev/general-development/site-collection-app-catalog)
