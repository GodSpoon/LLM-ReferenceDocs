-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo page publish

Publishes a modern page

## Usage

```sh
m365 spo page publish [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the page is located.

`-n, --name <name>`
: Name of the page.
```

<Global />

## Examples

Publish a modern page

```sh
m365 spo page publish --webUrl https://contoso.sharepoint.com/sites/Marketing --name "Style guide.aspx"
```

Publish a modern page in a subfolder

```sh
m365 spo page publish --webUrl https://contoso.sharepoint.com/sites/Marketing --name "/Styles/Guide.aspx"
```

## Response

The command won't return a response on success.
