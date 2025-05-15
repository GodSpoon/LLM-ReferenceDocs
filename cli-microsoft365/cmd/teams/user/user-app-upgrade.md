-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# teams user app upgrade

Upgrade an app in the personal scope of the specified user

## Usage

```sh
m365 teams user app upgrade [options]
```

## Options

```md definition-list
`--id [id]`
: The unique id of the app instance installed for the user. Specify either `id` or `name`.

`--name [name]`
: Name of the app instance installed for the user. Specify either `id` or `name`.

`--userId [userId]`
: The ID of the user to upgrade the app for. Specify either `userId` or `userName` but not both.

`--userName [userName]`
: The UPN of the user to upgrade the app for. Specify either `userId` or `userName` but not both.
```

<Global />

## Examples

Upgrade an app by name for the specified user using its UPN.

```sh
m365 teams user app upgrade --name HelloWorld --userName admin@contoso.com
```

Upgrade an app by name for the specified user using its id.

```sh
m365 teams user app upgrade --name HelloWorld --userId 2609af39-7775-4f94-a3dc-0dd67657e900
```

Upgrade an app by id for the specified user using its UPN.

```sh
m365 teams user app upgrade --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userName admin@contoso.com
```

Upgrade an app by id for the specified user using its id.

```sh
m365 teams user app upgrade --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userId 2609af39-7775-4f94-a3dc-0dd67657e900
```

## Response

The command won't return a response on success.
