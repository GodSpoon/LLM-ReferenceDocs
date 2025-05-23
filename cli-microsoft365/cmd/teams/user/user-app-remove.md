-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# teams user app remove

Uninstall an app from the personal scope of the specified user

## Usage

```sh
m365 teams user app remove [options]
```

## Options

```md definition-list
`--id [id]`
: The unique id of the app instance installed for the user. Specify either `id` or `name`.

`--name [name]`
: Name of the app instance installed for the user. Specify either `id` or `name`.

`--userId [userId]`
: The ID of the user to uninstall the app for. Specify either `userId` or `userName`.

`--userName [userName]`
: The UPN of the user to uninstall the app for. Specify either `userId` or `userName`.

`-f, --force`
: Confirm removal of app for user.
```

<Global />

## Remarks

The `id` has to be the id of the app instance installed for the user.
Do not use the ID from the manifest of the zip app package or the id from the Microsoft Teams App Catalog.

## Examples

Uninstall an app by id for the specified user.

```sh
m365 teams user app remove --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userId 2609af39-7775-4f94-a3dc-0dd67657e900
```

Uninstall an app by id for the specified user using its UPN.

```sh
m365 teams user app remove --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userName admin@contoso.com
```

Uninstall an app by name for the specified user.

```sh
m365 teams user app remove --name HelloWorld --userId 2609af39-7775-4f94-a3dc-0dd67657e900
```

## Response

The command won't return a response on success.
