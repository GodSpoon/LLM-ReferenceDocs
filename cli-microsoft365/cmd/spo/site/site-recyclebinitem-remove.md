-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo site recyclebinitem remove

Permanently deletes specific items from the site recycle bin

## Usage

```sh
m365 spo site recyclebinitem remove [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: URL of the site where the recycle bin is located.

`-i, --ids <ids>`
: Comma separated list of item IDs.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::warning

Items in the recycle bin will be permanently removed without the ability to restore them.

:::

## Examples

Permanently remove 2 specific items from the recycle bin

```sh
m365 spo site recyclebinitem remove --siteUrl https://contoso.sharepoint.com/sites/sales --ids "06ca4fe4-3048-4b76-bd41-296fed4c9881,d679c17b-d7b8-429a-9307-34e1d9e631e7"
```

Permanently remove 2 specific items from the recycle bin and skip the confirmation prompt

```sh
m365 spo site recyclebinitem remove --siteUrl https://contoso.sharepoint.com/sites/sales --ids "06ca4fe4-3048-4b76-bd41-296fed4c9881,d679c17b-d7b8-429a-9307-34e1d9e631e7" --force
```

## Response

The command won't return a response on success.
