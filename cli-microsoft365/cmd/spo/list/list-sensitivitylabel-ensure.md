-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo list sensitivitylabel ensure

Applies a default sensitivity label to the specified document library

## Usage

```sh
m365 spo list sensitivitylabel ensure [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the library is located.

`-n, --name [name]`
: The label name to apply to the list. Specify either `name` or `id`, but not both.

`-i, --id [id]`
: The Id of the label to apply to the list. Specify either `name` or `id`, but not both.

`-t, --listTitle [listTitle]`
: The title of the library on which to apply the label. Specify either `listTitle`, `listId`, or `listUrl` but not multiple.

`-l, --listId [listId]`
: The ID of the library on which to apply the label. Specify either `listTitle`, `listId`, or `listUrl` but not multiple.

`--listUrl [listUrl]`
: Server- or web-relative URL of the library on which to apply the label. Specify either `listTitle`, `listId`, or `listUrl` but not multiple.
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reaches general availability.

:::

## Examples

Applies a sensitivity label by id to a document library based on the list title.

```sh
m365 spo list sensitivitylabel ensure --webUrl 'https://contoso.sharepoint.com' --listTitle 'Shared Documents' --id '0d39dc11-75ff-4309-8b32-ff94f0e41607'
```

Applies a sensitivity label by name to a document library based on the list title.

```sh
m365 spo list sensitivitylabel ensure --webUrl 'https://contoso.sharepoint.com' --listTitle 'Shared Documents' --name 'Confidential'
```

Applies a sensitivity label by name to a document library based on the list url.

```sh
m365 spo list sensitivitylabel ensure --webUrl 'https://contoso.sharepoint.com' --listUrl '/Shared Documents' --name 'Confidential'
```

Applies a sensitivity label by name to a document library based on the list id.

```sh
m365 spo list sensitivitylabel ensure --webUrl 'https://contoso.sharepoint.com' --listId 'b4cfa0d9-b3d7-49ae-a0f0-f14ffdd005f7' --name 'Confidential'
```

## Response

The command won't return a response on success.
