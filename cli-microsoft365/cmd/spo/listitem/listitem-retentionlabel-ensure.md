-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo listitem retentionlabel ensure

Apply a retention label to a list item

## Usage

```sh
m365 spo listitem retentionlabel ensure [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the retentionlabel from a list item to apply is located.

`--listItemId <listItemId>`
: The ID of the list item for which the retention label should be applied.

`--listId [listId]`
: ID of the list where the retention label should be applied. Specify either `listTitle`, `listId` or `listUrl`.

`--listTitle [listTitle]`
: Title of the list where the retention label should be applied. Specify either `listTitle`, `listId` or `listUrl`.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listTitle`, `listId` or `listUrl`.

`-n, --name [name]`
: The name of the retention label. Specify either `name` or `id`.

`-i, --id [id]`
: The id of the retention label. Specify either `name` or `id`.

`-a, --assetId [assetId]`
: A Compliance Asset Id to set on the item when it's labeled. See below for more information.
```

<Global />

## Remarks

The `--assetId` option has to do with event-based retention. Event-based retention is about starting a retention period when a specific event occurs, instead of the moment a document was labeled or created.

## Examples

Applies a retention label to a list item in a given site based on the list id and label name

```sh
m365 spo listitem retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --listId 0cd891ef-afce-4e55-b836-fce03286cccf --listItemId 1 --name 'Some label'
```

Applies a retention label to a list item in a given site based on the list title and label id

```sh
m365 spo listitem retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'List 1' --listItemId 1 --id '7a621a91-063b-461b-aff6-d713d5fb23eb'
```

Applies a retention label to a list item in a given site based on the server relative list url

```sh
m365 spo listitem retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl /sites/project-x/lists/TestList --listItemId 1 --name 'Some label'
```

Applies a retention label to a list item in a given site based on the server relative list url and updates the Asset Id field

```sh
m365 spo listitem retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl /sites/project-x/lists/TestList --listItemId 1 --name 'Some label' --assetId 'XYZ'
```

## Response

The command won't return a response on success.
