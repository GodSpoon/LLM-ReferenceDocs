-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# pp solution remove

Removes the specified solution in the specified Power Platform environment

## Usage

```sh
m365 pp solution remove [options]
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

`-f, --force`
: Don't prompt for confirmation
```

<Global />

## Examples

Removes the specified solution with a specific name, owned by the currently signed-in user

```sh
m365 pp solution remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Solution Name"
```

Removes the specified solution owned by the currently signed-in user based on the name parameter without confirmation

```sh
m365 pp solution remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Solution Name" --force
```

Removes the specified solution owned by another user based on the name parameter

```sh
m365 pp solution remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Solution Name" --asAdmin
```

Removes the specified solution owned by another user based on the name parameter without confirmation

```sh
m365 pp solution remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "solution Name" --asAdmin --force
```

Removes the specified solution owned by the currently signed-in user based on the id parameter

```sh
m365 pp solution remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --id 00000001-0000-0000-0001-00000000009b
```

Removes the specified solution owned by the currently signed-in user based on the id parameter without confirmation

```sh
m365 pp solution remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --id 00000001-0000-0000-0001-00000000009b --force
```

Removes the specified solution owned by another user based on the id parameter

```sh
m365 pp solution remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --id 00000001-0000-0000-0001-00000000009b --asAdmin
```

Removes the specified solution owned by another user based on the id parameter without confirmation

```sh
m365 pp solution remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --id 00000001-0000-0000-0001-00000000009b --asAdmin --force
```

## Response

The command won't return a response on success.
