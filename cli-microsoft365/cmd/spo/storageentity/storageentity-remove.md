-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo storageentity remove

Removes tenant property stored on the specified SharePoint Online app catalog

## Usage

```sh
m365 spo storageentity remove [options]
```

## Options

```md definition-list
`-u, --appCatalogUrl <appCatalogUrl>`
: URL of the app catalog site

`-k, --key <key>`
: Name of the tenant property to retrieve

`-f, --force`
: Don't prompt for confirming removal of a tenant property
```

<Global />

## Remarks

Tenant properties are stored in the app catalog site associated with that tenant. To remove a property, you have to specify the absolute URL of the app catalog site. If you specify the URL of a site different than the app catalog, you will get an access denied error.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::
    
## Examples

Remove the _AnalyticsId_ tenant property. Yields a confirmation prompt before actually removing the property

```sh
m365 spo storageentity remove -k AnalyticsId -u https://contoso.sharepoint.com/sites/appcatalog
```

Remove the _AnalyticsId_ tenant property. Suppresses the confirmation prompt

```sh
m365 spo storageentity remove -k AnalyticsId --force -u https://contoso.sharepoint.com/sites/appcatalog
```

## Response

The command won't return a response on success.

## More information

- SharePoint Framework Tenant Properties: [https://learn.microsoft.com/sharepoint/dev/spfx/tenant-properties](https://learn.microsoft.com/sharepoint/dev/spfx/tenant-properties)
