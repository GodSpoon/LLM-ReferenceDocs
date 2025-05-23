-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo list webhook remove

Removes the specified webhook from the list

## Usage

```sh
m365 spo list webhook remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list is located.

`-l, --listId [listId]`
: ID of the list. Specify either `listId`, `listTitle` or `listUrl`.

`-t, --listTitle [listTitle]`
: Title of the list. Specify either `listId`, `listTitle` or `listUrl`.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listId`, `listTitle` or `listUrl`.

`-i, --id <id>`
: ID of the webhook.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

If the specified id doesn't refer to an existing webhook, you will get a `404 - "404 FILE NOT FOUND"` error.

## Examples

Remove webhook with a specific ID from a list retrieved by ID in a specific site

```sh
m365 spo list webhook remove --webUrl https://contoso.sharepoint.com/sites/ninja --listId 0cd891ef-afce-4e55-b836-fce03286cccf --id cc27a922-8224-4296-90a5-ebbc54da2e81
```

Remove webhook with a specific ID from a list retrieved by Title in a specific site
```sh
m365 spo list webhook remove --webUrl https://contoso.sharepoint.com/sites/ninja --listTitle Documents --id cc27a922-8224-4296-90a5-ebbc54da2e81
```

Remove webhook with a specific ID from a list retrieved by URL in a specific site without being asked for confirmation

```sh
m365 spo list webhook remove --webUrl https://contoso.sharepoint.com/sites/ninja --listUrl '/sites/ninja/Documents' --id cc27a922-8224-4296-90a5-ebbc54da2e81 --force
```

## Response

The command won't return a response on success.
