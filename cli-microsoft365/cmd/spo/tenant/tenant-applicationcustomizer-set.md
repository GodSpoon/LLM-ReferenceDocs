-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo tenant applicationcustomizer set

Updates an Application Customizer that is deployed as a tenant-wide extension

## Usage

```sh
m365 spo tenant applicationcustomizer set [options]
```

## Options

```md definition-list
`-t, --title [title]`
: The title of the Application Customizer to update. Specify either `title`, `id` or `clientSideComponentId`.

`-i, --id [id]`
: The id of the Application Customizer to update. Specify either `title`, `id` or `clientSideComponentId`.

`-c, --clientSideComponentId  [clientSideComponentId]`
: The Client Side Component Id (GUID) of the Application Customizer to update. Specify either `title`, `id` or `clientSideComponentId`.

`--newTitle [newTitle]`
: The updated title of the Application Customizer.

`--newClientSideComponentId [newClientSideComponentId]`
: The new Client Side Component Id (GUID) of the Application Customizer.

`-p, --clientSideComponentProperties [clientSideComponentProperties]`
: The Client Side Component properties of the Application Customizer.

`-w, --webTemplate [webTemplate]`
: Optionally add a web template (e.g. STS#3, SITEPAGEPUBLISHING#0, etc) as a filter for what kind of sites the application customizer is registered on.
```

<Global />

## Remarks

Running this command from the Windows Command Shell (cmd.exe) or PowerShell for Windows OS XP, 7, 8, 8.1 without bash installed might require additional formatting for clientSideComponentProperties option that has JSON value because the command shell treats quotes differently. For example, this is how Application Customizer can be updated from the Windows cmd.exe:

```sh
m365 spo tenant applicationcustomizer set --id 3 --clientSideComponentProperties '{\"someProperty\":\"Some value\"}'
```

Note, how the clientSideComponentProperties option (--clientSideComponentProperties) has escaped double quotes `'{\"someProperty\":\"Some value\"}'` compared to execution from bash `'{"someProperty": "Some value"}'`.

:::warning[Escaping JSON in PowerShell]
    
When using the `--clientSideComponentProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

This command can be used for updating an application customizer that's installed tenant-wide. To update an application customizer from a specific site, view our dedicated [spo applicationcustomizer set](../applicationcustomizer/applicationcustomizer-set.mdx) command.

## Examples

Updates the title of an Application Customizer that is deployed as a tenant-wide extension by its id

```sh
m365 spo tenant applicationcustomizer set --id 3 --newTitle "Some customizer" 
```

Updates the Client Side Component Id of an Application Customizer that is deployed as a tenant-wide extension by its id

```sh
m365 spo tenant applicationcustomizer set --id 3 --newClientSideComponentId "b44a5182-9877-4029-baec-0181c70dacbc" 
```

Updates the properties of an Application Customizer that is deployed as a tenant-wide extension by its id

```sh
m365 spo tenant applicationcustomizer set --id 3 --clientSideComponentProperties '{ "someProperty": "Some value" }'
```

Updates the title of an Application Customizer that is deployed as a tenant-wide extension by its title

```sh
m365 spo tenant applicationcustomizer set --title "Some customizer" --newTitle "Updated customizer" 
```

Updates the title of an Application Customizer that is deployed as a tenant-wide extension by its clientSideComponentId

```sh
m365 spo tenant applicationcustomizer set --clientSideComponentId "7f8fd1f2-9d26-4a4a-a607-bf4622d7ec11" --newTitle "Some customizer" 
```

## Response

The command won't return a response on success.
