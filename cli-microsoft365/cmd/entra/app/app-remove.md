-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra app remove

Removes an Entra app registration

## Usage

```sh
m365 entra app remove [options]
```

## Alias

```sh
m365 entra appregistration remove [options]
```

## Options

```md definition-list
`--appId [appId]`
: Application (client) ID of the Entra application registration to remove. Specify either `appId`, `objectId` or `name` but not multiple.

`--objectId [objectId]`
: Object ID of the Entra application registration to remove. Specify either `appId`, `objectId` or `name` but not multiple.

`--name [name]`
: Name of the Entra application registration to remove. Specify either `appId`, `objectId` or `name` but not multiple.

`-f, --force`
: Don't prompt for confirmation to remove the app.
```

<Global />

## Remarks

For best performance use the `objectId` option to reference the Entra application registration to remove. If you use `appId` or `name`, this command will first need to find the corresponding object ID for that application.

If the command finds multiple Entra application registrations with the specified app name, it will prompt you to disambiguate which app it should use, listing the discovered object IDs.

## Examples

Remove the Entra application registration by its app (client) ID.

```sh
m365 entra app remove --appId d75be2e1-0204-4f95-857d-51a37cf40be8
```

Remove the Entra application registration by its object ID.

```sh
m365 entra app remove --objectId d75be2e1-0204-4f95-857d-51a37cf40be8
```

Remove the Entra application registration by its name. Will NOT prompt for confirmation before deleting.

```sh
m365 entra app remove --name "My app" --force
```

## Response

The command won't return a response on success.
