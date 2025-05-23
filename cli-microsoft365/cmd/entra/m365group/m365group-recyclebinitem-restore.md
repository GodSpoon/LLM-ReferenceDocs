-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra m365group recyclebinitem restore

Restores a deleted Microsoft 365 Group

## Usage

```sh
m365 entra m365group recyclebinitem restore [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the Microsoft 365 Group to restore. Specify either `id`, `displayName` or `mailNickname` but not multiple.

`-d, --displayName [displayName]`
: Display name for the Microsoft 365 Group to restore. Specify either `id`, `displayName` or `mailNickname` but not multiple.

`-m, --mailNickname [mailNickname]`
: Name of the group e-mail (part before the @). Specify either `id`, `displayName` or `mailNickname` but not multiple.
```

<Global />

## Examples

Restores the Microsoft 365 Group with specific ID

```sh
m365 entra m365group recyclebinitem restore --id 28beab62-7540-4db1-a23f-29a6018a3848
```

Restores the Microsoft 365 Group with specific name

```sh
m365 entra m365group recyclebinitem restore --displayName "My Group"
```

Restores the Microsoft 365 Group with specific mail nickname

```sh
m365 entra m365group recyclebinitem restore --mailNickname "Mygroup"
```

## Response

The command won't return a response on success.
