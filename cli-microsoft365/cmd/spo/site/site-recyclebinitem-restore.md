-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo site recyclebinitem restore

Restores given items from the site recycle bin

## Usage

```sh
m365 spo site recyclebinitem restore [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: URL of the site.

`-i, --ids [ids]`
: List of ids of items which will be restored from the site recycle bin. Specify `ids` or `allPrimary` and/or `allSecondary`.

`--allPrimary`
: Restore all items from the first-stage recycle bin. Specify `ids` or `allPrimary` and/or `allSecondary`.

`--allSecondary`
: Restore all items from the second-stage recycle bin. Specify `ids` or `allPrimary` and/or `allSecondary`.
```

<Global />

## Examples

Restore specific items by given ids from recycle bin of given site.

```sh
m365 spo site recyclebinitem restore --siteUrl https://contoso.sharepoint.com/sites/project --ids "ae6f97a7-280e-48d6-b481-0ea986c323da,aadbf916-1f71-42ee-abf2-8ee4802ae291"
```

Restore all items from the first-stage recycle bin of a given site.

```sh
m365 spo site recyclebinitem restore --siteUrl https://contoso.sharepoint.com/sites/project --allPrimary
```

Restore all items from the second-stage recycle bin of a given site.

```sh
m365 spo site recyclebinitem restore --siteUrl https://contoso.sharepoint.com --allSecondary
```

Restore all items from both the first-stage and second-stage recycle bins of a given site.

```sh
m365 spo site recyclebinitem restore --siteUrl https://contoso.sharepoint.com --allPrimary --allSecondary
```

## Response

The command won't return a response on success.
