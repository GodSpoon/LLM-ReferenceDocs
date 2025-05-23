-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo listitem roleinheritance reset

Restores the role inheritance of list item, file, or folder

## Usage

```sh
m365 spo listitem roleinheritance reset [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the item for which to reset role inheritance is located

`--listItemId <listItemId>`
: ID of the item for which to reset role inheritance

`--listId [listId]`
: ID of the list. Specify either `listTitle`, `listId` or `listUrl`

`--listTitle [listTitle]`
: Title of the list. Specify either `listTitle`, `listId` or `listUrl`

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listTitle`, `listId` or `listUrl`

`-f, --force`
: Do not prompt for confirmation before resetting role inheritance.
```

<Global />

## Examples

Restore role inheritance of list item with id 8 from list with ID _0cd891ef-afce-4e55-b836-fce03286cccf_ located in site _https://contoso.sharepoint.com/sites/project-x_

```sh
m365 spo listitem roleinheritance reset --webUrl https://contoso.sharepoint.com/sites/project-x --listItemId 8 --listId 0cd891ef-afce-4e55-b836-fce03286cccf
```

Restore role inheritance of list item with id 8 from list with title _test_ located in site _https://contoso.sharepoint.com/sites/project-x_

```sh
m365 spo listitem roleinheritance reset --webUrl https://contoso.sharepoint.com/sites/project-x --listItemId 8 --listTitle test
```

Restore role inheritance of a list item with a specific id in a list retrieved by server relative URL located in a specific site without prompting for confirmation

```sh
m365 spo listitem roleinheritance reset --webUrl https://contoso.sharepoint.com/sites/project-x --listItemId 8 --listUrl /sites/project-x/lists/test --force
```

## Response

The command won't return a response on success.
