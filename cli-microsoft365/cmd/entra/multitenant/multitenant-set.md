-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra multitenant set

Updates the properties of a multitenant organization

## Usage

```sh
m365 entra multitenant set [options]
```

## Options

```md definition-list
`-n, --displayName [displayName]`
: New display name of the multitenant organization. Both options, `displayName` and `description` are optional but at least must be specified.

`-d, --description [description]`
: New description of the multitenant organization. Both options, `displayName` and `description` are optional but at least must be specified.
```

<Global />

## Remarks

:::info

To use this command you must be at least **Security Administrator**.

:::

## Examples

Update display name of multitenant organization.

```sh
m365 entra multitenant set --displayName 'Fabrikam organization'
```

Update display name and description of multitenant organization.

```sh
m365 entra multitenant set --displayName 'Fabrikam organization' --description 'Multitenant organization between Fabrikam and Contoso'
```

## Response

The command won't return a response on success

## More information

- Multitenant organization: https://learn.microsoft.com/entra/identity/multi-tenant-organizations/overview
