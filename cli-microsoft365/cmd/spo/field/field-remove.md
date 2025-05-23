-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo field remove

Removes the specified list- or site column

## Usage

```sh
m365 spo field remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Absolute URL of the site where the field to remove is located.

`-l, --listTitle [listTitle]`
: Title of the list where the field is located. Specify either `listTitle`, `listId` or `listUrl`.

`--listId [listId]`
: ID of the list where the field is located. Specify either `listTitle`, `listId` or `listUrl`.

`--listUrl [listUrl]`
: Server- or web-relative URL of the list where the field is located. Specify either `listTitle`, `listId` or `listUrl`.

`-i, --id [id]`
: The ID of the field to remove. Specify either `id`, `title`, `internalName`, or `group`.

`-t, --title [title]`
: The display name (case-sensitive) of the field to remove. Specify either `id`, `title`, `internalName`, or `group`.

`--internalName [internalName]`
: The internal name (case-sensitive) of the field to remove. Specify either `id`, `title`, `internalName`, or `group`.

`-g, --group [group]`
: Delete all fields from this group (case-sensitive). Specify either `id`, `title`, `internalName`, or `group`.

`-f, --force`
: Don't prompt for confirming removing the field.
```

<Global />

## Examples

Remove the site column with the specified ID, located in the specified site.

```sh
m365 spo field remove --webUrl https://contoso.sharepoint.com/sites/contoso-sales --id 5ee2dd25-d941-455a-9bdb-7f2c54aed11b
```

Remove the list column with the specified ID, located in the specified site. Retrieves the list by its title.

```sh
m365 spo field remove --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listTitle Events --id 5ee2dd25-d941-455a-9bdb-7f2c54aed11b
```

Remove the list column with the specified display name, located in the specified site. Retrieves the list by its url.

```sh
m365 spo field remove --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listUrl "Lists/Events" --title "Title"
```

Remove the list column with the specified display name, located in the specified site. Retrieves the list by its url.

```sh
m365 spo field remove --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listUrl "Lists/Events" --internalName "Title"
```

Remove all site columns from the specified group.

```sh
m365 spo field remove --webUrl https://contoso.sharepoint.com/sites/contoso-sales --group "MyGroup"
```

## Response

The command won't return a response on success.
