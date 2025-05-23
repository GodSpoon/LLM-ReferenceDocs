-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo site remove

Removes the specified site

## Usage

```sh
m365 spo site remove [options]
```

## Options

```md definition-list
`-u, --url <url>`
: URL of the site.

`--skipRecycleBin`
: Set to directly remove the site without moving it to the recycle bin.

`--fromRecycleBin`
: Set to remove the site from the recycle bin.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

If the argument `--fromRecycleBin` is passed, the selected site will be permanently removed even if it's a groupified one.

:::info

To use this command you must be a Global or SharePoint administrator.

:::

## Examples

Remove the specified site and place it in the recycle bin.

```sh
m365 spo site remove --url https://contoso.sharepoint.com/sites/demosite
```

Remove the site without moving it to the recycle bin.

```sh
m365 spo site remove --url https://contoso.sharepoint.com/sites/demosite --skipRecycleBin
```

Remove the previously deleted site from the recycle bin.

```sh
m365 spo site remove --url https://contoso.sharepoint.com/sites/demosite --fromRecycleBin
```

## Response

The command won't return a response on success.
