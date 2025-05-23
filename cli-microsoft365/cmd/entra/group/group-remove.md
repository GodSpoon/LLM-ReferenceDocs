-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra group remove

Removes an Entra group

## Usage

```sh
m365 entra group remove [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the Entra group. Specify either `id` or `displayName` but not both.

`-n, --displayName [displayName]`
: The display name of the Entra group. Specify either `id` or `displayName` but not both.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Remove an Entra group by display name

```sh
m365 entra group remove --displayName Developers
```

Remove an Entra group by ID

```sh
m365 entra group remove --id 016bf125-195b-43c5-a1a0-28ccd3192c6d
```

## Response

The command won't return a response on success.
