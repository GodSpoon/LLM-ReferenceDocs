-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo list retentionlabel remove

Clears the retention label on the specified list or library.

## Usage

```sh
m365 spo list retentionlabel remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the list is located.

`-t, --listTitle [listTitle]`
: The title of the list on which to remove the label. Specify either `listTitle`, `listId`, or `listUrl` but not multiple.

`-i, --listId [listId]`
: The ID of the list on which to remove the label. Specify either `listTitle`, `listId`, or `listUrl` but not multiple.

`-l, --listUrl [listUrl]`
: Server- or web-relative URL of the list on which to remove the label. Specify either `listTitle`, `listId`, or `listUrl` but not multiple.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Clears the retention label on a given list by URL.

```sh
m365 spo list retentionlabel remove --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl 'Shared Documents'
```

Clears the retention label on a given list by title.

```sh
m365 spo list retentionlabel remove --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'Documents'
```

Clears the retention label on a given list by ID without confirmation.

```sh
m365 spo list retentionlabel remove --webUrl https://contoso.sharepoint.com/sites/project-x --listId 'Documents' --force
```

## Response

The command won't return a response on success.
