-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo web remove

Delete specified subsite

## Usage

```sh
m365 spo web remove [options]
```

## Options

```md definition-list
`-u, --url <url>`
: URL of the subsite to remove

`-f, --force`
: Do not prompt for confirmation before deleting the subsite
```

<Global />

## Examples

Delete subsite without prompting for confirmation

```sh
m365 spo web remove --url https://contoso.sharepoint.com/subsite --force
```

## Response

The command won't return a response on success.
