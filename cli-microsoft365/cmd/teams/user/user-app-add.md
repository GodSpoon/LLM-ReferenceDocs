-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# teams user app add

Install an app in the personal scope of the specified user

## Usage

```sh
m365 teams user app add [options]
```

## Options

```md definition-list
`--id [id]`
: The ID of the app to install. Specify either `id` or `name` but not both.

`--name [name]`
: Name of the app to install. Specify either `id` or `name` but not both.

`--userId [userId]`
: The ID of the user to install the app for. Specify either `userId` or `userName` but not both.

`--userName [userName]`
: The UPN of the user to install the app for. Specify either `userId` or `userName` but not both.
```

<Global />

## Remarks

The `id` has to be the ID of the app from the Microsoft Teams App Catalog. Do not use the ID from the manifest of the zip app package. Use the [teams app list](../app/app-list.mdx) command to get this ID.

## Examples

Install an app by id from the catalog for the specified user by id.

```sh
m365 teams user app add --id 4440558e-8c73-4597-abc7-3644a64c4bce --userId 2609af39-7775-4f94-a3dc-0dd67657e900
```

Install an app by name from the catalog for the specified user by name.

```sh
m365 teams user app add --name HelloWorld --userName admin@contoso.com
```

## Response

The command won't return a response on success.
