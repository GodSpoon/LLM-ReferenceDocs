-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo site hubsite theme sync

Applies any theme updates from the hub site to the site it is connected to.

## Usage

```sh
m365 spo site hubsite theme sync [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site to apply theme updates from the hub site to.
```

<Global />

## Examples

Applies any theme updates from the hub site to a specific site

```sh
m365 spo site hubsite theme sync --webUrl https://contoso.sharepoint.com/sites/project-x
```

## Response

The command won't return a response on success.

## More information

- SharePoint hub sites new in Microsoft 365: [https://techcommunity.microsoft.com/t5/SharePoint-Blog/SharePoint-hub-sites-new-in-Office-365/ba-p/109547](https://techcommunity.microsoft.com/t5/SharePoint-Blog/SharePoint-hub-sites-new-in-Office-365/ba-p/109547)
