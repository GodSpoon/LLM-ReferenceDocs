<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo list contenttype remove

Removes content type from list

## Usage

```sh
m365 spo list contenttype remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list is located.

`-l, --listId [listId]`
: ID of the list. Specify either `listTitle`, `listId`, or `listUrl`.

`-t, --listTitle [listTitle]`
: Title of the list. Specify either `listTitle`, `listId`, or `listUrl`.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listTitle`, `listId`, or `listUrl`.

`-i, --id <id>`
: ID of the content type to remove from the list.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Remove content type with a specific id from the list retrieved by id in a specific site.

```sh
m365 spo list contenttype remove --webUrl https://contoso.sharepoint.com/sites/project-x --listId 0cd891ef-afce-4e55-b836-fce03286cccf --id EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

Remove content type with a specific id from the list retrieved by title in a specific site.

```sh
m365 spo list contenttype remove --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle Documents --id EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

Remove content type with a specific id from the list retrieved by server relative URL in a specific site. This will not prompt for confirmation.

```sh
m365 spo list contenttype remove --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl 'sites/project-x/Documents' --id EXAMPLE_SECRET_VALUE_PLACEHOLDER --force
```

## Response

The command won't return a response on success.
