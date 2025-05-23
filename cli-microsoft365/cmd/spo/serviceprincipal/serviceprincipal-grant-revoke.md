-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo serviceprincipal grant revoke

Revokes the specified set of permissions granted to the service principal

## Usage

```sh
m365 spo serviceprincipal grant revoke [options]
```

## Alias

```sh
m365 spo sp grant revoke
```

## Options

```md definition-list
`-i, --id <id>`
: `ObjectId` of the permission grant to revoke.

`-s, --scope [scope]`
: Scope to revoke. If not specified, will revoke all permissions.
```

<Global />

## Remarks

:::info

To use this command you must be a Global administrator.

:::

The permission grant you want to revoke is denoted using its `ObjectId`. You can retrieve it using the [spo serviceprincipal grant list](./serviceprincipal-grant-list.mdx) command.

## Examples

Revoke permission grant with all permissions

```sh
m365 spo serviceprincipal grant revoke --id EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

Revoke a specific permission

```sh
m365 spo serviceprincipal grant revoke --id EXAMPLE_SECRET_VALUE_PLACEHOLDER --scope "Mail.Read"
```

## Response

The command won't return a response on success.
