-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spp model apply

Applies (or syncs) a trained document understanding model to a document library

## Usage

```sh
m365 spp model apply [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the web where the library is located.

`-c, --contentCenterUrl <contentCenterUrl>`
: The URL of the content center site where model is located.

`-i, --id [id]`
: The unique ID of the model. Specify either `id` or `title` but not both.

`-t, --title [title]`
: The display name of the model. Specify either `id` or `title` but not both.

`--listTitle [listTitle]`
: The title of the document library to which the model will be applied. Specify either `listTitle`, `listId`, or `listUrl` but not multiple.

`--listId [listId]`
: The ID of the library to which the model will be applied. Specify either `listTitle`, `listId`, or `listUrl` but not multiple.

`--listUrl [listUrl]`
: Server or web-relative URL of the library to which the model will be applied. Specify either `listTitle`, `listId`, or `listUrl` but not multiple.

`--viewOption [viewOption]`
: Defines whether the model view should be set as the default view for the document library. Allowed values are: `NewViewAsDefault`, `DoNotChangeDefault`, `TileViewAsDefault`. The default value is `NewViewAsDefault`.
```

<Global />

## Examples

Applies a trained document understanding model using its unique ID to a document library, identified by its title.

```sh
m365 spp model apply --webUrl "https://contoso.sharepoint.com" --contentCenterUrl "https://contoso.sharepoint.com/sites/ContentCenter" --id "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc" --listTitle "Shared Documents"
```

Applies a trained document understanding model using its display name to a document library, identified by its title.

```sh
m365 spp model apply --webUrl "https://contoso.sharepoint.com" --contentCenterUrl "https://contoso.sharepoint.com/sites/ContentCenter" --title "ModelExample" --listTitle "Shared Documents"
```

Applies a trained document understanding model using its display name to a document library, identified by its URL.

```sh
m365 spp model apply --webUrl "https://contoso.sharepoint.com" --contentCenterUrl "https://contoso.sharepoint.com/sites/ContentCenter" --title "ModelExample" --listUrl "/Shared Documents"
```

Applies a trained document understanding model using its display name to a document library, identified by its unique ID.

```sh
m365 spp model apply --webUrl "https://contoso.sharepoint.com" --contentCenterUrl "https://contoso.sharepoint.com/sites/ContentCenter" --title "ModelExample" --listId "b4cfa0d9-b3d7-49ae-a0f0-f14ffdd005f7"
```

Applies a trained document understanding model using its display name to a document library, identified by its unique ID. Without changing a default document library view.

```sh
m365 spp model apply --webUrl "https://contoso.sharepoint.com" --contentCenterUrl "https://contoso.sharepoint.com/sites/ContentCenter" --title "ModelExample" --listId "b4cfa0d9-b3d7-49ae-a0f0-f14ffdd005f7" --viewOption "DoNotChangeDefault"
```

## Response

The command won't return a response on success.
