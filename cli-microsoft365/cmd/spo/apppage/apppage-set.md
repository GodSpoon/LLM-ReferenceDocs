-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo apppage set

Updates the single-part app page

## Usage

```sh
m365 spo apppage set [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the page to update is located.

`-n, --name <name>`
: The name of the page to be updated, eg. page.aspx.

`-d, --webPartData <webPartData>`
: JSON string of the web part to update on the page.
```

<Global />

## Examples

Updates the single-part app page located in a specified site. Web part data is stored in the `$webPartData` variable.

```sh
m365 spo apppage set --webUrl "https://contoso.sharepoint.com" --name "Contoso.aspx" --webPartData $webPartData
```

## Response

The command won't return a response on success.
