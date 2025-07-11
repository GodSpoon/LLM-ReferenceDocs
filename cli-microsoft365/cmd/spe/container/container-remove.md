-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spe container remove

Removes a container

## Usage

```sh
m365 spe container remove [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the container instance. Specify either `id` or `name` but not both.

`-n, --name [name]`
: The name of the container instance. Specify either `id` or `name` but not both.

`--containerTypeId [containerTypeId]`
: The ID of the container type. Specify either `containerTypeId` or `containerTypeName` when using `name` but not both.

`--containerTypeName [containerTypeName]`
: The name of the container type. Specify either `containerTypeId` or `containerTypeName` when using `name` but not both.

`--recycle`
: Recycle the container instance instead of permanently deleting it.

`-f, --force`
: Do not prompt for confirmation.
```

<Global />

## Examples

Remove a container by ID.

```sh
m365 spe container remove --id "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER"
```

Move a container specified by ID to the recycle bin.

```sh
m365 spe container remove --id "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER" --recycle
```

Remove a container by name specifying the container type id.

```sh
m365 spe container remove --name "My Application Storage Container" --containerTypeId d248c449-da7e-4119-b5f6-7bb0865a42f9
```

Remove a container by name specifying the container type name.

```sh
m365 spe container remove --name "My Application Storage Container" --containerTypeName "My Application Container Type"
```

## Response

The command won't return a response on success.
