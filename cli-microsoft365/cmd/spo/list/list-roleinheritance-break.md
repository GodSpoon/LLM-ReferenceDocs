-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo list roleinheritance break

Breaks role inheritance on list or library

## Usage

```sh
m365 spo list roleinheritance break [options]
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

`-c, --clearExistingPermissions`
: Flag if used clears all roles from the list.

`-f, --force`
: Do not prompt for confirmation before breaking role inheritance.
```

<Global />

## Remarks

By default, when breaking permissions inheritance, the list will retain existing permissions. To remove existing permissions, use the `--clearExistingPermissions` option.

## Examples

Break inheritance of list by title in a specific site.

```sh
m365 spo list roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList"
```

Break inheritance of list by id in a specific site.

```sh
m365 spo list roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --listId "202b8199-b9de-43fd-9737-7f213f51c991"
```

Break inheritance of list by title located in a specific site and clearing the existing permissions.

```sh
m365 spo list roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList" --clearExistingPermissions
```

Break inheritance of list by url in a specific site and clearing the existing permissions.

```sh
m365 spo list roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --listUrl '/sites/project-x/lists/events' --clearExistingPermissions
```

Break inheritance of list by ID located in in a specific site with clearing permissions without prompting for confirmation.

```sh
m365 spo list roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --listId "202b8199-b9de-43fd-9737-7f213f51c991" --clearExistingPermissions --force
```

## Response

The command won't return a response on success.
