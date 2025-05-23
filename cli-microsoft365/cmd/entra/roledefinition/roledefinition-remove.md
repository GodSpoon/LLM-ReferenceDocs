-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra roledefinition remove

Removes a custom Microsoft Entra role definition

## Usage

```sh
m365 entra roledefinition remove [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The id of the role definition. Specify either `id` or `displayName`, but not both.

`-n, --displayName [displayName]`
: The name of the role definition. Specify either `id` or `displayName`, but not both.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::info

When the role definition is removed, all the associated role assignments are deleted.

:::

## Examples

Remove a role definition specified by id without prompting

```sh
m365 entra roledefinition remove --id 0bed8b86-5026-4a93-ac7d-56750cc099f1 --force
```

Remove a role definition specified by name and prompt for confirmation

```sh
m365 entra roledefinition remove --displayName 'Custom Role'
```

## Response

The command won't return a response on success
