-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra user recyclebinitem remove

Removes a user from the recycle bin in the current tenant

## Usage

```sh
m365 entra user recyclebinitem remove [options]
```

## Options

```md definition-list
`--id <id>`
: ID of the deleted user.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::info

To use this command you must be a Global administrator, User administrator or Privileged Authentication administrator.

:::

:::note

After running this command, it may take a minute before the deleted user is effectively removed from the tenant.

:::

## Examples

Removes a specific user from the recycle bin.

```sh
m365 entra user recyclebinitem remove --id 59f80e08-24b1-41f8-8586-16765fd830d3
```

Removes a specific user from the recycle bin without confirmation prompt.

```sh
m365 entra user recyclebinitem remove --id 59f80e08-24b1-41f8-8586-16765fd830d3 --force
```

## Response

The command won't return a response on success.
