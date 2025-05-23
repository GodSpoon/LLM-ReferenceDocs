-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo web roleinheritance reset

Restores role inheritance of subsite.

## Usage

```sh
m365 spo web roleinheritance reset [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site

`-f, --force`
: Do not prompt for confirmation before resetting role inheritance.
```

<Global />

## Examples

Restore role inheritance of subsite _https://contoso.sharepoint.com/sites/project-x_

```sh
m365 spo web roleinheritance reset --webUrl https://contoso.sharepoint.com/sites/project-x
```

Restore role inheritance of subsite _https://contoso.sharepoint.com/sites/project-x_ without prompting for confirmation

```sh
m365 spo web roleinheritance reset --webUrl https://contoso.sharepoint.com/sites/project-x --force
```

## Response

The command won't return a response on success.
