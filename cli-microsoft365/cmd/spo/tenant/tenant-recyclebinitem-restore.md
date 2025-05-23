-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo tenant recyclebinitem restore

Restores the specified deleted Site Collection from Tenant Recycle Bin

## Usage

```sh
m365 spo tenant recyclebinitem restore [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: URL of the site.
```

<Global />

## Remarks

:::info

To use this command you must be a Global or SharePoint administrator.

:::
    
## Examples

Restores a deleted site collection from tenant recycle bin.

```sh
m365 spo tenant recyclebinitem restore --siteUrl https://contoso.sharepoint.com/sites/team
```

## Response

The command won't return a response on success.
