-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo tenant site archive

Archives a site collection

## Usage

```sh
m365 spo tenant site archive [options]
```

## Options

```md definition-list
`-u, --url <url>`
: URL of the site collection.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::info

To use this command, you must be a Global or SharePoint administrator.

:::

:::note

After running this command, it may take a few minutes for the site to be fully archived.

:::


## Examples

Archive a specific SharePoint site collection

```sh
m365 spo tenant site archive --url "https://contoso.sharepoint.com/sites/Marketing"
```

Archive a specific SharePoint site collection without confirmation prompt

```sh
m365 spo tenant site archive --url "https://contoso.sharepoint.com/sites/Marketing" --force
```

## Response

The command won't return a response on success.

## More information

- Pricing model for Microsoft 365 Archive: [https://learn.microsoft.com/microsoft-365/archive/archive-pricing](https://learn.microsoft.com/microsoft-365/archive/archive-pricing)
- Set up Microsoft 365 Archive: [https://learn.microsoft.com/microsoft-365/archive/archive-setup](https://learn.microsoft.com/microsoft-365/archive/archive-setup)
