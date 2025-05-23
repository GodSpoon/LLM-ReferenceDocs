-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo navigation node remove

Removes the specified navigation node

## Usage

```sh
m365 spo navigation node remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Absolute URL of the site to which navigation should be modified

`-l, --location <location>`
: Navigation type where the node should be removed. Available options: `QuickLaunch,TopNavigationBar`

`-i, --id <id>`
: ID of the node to remove

`-f, --force`
: Don't prompt for confirming removing the node
```

<Global />

## Examples

Remove a node from the top navigation. Will prompt for confirmation

```sh
m365 spo navigation node remove --webUrl https://contoso.sharepoint.com/sites/team-a --location TopNavigationBar --id 2003
```

Remove a node from the quick launch without prompting for confirmation

```sh
m365 spo navigation node remove --webUrl https://contoso.sharepoint.com/sites/team-a --location QuickLaunch --id 2003 --force
```

## Response

The command won't return a response on success.
