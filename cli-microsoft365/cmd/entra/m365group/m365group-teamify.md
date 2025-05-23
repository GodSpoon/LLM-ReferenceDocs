-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra m365group teamify

Creates a new Microsoft Teams team under existing Microsoft 365 group

## Usage

```sh
m365 entra m365group teamify [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the Microsoft 365 Group to connect to Microsoft Teams. Specify either `id`, `displayName` or `mailNickname`, but not multiple.

`-n, --displayName [displayName]`
: Display name of the Microsoft 365 Group to connect to Microsoft Teams. Specify either `id`, `displayName` or `mailNickname`, but not multiple.

`--mailNickname [mailNickname]`
: The mail alias of the Microsoft 365 Group to connect to Microsoft Teams. Specify either `id`, `displayName` or `mailNickname`, but not multiple.
```

<Global />

## Examples

Creates a new Microsoft Teams team under existing Microsoft 365 group with the specified id.

```sh
m365 entra m365group teamify --id e3f60f99-0bad-481f-9e9f-ff0f572fbd03
```

Creates a new Microsoft Teams team under existing Microsoft 365 group with the specified displayName.

```sh
m365 entra m365group teamify --displayName Finance
```

Creates a new Microsoft Teams team under existing Microsoft 365 group with the specified mailNickname._

```sh
m365 entra m365group teamify --mailNickname GroupName
```

## Response

The command won't return a response on success.
