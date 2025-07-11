-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# graph openextension set

Updates an open extension for a resource

## Usage

```sh
m365 graph openextension set [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The name of the open extension.

`-i, --resourceId <resourceId>`
: The Id of the resource for which to update the open extension.

`-t, --resourceType <resourceType>`
: The type of resource. Allowed values are `user`, `group`, `device`, `organization`.

`-k, --keepUnchangedProperties`
: Keeps unspecified properties. Without this flag, any property that is not updated will be removed from the extension.
```

<Global />

## Remarks

This command allows using unknown options to update custom data of the open extension.

When updating an open extension to a user, it's possible to use the UPN as the resourceId.

:::warning[Escaping JSON in PowerShell]

When updating open extensions it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

:::info

If a property of the open extension is not specified, the property is removed from the open extension.

If a property of the open extension is not specified and `keepUnchangedProperties` is specified, the property will be kept in the open extension.

:::

## Examples

Updates an open extension for a user specified by id

```sh
m365 graph openextension set --userId eb77fbcf-6fe8-458b-985d-1747284793bc --name 'com.contoso.roamingSettings' --resourceType user --theme dark --color red --language English
```

Updates an open extension for a user specified by UPN

```sh
m365 graph openextension set --userName john.doe@contoso.com --name 'com.contoso.roamingSettings' --resourceType user --theme dark --color red --language English
```

Updates an open extension for a group specified by id, one of the property represents a JSON object

```sh
m365 graph openextension set --resourceId c956e711-f074-40c3-8431-fbd69bb67d9c --name 'com.contoso.roamingSettings' --resourceType group --settings '{"theme": "dark", "color": "red" }'
```

Updates an open extension, but keeps the properties that are not specified

```sh
m365 graph openextension set --userId eb77fbcf-6fe8-458b-985d-1747284793bc --name 'com.contoso.roamingSettings' --resourceType user --color red --keepUnchangedProperties
```

Updates an open extension, but removes the properties that are not specified

```sh
m365 graph openextension set --userId eb77fbcf-6fe8-458b-985d-1747284793bc --name 'com.contoso.roamingSettings' --resourceType user --color red
```

Clears the value of the property

```sh
m365 graph openextension set --userId eb77fbcf-6fe8-458b-985d-1747284793bc --name 'com.contoso.roamingSettings' --resourceType user --theme ""
```

## Response

The command won't return a response on success.

## More information

- Open extensions: https://learn.microsoft.com/graph/extensibility-overview?tabs=http#open-extensions
