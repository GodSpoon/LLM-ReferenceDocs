-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo site recyclebinitem move

Moves items from the first-stage recycle bin to the second-stage recycle bin

## Usage

```sh
m365 spo site recyclebinitem move [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: URL of the site where the recycle bin is located.

`-i, --ids [ids]`
: Comma separated list of item IDs. Specify either `ids` or `all` but not both.

`--all`
: Move all first-stage recycle bin items to the second-stage recycle bin. Specify either `ids` or `all` but not both.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Move 2 specific items from the first-stage recycle bin to the second-stage

```sh
m365 spo site recyclebinitem move --siteUrl https://contoso.sharepoint.com/sites/sales --ids "06ca4fe4-3048-4b76-bd41-296fed4c9881,d679c17b-d7b8-429a-9307-34e1d9e631e7"
```

Move all first-stage recycle bin items to the second-stage

```sh
m365 spo site recyclebinitem move --siteUrl https://contoso.sharepoint.com/sites/sales --all
```

## Response

The command won't return a response on success.
