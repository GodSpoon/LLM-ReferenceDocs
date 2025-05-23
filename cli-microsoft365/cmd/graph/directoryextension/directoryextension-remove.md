-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# graph directoryextension remove

Removes a directory extension

## Usage

```sh
m365 graph directoryextension remove [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the directory extension to remove. Specify either `id` or `name`, but not both.

`-n, --name [name]`
: The name of the directory extension to remove. Specify either `id` or `name`, but not both.

`--appId [appId]`
: Application (client) ID of the Entra application where the directory extension is registered. Specify either `appId`, `appObjectId` or `appName`, but not multiple.

`--appObjectId [appObjectId]`
: Object ID of the Entra application where the directory extension is registered. Specify either `appId`, `appObjectId` or `appName`, but not multiple.

`--appName [appName]`
: The name of Entra application where the directory extension is registered. Specify either `appId`, `appObjectId` or `appName`, but not multiple.

`-f, --force`
: Don't prompt for confirmation before removing the directory extension
```

<Global />

## Examples

Remove a directory extension specified by name from an application specified by app object id and don't prompt for confirmation

```sh
m365 graph directoryextension remove --name EXAMPLE_SECRET_VALUE_PLACEHOLDER --appObjectId 1caf7dcd-7e83-4c3a-94f7-932a1299c844 --force
```

Remove a directory extension specified by id from an application specified by app name and don't prompt for confirmation

```sh
m365 graph directoryextension remove --id 522817ae-5c95-4243-96c1-f85231fcbc1f --appName ContosoApp
```

## Response

The command won't return a response on success.

## More information

- Directory extensions: https://learn.microsoft.com/graph/extensibility-overview#directory-microsoft-entra-id-extensions
