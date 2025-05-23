-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra administrativeunit remove

Removes an administrative unit

## Usage

```sh
m365 entra administrativeunit remove [options]
```

## options

```md definition-list
`-i, --id [id]`
: The id of the administrative unit. Specify either `id` or `displayName` but not both.

`-n, --displayName [displayName]`
: The display name of the administrative unit. Specify either `id` or `displayName` but not both.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::info

To use this command you must be either **Global Administrator** or **Privileged Role Administrator**.

:::

## Examples

Remove an administrative unit by its id

```sh
m365 entra administrativeunit remove --id 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7
```

Remove an administrative unit by it displayName

```sh
m365 entra administrativeunit remove --displayName 'Marketing Division'
```

## Response

The command won't return a response on success

## More information

- Administrative units: https://learn.microsoft.com/entra/identity/role-based-access-control/administrative-units
