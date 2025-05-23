-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo list retentionlabel ensure

Sets a default retention label on the specified list or library.

## Usage

```sh
m365 spo list retentionlabel ensure [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the list is located.

`--name <name>`
: The label name to set on the list.

`-t, --listTitle [listTitle]`
: The title of the list on which to set the label. Specify either `listTitle`, `listId`, or `listUrl` but not multiple.

`-l, --listId [listId]`
: The ID of the list on which to set the label. Specify either `listTitle`, `listId`, or `listUrl` but not multiple.

`--listUrl [listUrl]`
: Server- or web-relative URL of the list on which to set the label. Specify either `listTitle`, `listId`, or `listUrl` but not multiple.

`--syncToItems`
: Specify, to set the label on all existing items in the list.
```

<Global />

## Remarks

A list retention label is a default label that will be applied to all new items in the list. If you specify `syncToItems`, it is also synced to existing items. 

## Examples

Sets a retention label by name on a given list.

```sh
m365 spo list retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl 'Shared Documents' --name 'Some label'
```

Sets a retention label by name and syncs this to all existing items for a given list.

```sh
m365 spo list retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'Documents' --name 'Some label' --syncToItems
```

## Response

The command won't return a response on success.
