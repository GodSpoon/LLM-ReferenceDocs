-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo list roleinheritance reset

Restores role inheritance on list or library

## Usage

```sh
m365 spo list roleinheritance reset [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list is located.

`-i, --listId [listId]`
: ID of the list. Specify either `listTitle`, `listId`, or `listUrl`.

`-t, --listTitle [listTitle]`
: Title of the list. Specify either `listTitle`, `listId`, or `listUrl`.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listTitle`, `listId`, or `listUrl`.

`-f, --force`
: Do not prompt for confirmation before resetting role inheritance.
```

<Global />

## Examples

Restores role inheritance of a specific list by id in a specific site.

```sh
m365 spo list roleinheritance reset --webUrl https://contoso.sharepoint.com/sites/project-x --listId 0cd891ef-afce-4e55-b836-fce03286cccf
```

Restores role inheritance of a specific list by title in a specific site.

```sh
m365 spo list roleinheritance reset --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle test
```

Restores role inheritance of a specific list by url in a specific site.

```sh
m365 spo list roleinheritance reset --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl '/sites/project-x/lists/events'
```

Restores role inheritance of list a specific list by title without prompting for confirmation.

```sh
m365 spo list roleinheritance reset --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle test --force
```

## Response

The command won't return a response on success.
