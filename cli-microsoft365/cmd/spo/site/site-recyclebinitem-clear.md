-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo site recyclebinitem clear

Permanently removes all items in a site recycle bin

## Usage

```sh
m365 spo site recyclebinitem clear [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: URL of the site where the recycle bin is located.

`--secondary`
: Remove all items from the second-stage recycle bin. When not specified, items from the first-stage recycle bin will be cleared.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::warning

Items in the recycle bin will be permanently removed without the ability to restore them.

:::

## Examples

Clear all items from the first-stage recycle bin

```sh
m365 spo site recyclebinitem clear --siteUrl https://contoso.sharepoint.com/sites/sales
```

Clear all items from the second-stage recycle bin

```sh
m365 spo site recyclebinitem clear --siteUrl https://contoso.sharepoint.com/sites/sales --secondary
```

## Response

The command won't return a response on success.
