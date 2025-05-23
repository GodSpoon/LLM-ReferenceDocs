-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo tenant commandset set

Updates a ListView Command Set that is installed tenant-wide

## Usage

```sh
m365 spo tenant commandset set [options]
```

## Options

```md definition-list
`-t, --title [title]`
: The title of the ListView Command Set to update. Specify either `title`, `id` or `clientSideComponentId`.

`-i, --id [id]`
: The id of the ListView Command Set to update. Specify either `title`, `id` or `clientSideComponentId`.

`-c, --clientSideComponentId  [clientSideComponentId]`
: The Client Side Component Id (GUID) of the ListView Command Set to update. Specify either `title`, `id` or `clientSideComponentId`.

`--newTitle [newTitle]`
: The updated title of the ListView Command Set.

`-l, --listType [listType]`
: The list or library type to register the ListView Command Set on. Allowed values `List` or `Library`.

`--newClientSideComponentId  [newClientSideComponentId]`
: The updated Client Side Component Id (GUID) of the ListView Command Set.

`-p, --clientSideComponentProperties [clientSideComponentProperties]`
: The Client Side Component properties of the ListView Command Set.

`-w, --webTemplate [webTemplate]`
: Optionally add a web template (e.g. STS#3, SITEPAGEPUBLISHING#0, etc) as a filter for what kind of sites the ListView Command Set is registered on.

`--location [location]`
: The location of the ListView Command Set. Allowed values `ContextMenu`, `CommandBar` or `Both`. Defaults to `CommandBar`.
```

<Global />

## Remarks

:::warning[Escaping JSON in PowerShell]

When using the `--clientSideComponentProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

This command can be used for updating a ListView Command Set that's installed tenant-wide. To update a ListView Command Set on a specific site, view our dedicated [spo commandset set](../commandset/commandset-set.mdx) command.

## Examples

Updates the title of a ListView Command Set that's deployed tenant wide by its id.

```sh
m365 spo tenant commandset set --id 4 --newTitle "Some customizer"
```

Updates the properties of a ListView Command Set that's deployed tenant wide by its title.

```sh
m365 spo tenant commandset set --title "Some Command Set" --clientSideComponentProperties '{ "someProperty": "Some value" }'
```

Updates the Client Side Component Id (GUID) of a ListView Command Set that's deployed tenant wide by its clientSideComponentId.

```sh
m365 spo tenant commandset set --clientSideComponentId "07ee7d3d-923e-49be-b050-86f53edb45fb" --newClientSideComponentId "b44a5182-9877-4029-baec-0181c70dacbc"
```

## Response

The command won't return a response on success.
