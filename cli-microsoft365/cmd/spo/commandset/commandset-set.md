-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo commandset set

Updates a ListView Command Set on a site

## Usage

```sh
m365 spo commandset set [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The site to update the ListView Command Set on.

`-t, --title [title]`
: The title of the ListView Command Set to update. Specify either `title`, `id`or `clientSideComponentId`.

`-i, --id [id]`
: The id of the ListView Command Set to update. Specify either `title`, `id`or `clientSideComponentId`.

`-c, --clientSideComponentId [clientSideComponentId]`
: The Client Side Component Id (GUID) of the ListView Command Set to update. Specify either `title`, `id`or `clientSideComponentId`.

`--newClientSideComponentId [newClientSideComponentId]`
: The new Client Side Component Id (GUID) of the ListView Command Set.

`--newTitle [newTitle]`
: The new title of the ListView Command Set.

`-l, --listType [listType]`
: The list or library type to register the Command Set on. Allowed values are: `List`, `Library` or `SitePages`.

`--clientSideComponentProperties [clientSideComponentProperties]`
: The Client Side Component properties of the ListView Command Set.

`-s, --scope [scope]`
: The scope where to lookup the ListView Command Set: at site level or web level. Allowed values are: `Site`, `Web`, `All`. Defaults to `All`.

`--location [location]`
: The location of the ListView Command Set. Allowed values are: `ContextMenu`, `CommandBar` or `Both`.
```

<Global />

## Remarks

Running this command from the Windows Command Shell (cmd.exe) or PowerShell for Windows OS XP, 7, 8, 8.1 without bash installed might require additional formatting for command options that have JSON, XML or JavaScript values because the command shell treats quotes differently. For example, this is how a ListView Command Set can be created from the Windows cmd.exe:

```sh
m365 spo commandset set --webUrl https://contoso.sharepoint.com/sites/test --title "CLI Commandset" --location "Both" --listType "List" --clientSideComponentProperties '{\"testMessage\":\"Test message\"}'
```

Note, how the clientSideComponentProperties option has escaped double quotes `'{\"testMessage\":\"Test message\"}'` compared to execution from bash `'{"testMessage":"Test message"}'`.

:::warning[Escaping JSON in PowerShell]

When using the `--clientSideComponentProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

This command can be used for updating a ListView Command Set on a specific site. To update a ListView Command Set that's installed tenant-wide, view our dedicated [spo tenant commandset set](../tenant/tenant-commandset-set.mdx) command.

## Examples

Updates the title and location of a ListView Command Set on the sales site.

```sh
m365 spo commandset set --clientSideComponentId 799883f5-7962-4384-a10a-105adaec6ffc --newTitle "Some new title" --location Both --webUrl https://contoso.sharepoint.com/sites/sales --scope Site
```

Updates a ListView Command Set on the sales site with some properties.

```sh
m365 spo commandset set --title "Some customizer" --clientSideComponentProperties '{ "someProperty": "Some value" }' --webUrl https://contoso.sharepoint.com/sites/sales --scope Site
```

Updates the Client Side Component Id of a ListView Command Set.

```sh
m365 spo commandset set --title "Some customizer" --newClientSideComponentId b2c5faf3-638f-44ae-bfde-1730d94283bf --webUrl https://contoso.sharepoint.com/sites/sales
```

## Response

The command won't return a response on success.
