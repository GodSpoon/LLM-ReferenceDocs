-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# pa app export

Exports the specified Power App

## Usage

```sh
m365 pa app export [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The name (GUID) of the Power Apps app to export.

`-e, --environmentName <environmentName>`
: The name of the environment for which to export the app.

`--packageDisplayName [packageDisplayName]`
: The display name to use in the exported package.

`-d, --packageDescription [packageDescription]`
: The description to use in the exported package.

`-c, --packageCreatedBy [packageCreatedBy]`
: The name of the person to be used as the creator of the exported package.

`-s, --packageSourceEnvironment [packageSourceEnvironment]`
: The name of the source environment from which the exported package was taken.

`-p, --path [path]`
: The path to save the exported package to. If not specified the app will be exported in the current working directory.
```

<Global />

## Examples

Export the specified Power App as a ZIP file

```sh
m365 pa app export --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d
```

Export the specified Power App as a ZIP file with a custom package name

```sh
m365 pa app export --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d --packageDisplayName "Assets app"
```

Export the specified Power App as a ZIP file with the package displayname, package description, the one who created it, the package source environment and the path

```sh
m365 pa app export --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d --packageDisplayName "Assets app" --packageDescription "App to track assets of people" --packageCreatedBy "John Doe" --packageSourceEnvironment "Contoso" --path "C:/Users/John/Documents"
```

## Response

The command won't return a response on success.
