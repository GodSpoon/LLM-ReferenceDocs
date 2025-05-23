-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# pp solution publish

Publishes the components of a solution in a given Power Platform environment

## Usage

```sh
m365 pp solution publish [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment.

`-i, --id [id]`
: The id of the solution. Specify either `id` or `name` but not both.

`-n, --name [name]`
: The unique name (not the display name) of the solution. Specify either `id` or `name` but not both.

`--asAdmin`
: Run the command as admin for environments you do not have explicitly assigned permissions to.

`--wait`
: Wait for the job to complete
```

<Global />

## Examples

Publishes the components of a specified solution with a specific name, owned by the currently signed-in user

```sh
m365 pp solution publish --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Solution Name"
```

Publishes the components of a specified solution owned by the currently signed-in user based on the id parameter and waits for completion

```sh
m365 pp solution publish --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --id 00000001-0000-0000-0001-00000000009b --wait
```

Publishes the components of a specified solution owned by another user based on the name parameter

```sh
m365 pp solution publish --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Solution Name" --asAdmin
```

## Response

The command won't return a response on success.
