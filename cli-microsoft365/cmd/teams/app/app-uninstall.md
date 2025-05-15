-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# teams app uninstall

Uninstalls an app from a Microsoft Team team

## Usage

```sh
m365 teams app uninstall [options]
```

## Options

```md definition-list
`--id <id>`
: The unique id of the app instance installed in the Microsoft Teams team

`--teamId <teamId>`
: The ID of the Microsoft Teams team from which to uninstall the app

`-f, --force`
: Don't prompt for confirmation when uninstalling the app
```

<Global />

## Remarks

The `id` has to be the id the app instance installed in the Microsoft Teams team.
Do not use the ID from the manifest of the zip app package or the id from the Microsoft Teams App Catalog.

## Examples

Uninstall an app from a Microsoft Teams team

```sh
m365 teams app uninstall --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --teamId 2609af39-7775-4f94-a3dc-0dd67657e900
```

## Response

The command won't return a response on success.
