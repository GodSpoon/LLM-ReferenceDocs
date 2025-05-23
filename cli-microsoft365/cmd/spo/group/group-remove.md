-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo group remove

Removes group from specific web

## Usage

```sh
m365 spo group remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Url of the web to remove the group from.

`--id [id]`
: ID of the group to remove. Use ID or name but not both.

`--name [name]`
: Name of the group to remove. Use ID or name but not both.

`-f, --force`
: Confirm removal of the group.
```

<Global />

## Examples

Removes group with id from the specified web.

```sh
m365 spo group remove --webUrl https://contoso.sharepoint.com/sites/mysite --id 5
```

Removes group with name from the specified web.

```sh
m365 spo group remove --webUrl https://contoso.sharepoint.com/sites/mysite --name "Team Site Owners"
```

## Response

The command won't return a response on success.
