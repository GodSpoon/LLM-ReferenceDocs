-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# pp aibuildermodel remove

Removes the specified Microsoft Power Platform aibuildermodel in the specified Power Platform environment

## Usage

```sh
m365 pp aibuildermodel remove [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment.

`-i, --id [id]`
: The id of the AI builder model. Specify either `id` or `name` but not both.

`-n, --name [name]`
: The name of the AI builder model. Specify either `id` or `name` but not both.

`--asAdmin`
: Run the command as admin for environments you do not have explicitly assigned permissions to.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Removes the AI builder model owned by the currently signed-in user based on the name parameter

```sh
m365 pp aibuildermodel remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "AI Builder Model Name"
```

Removes the AI builder model owned by the currently signed-in user based on the name parameter without confirmation

```sh
m365 pp aibuildermodel remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "AI Builder Model Name" --force
```

Removes the AI builder model owned by another user based on the id parameter

```sh
m365 pp aibuildermodel remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --id 9d9a13d0-6255-ed11-bba2-000d3adf774e  --asAdmin
```


## Response

The command won't return a response on success.
