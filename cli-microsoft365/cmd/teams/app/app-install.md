-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# teams app install

Installs a Microsoft Teams team app from the catalog in the specified team or for the specified user

## Usage

```sh
m365 teams app install [options]
```

## Options

```md definition-list
`-i, --id [id]`
: ID of the app to update. Specify either id or name, but not both

`-n, --name [name]`
: The display name of the app to update. Specify either id or name, but not both

`--teamId [teamId]`
: The ID of the Microsoft Teams team to which to install the app

`--userId [userId]`
: The ID of the user for who to install the app. Specify either `userId` or `userName` to install a personal app for a user.

`--userName [userName]`
: The UPN of the user for who to install the app. Specify either `userId` or `userName` to install a personal app for a user.
```

<Global />

## Remarks

The `id` has to be the ID of the app from the Microsoft Teams App Catalog. Do not use the ID from the manifest of the zip app package. Use the [teams app list](./app-list.mdx) command to get this ID instead.

## Examples

Install an app from the catalog in a Microsoft Teams team

```sh
m365 teams app install --id 4440558e-8c73-4597-abc7-3644a64c4bce --teamId 2609af39-7775-4f94-a3dc-0dd67657e900
```

Install a personal app for the user specified using their user name

```sh
m365 teams app install --id 4440558e-8c73-4597-abc7-3644a64c4bce --userName steve@contoso.com
```

Install a personal app for the user specified using their ID

```sh
m365 teams app install --id 4440558e-8c73-4597-abc7-3644a64c4bce --userId 2609af39-7775-4f94-a3dc-0dd67657e900
```

Install an app with name _Test app_ from the catalog in a Microsoft Teams team

```sh
m365 teams app install --name "Test app" --teamId 2609af39-7775-4f94-a3dc-0dd67657e900
```

## Response

The command won't return a response on success.
