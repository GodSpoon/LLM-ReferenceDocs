-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo applicationcustomizer add

Add an application customizer to a site

## Usage

```sh
m365 spo applicationcustomizer add [options]
```

## Options

```md definition-list
`-t, --title <title>`
: The title of the application customizer.

`-u, --webUrl <webUrl>`
: URL of the site.

`-i, --clientSideComponentId <clientSideComponentId>`
: Client-side component ID of the application customizer (GUID).

`--clientSideComponentProperties [clientSideComponentProperties]`
: JSON string with application customizer properties.

`-s, --scope [scope]`
: Scope of the application customizer. Allowed values: `Site`, `Web`. Defaults to `Site`.
```

<Global />

## Remarks

Running this command from the Windows Command Shell (cmd.exe) or PowerShell for Windows OS XP, 7, 8, 8.1 without bash installed might require additional formatting for command options that have JSON, XML or JavaScript values because the command shell treats quotes differently. For example, this is how an application customizer can be created from the Windows cmd.exe:

```sh
m365 spo applicationcustomizer add --webUrl https://contoso.sharepoint.com/sites/test --title "YourAppCustomizer" --clientSideComponentId b41916e7-e69d-467f-b37f-ff8ecf8f99f2 --clientSideComponentProperties '{\"testMessage\":\"Test message\"}'
```

Note, how the clientSideComponentProperties option has escaped double quotes `'{\"testMessage\":\"Test message\"}'` compared to execution from bash `'{"testMessage":"Test message"}'`.

:::warning[Escaping JSON in PowerShell]

When using the `--clientSideComponentProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

This command can be used for configuring an application customizer on a specific site. To configure an application customizer tenant-wide, view our dedicated [spo tenant applicationcustomizer add](../tenant/tenant-applicationcustomizer-add.mdx) command.

## Examples

Adds an application customizer to the sales site.

```sh
m365 spo applicationcustomizer add --title 'Some customizer' --clientSideComponentId 799883f5-7962-4384-a10a-105adaec6ffc --webUrl https://contoso.sharepoint.com/sites/sales
```

Adds an application customizer to the sales site with some properties.

```sh
m365 spo applicationcustomizer add --title 'Some customizer' --clientSideComponentId 799883f5-7962-4384-a10a-105adaec6ffc --clientSideComponentProperties '{ "someProperty": "Some value" }' --webUrl https://contoso.sharepoint.com/sites/sales --scope 'Site'
```

## Response

The command won't return a response on success.
