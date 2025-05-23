-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo listitem roleinheritance break

Break inheritance of list item.

## Usage

```sh
m365 spo listitem roleinheritance break [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the item for which to break role inheritance is located

`--listItemId <listItemId>`
: ID of the item for which to break role inheritance

`-l, --listId [listId]`
: ID of the list. Specify either `listTitle`, `listId` or `listUrl`

`-t, --listTitle [listTitle]`
: Title of the list.  Specify either `listTitle`, `listId` or `listUrl`

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listTitle`, `listId` or `listUrl`

`-c, --clearExistingPermissions`
: Set to clear existing roles from the list item

`-f, --force`
: Do not prompt for confirmation before breaking role inheritance.
```

<Global />

## Remarks

By default, when breaking permissions inheritance, the list item will retain existing permissions. To remove existing permissions, use the `--clearExistingPermissions` option.

## Examples

Break inheritance of list item _1_ in list _someList_ located in site _https://contoso.sharepoint.com/sites/project-x_

```sh
m365 spo listitem roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "_someList_" --listItemId 1
```

Break inheritance of list item _1_ in list with ID _202b8199-b9de-43fd-9737-7f213f51c991_ located in site _https://contoso.sharepoint.com/sites/project-x_

```sh
m365 spo listitem roleinheritance break --webUrl https://contoso.sharepoint.com/sites/project-x --listId 202b8199-b9de-43fd-9737-7f213f51c991 --listItemId 1
```

Break inheritance of list item _1_ in list _someList_ located in site _https://contoso.sharepoint.com/sites/project-x_ with clearing permissions

```sh
m365 spo listitem roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "_someList_" --listItemId 1 --clearExistingPermissions
```

Break inheritance of a specific list item in a list retrieved by server-relative URL in a specific site and clear the existing permissions

```sh
m365 spo listitem roleinheritance break --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl /sites/project-x/Documents --listItemId 1 --clearExistingPermissions
```

Break inheritance of list item _1_ in list with ID _202b8199-b9de-43fd-9737-7f213f51c991_ located in site _https://contoso.sharepoint.com/sites/project-x_ with clearing permissions without prompting for confirmation

```sh
m365 spo listitem roleinheritance break --webUrl https://contoso.sharepoint.com/sites/project-x --listId 202b8199-b9de-43fd-9737-7f213f51c991 --listItemId 1 --clearExistingPermissions --force
```

## Response

The command won't return a response on success.
