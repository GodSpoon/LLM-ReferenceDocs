-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# external connection remove

Allow the administrator to remove a specific external connection

## Usage

```sh
m365 external connection remove [options]
```

## Alias

```sh
m365 search externalconnection remove
```

## Options

```md definition-list
`-i, --id [id]`
: ID of the External Connection to remove. Specify either `id` or `name`.

`-n, --name [name]`
: Name of the External Connection to remove. Specify either `id` or `name`.

`-f, --force`
: Don't prompt for confirming removing the connection.
```

<Global />

## Remarks

If the command finds multiple external connections with the specified name, it will prompt you to disambiguate which external connection it should remove, listing the discovered IDs.

## Examples

Removes external connection by its id.

```sh
m365 external connection remove --id "MyApp"
```

Removes external connection by its name. Will NOT prompt for confirmation before removing.

```sh
m365 external connection remove --name "Test" --force
```

## Response

The command won't return a response on success.
