-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo list remove

Removes the specified list

## Usage

```sh
m365 spo list remove [options]
```
 
## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list to remove is located.

`-i, --id [id]`
: The ID of the list to remove. Specify either `id` or `title` but not both.

`-t, --title [title]`
: Title of the list to remove. Specify either `id` or `title` but not both.

`--recycle`
: Instead of permanently deleting, send the list to the recycle bin.

`-f, --force`
: Don't prompt for confirming removing the list.
```

<Global />

## Examples

Remove the list with a specific ID located in a specific site

```sh
m365 spo list remove --webUrl https://contoso.sharepoint.com/sites/project-x --id 0cd891ef-afce-4e55-b836-fce03286cccf
```

Remove the list with a specific title located in a specific site.

```sh
m365 spo list remove --webUrl https://contoso.sharepoint.com/sites/project-x --title 'List 1'
```

Remove a list specified by id by sending it to the recycle bin instead of permanently removing it

```sh
m365 spo list remove --webUrl https://contoso.sharepoint.com/sites/project-x --id 0cd891ef-afce-4e55-b836-fce03286cccf --recycle
```

## Response

The command won't return a response on success.
