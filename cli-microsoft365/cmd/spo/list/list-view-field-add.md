-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo list view field add

Adds the specified field to list view

## Usage

```sh
m365 spo list view field add [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list is located.

`--listId [listId]`
: ID of the list where the view is located. Specify either `listId`, `listTitle`, or `listUrl`.

`--listTitle [listTitle]`
: Title of the list where the view is located. Specify either `listId`, `listTitle`, or `listUrl`.

 `--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listId` , `listTitle` or `listUrl`.

`--viewId [viewId]`
: ID of the view to update. Specify `viewTitle` or `viewId` but not both.

`--viewTitle [viewTitle]`
: Title of the view to update. Specify `viewTitle` or `viewId` but not both.

`--id [id]`
: ID of the field to add. Specify `id` or `title` but not both.

`--title [title]`
: The **case-sensitive** internal name or display name of the field to add. Specify `id` or `title` but not both.

`--position [position]`
: The zero-based index of the position for the field.
```

<Global />

## Examples

Add field with ID to view with ID of the list with ID located in a specific site.

```sh
m365 spo list view field add --webUrl https://contoso.sharepoint.com/sites/project-x --listId 1f187321-f086-4d3d-8523-517e94cc9df9 --viewId 3d760127-982c-405e-9c93-e1f76e1a1110 --id 330f29c5-5c4c-465f-9f4b-7903020ae1ce
```

Add field with title to view with title of the list with title _Documents_ located in a specific site.

```sh
m365 spo list view field add --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle Documents --viewTitle 'All Documents' --title 'Custom field'
```

Add field with title at the position to view with title of the list with url located in a specific site.

```sh
m365 spo list view field add --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl '/sites/project-x/lists/Events' --viewTitle 'My Events' --title 'Custom field' --fieldPosition 0
```

Add field with title to view with title of the list with site-relative URL located in a specific site.

```sh
m365 spo list view field add --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl 'Shared Documents' --viewTitle 'All Documents' --fieldTitle 'Custom field'
```

## Response

The command won't return a response on success.
