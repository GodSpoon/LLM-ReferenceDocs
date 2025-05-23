-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra multitenant remove

Removes a multitenant organization

## Usage

```sh
m365 entra multitenant remove [options]
```

## options

```md definition-list
`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::info

To use this command you must be at least **Security Administrator**.

:::

:::info

When removing a Multi-Tenant Organization, all associations with other tenants will be removed too.

The removing process can take up to 2 hours to complete.

:::

## Examples

Remove the multitenant organization.

```sh
m365 entra multitenant remove
```

Remove the multitenant organization without prompting for confirmation.

```sh
m365 entra multitenant remove --force
```

## Response

The command won't return a response on success

## More information

- Multitenant organization: https://learn.microsoft.com/entra/identity/multi-tenant-organizations/overview
