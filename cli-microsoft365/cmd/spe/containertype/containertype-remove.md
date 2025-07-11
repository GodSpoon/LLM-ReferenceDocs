-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spe containertype remove

Remove a specific container type

## Usage

```sh
m365 spe containertype remove [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the container type. Specify either `id` or `name` but not both.

`-n, --name [name]`
: The container type name. Specify either `id` or `name` but not both.

`-f, --force`
: Force removal of the container type without confirmation.
```

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Removes a container type by ID

```sh
m365 spe containertype remove --id 4ec4aefd-4fa3-0e4a-20c3-6e68389e7138
```

Removes a container type by name

```sh
m365 spe containertype remove --name 'My container type'
```

## Response

The command won't return a response on success.
