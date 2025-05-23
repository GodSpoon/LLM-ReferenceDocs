-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo set

Sets the URL of the root SharePoint site collection for use in SPO commands

## Usage

```sh
m365 spo set [options]
```

## Options

```md definition-list
`-u, --url <url>`
: The URL of the root SharePoint site collection to use in SPO commands
```

<Global />

## Remarks

CLI for Microsoft 365 automatically discovers the URL of the root SharePoint site collection/SharePoint tenant admin site (whichever is needed to run the particular command). In specific cases, like when managing multi-geo Microsoft 365 tenants, it could be desirable to make the CLI manage the specific geography. For such cases, you can use this command to explicitly specify the SPO URL that should be used when executing SPO commands.

## Examples

Set SPO URL to the specified URL

```sh
m365 spo set --url https://contoso.sharepoint.com
```

## Response

The command won't return a response on success.
