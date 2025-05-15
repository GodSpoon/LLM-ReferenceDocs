<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# pp solution publisher remove

Removes the specified publisher in the specified Power Platform environment

## Usage

```sh
m365 pp solution publisher remove [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment.

`-i, --id [id]`
: The id of the publisher. Specify either `id` or `name` but not both.

`-n, --name [name]`
: The unique name of the publisher. Specify either `id` or `name` but not both.

`--asAdmin`
: Run the command as admin for environments you do not have explicitly assigned permissions to.

`-f, --force`
: Don't prompt for confirmation
```

<Global />

## Examples

Removes the specified publisher based on the name parameter

```sh
m365 pp solution publisher remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Publisher Name"
```

Removes the specified publisher based on the name parameter without confirmation

```sh
m365 pp solution publisher remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Publisher Name" --force
```

Removes the specified publisher based on the name parameter as admin

```sh
m365 pp solution publisher remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Publisher Name" --asAdmin
```

Removes the specified publisher owned by the currently signed-in user based on the id parameter

```sh
m365 pp solution publisher remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --id 00000001-0000-0000-0001-00000000009b
```

## Response

The command won't return a response on success.
