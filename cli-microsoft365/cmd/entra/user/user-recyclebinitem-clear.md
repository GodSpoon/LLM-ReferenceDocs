-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra user recyclebinitem clear

Removes all users from the tenant recycle bin

## Usage

```sh
m365 entra user recyclebinitem clear [options]
```

## Options

```md definition-list
`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::info

To use this command you must be a Global administrator, User administrator or Privileged Authentication administrator.

:::

:::note

After running this command, it may take a minute before all deleted users are effectively removed from the tenant.

:::

## Examples

Removes all users from the tenant recycle bin.

```sh
m365 entra user recyclebinitem clear
```

Removes all users from the tenant recycle bin without confirmation prompt.

```sh
m365 entra user recyclebinitem clear --force
```

## Response

The command won't return a response on success.
