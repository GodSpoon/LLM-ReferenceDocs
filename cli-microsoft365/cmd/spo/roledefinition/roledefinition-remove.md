-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo roledefinition remove

Removes the role definition from the specified site

## Usage

```sh
m365 spo roledefinition remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site from which role should be removed.

`-i, --id <id>`
: ID of the role definition to remove.

`-f, --force`
: Don't prompt for confirming removing the role definition.
```

<Global />

## Examples

Remove the role definition from the given site

```sh
m365 spo roledefinition remove --webUrl https://contoso.sharepoint.com/sites/project-x --id 1
```

Remove the role definition from the given site and don't prompt for confirmation

```sh
m365 spo roledefinition remove --webUrl https://contoso.sharepoint.com/sites/project-x --id 1 --force
```

## Response

The command won't return a response on success.
