-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo list view remove

Deletes the specified view from the list

## Usage

```sh
m365 spo list view remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list to remove the view from is located

`--listId [listId]`
: ID of the list from which the view should be removed. Specify either `listId`, `listTitle`, or `listUrl`.

`--listTitle [listTitle]`
: Title of the list from which the view should be removed. Specify either `listId`, `listTitle`, or `listUrl`.

 `--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listId` , `listTitle` or `listUrl`.

`--id [id]`
: ID of the view to remove. Specify either `id` or `title` but not both

`--title [title]`
: Title of the view to remove. Specify either `id` or `title` but not both

`-f, --force`
: Don't prompt for confirming removing the view
```

<Global />

## Examples

Remove view from the list by ID _0cd891ef-afce-4e55-b836-fce03286cccf_ located in site _https://contoso.sharepoint.com/sites/project-x_

```sh
m365 spo list view remove --webUrl https://contoso.sharepoint.com/sites/project-x --listId 0cd891ef-afce-4e55-b836-fce03286cccf --id cc27a922-8224-4296-90a5-ebbc54da2e81
```

Remove view with ID _cc27a922-8224-4296-90a5-ebbc54da2e81_ from the list with title _Documents_ located in site _https://contoso.sharepoint.com/sites/project-x_

```sh
m365 spo list view remove --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle Documents --id cc27a922-8224-4296-90a5-ebbc54da2e81
```

Remove view with title _MyView_ from a list with title _Documents_ located in site _https://contoso.sharepoint.com/sites/project-x_

```sh
m365 spo list view remove --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle Documents --title MyView
```

Remove view with title _MyView_ from a list with url _/sites/project-x/lists/Events_ located in site _https://contoso.sharepoint.com/sites/project-x_

```sh
m365 spo list view remove --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl '/sites/project-x/lists/Events' --title MyView
```

Remove view with ID _cc27a922-8224-4296-90a5-ebbc54da2e81_ from a list with title _Documents_ located in site _https://contoso.sharepoint.com/sites/project-x_ without being asked for confirmation

```sh
m365 spo list view remove --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle Documents --id cc27a922-8224-4296-90a5-ebbc54da2e81 --force
```

## Response

The command won't return a response on success.
