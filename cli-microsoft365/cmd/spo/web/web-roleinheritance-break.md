-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo web roleinheritance break

Break role inheritance of subsite

## Usage

```sh
m365 spo web roleinheritance break [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site.

`-c, --clearExistingPermissions`
: Clears all existing permissions from the web.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

By default, when breaking permissions inheritance, the web will retain existing permissions. To remove existing permissions, use the `--clearExistingPermissions` option.

## Examples

Break role inheritance of a web and keep the existing permissions

```sh
m365 spo web roleinheritance break --webUrl https://contoso.sharepoint.com/sites/project-x
```

Break role inheritance of a web and clear the existing permissions

```sh
m365 spo web roleinheritance break --webUrl https://contoso.sharepoint.com/sites/project-x --clearExistingPermissions
```

## Response

The command won't return a response on success.
