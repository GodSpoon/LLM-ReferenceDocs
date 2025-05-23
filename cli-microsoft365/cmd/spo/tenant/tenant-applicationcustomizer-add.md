-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo tenant applicationcustomizer add

Add an application customizer as a tenant-wide extension

## Usage

```sh
m365 spo tenant applicationcustomizer add [options]
```

## Options

```md definition-list
`-t, --title <title>`
: The title of the Application Customizer.

`-i, --clientSideComponentId <clientSideComponentId>`
: The Client Side Component Id (GUID) of the application customizer.

`-p, --clientSideComponentProperties [clientSideComponentProperties]`
: The Client Side Component properties of the application customizer.

`-w, --webTemplate [webTemplate]`
: Optionally add a web template (e.g. STS#3, SITEPAGEPUBLISHING#0, etc) as a filter for what kind of sites the application customizer is registered on.
```

<Global />

## Remarks

Running this command from the Windows Command Shell (cmd.exe) or PowerShell for Windows OS XP, 7, 8, 8.1 without bash installed might require additional formatting for command options that have JSON, XML or JavaScript values because the command shell treats quotes differently. For example, this is how ApplicationCustomizer user custom action can be created from the Windows cmd.exe:

```sh
m365 spo tenant applicationcustomizer add --title "YourAppCustomizer" --clientSideComponentId b41916e7-e69d-467f-b37f-ff8ecf8f99f2 --clientSideComponentProperties '{\"testMessage\":\"Test message\"}'
```

Note, how the clientSideComponentProperties option has escaped double quotes `'{\"testMessage\":\"Test message\"}'` compared to execution from bash `'{"testMessage":"Test message"}'`.

:::warning[Escaping JSON in PowerShell]

When using the `--clientSideComponentProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

:::info

To use this command, you need to be a SharePoint Admin.

:::

This command can be used for configuring a tenant-wide application customizer. To configure an application customizer on a specific site, view our dedicated [spo applicationcustomizer add](../applicationcustomizer/applicationcustomizer-add.mdx) command.

## Examples

Adds an application customizer that's deployed tenant wide

```sh
m365 spo tenant applicationcustomizer add --title "Some customizer" --clientSideComponentId  799883f5-7962-4384-a10a-105adaec6ffc 
```

Adds an application customizer that is configured for all communication sites.

```sh
m365 spo tenant applicationcustomizer add --title "Some customizer" --clientSideComponentId  799883f5-7962-4384-a10a-105adaec6ffc --webTemplate "SITEPAGEPUBLISHING#0"
```

## Response

The command won't return a response on success.
