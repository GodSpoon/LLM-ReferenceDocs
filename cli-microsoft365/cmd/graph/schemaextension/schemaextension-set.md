-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# graph schemaextension set

Updates a Microsoft Graph schema extension

## Usage

```sh
m365 graph schemaextension set [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The unique identifier for the schema extension definition

`--owner <owner>`
: The ID of the Microsoft Entra application that is the owner of the schema extension

`-d, --description [description]`
: Description of the schema extension

`-s, --status [status]`
: The lifecycle state of the schema extension. Accepted values are `Available` or `Deprecated`

`-t, --targetTypes [targetTypes]`
: Comma-separated list of Microsoft Graph resource types the schema extension targets

`-p, --properties [properties]`
: The collection of property names and types that make up the schema extension definition formatted as a JSON string
```

<Global />

## Remarks

The lifecycle state of the schema extension. The initial state upon creation is `InDevelopment`.
Possible states transitions are from `InDevelopment` to `Available` and `Available` to `Deprecated`.
The target types are the set of Microsoft Graph resource types (that support schema extensions) that this schema extension definition can be applied to. This option is specified as a comma-separated list.

:::warning[Escaping JSON in PowerShell]

When using the `--properties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

## Examples

 Update the description of a schema extension

```sh
m365 graph schemaextension set --id MySchemaExtension --owner 62375ab9-6b52-47ed-826b-58e47e0e304b --description "My schema extension" 
```

Update the target types and properties of a schema extension

```sh
m365 graph schemaextension set --id contoso_MySchemaExtension --owner 62375ab9-6b52-47ed-826b-58e47e0e304b --targetTypes "Group,User" --properties '[{"name":"myProp1","type":"Integer"},{"name":"myProp2","type":"String"}]'
```

Change the status of a schema extension to 'Available'

```sh
m365 graph schemaextension set --id contoso_MySchemaExtension --owner 62375ab9-6b52-47ed-826b-58e47e0e304b --status Available
```

## Response

The command won't return a response on success.
