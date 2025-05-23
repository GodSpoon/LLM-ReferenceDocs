-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# pp copilot remove

Removes the specified copilot

## Usage

```sh
m365 pp copilot remove [options]
```

## Alias

```sh
m365 pp chatbot remove [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment.

`-i, --id [id]`
: The id of the copilot. Specify either `id` or `name` but not both.

`-n, --name [name]`
: The name of the copilot. Specify either `id` or `name` but not both.

`--asAdmin`
: Run the command as admin for environments you do not have explicitly assigned permissions to.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Removes the specified Microsoft Power Platform copilot owned by the currently signed-in user based on name

```sh
m365 pp copilot remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Chatbot Name"
```

Removes the specified Microsoft Power Platform copilot owned by the currently signed-in user based on id without confirmation

```sh
m365 pp copilot remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --id 9d9a13d0-6255-ed11-bba2-000d3adf774e --force
```

Removes the specified Microsoft Power Platform copilot owned by another user based on name

```sh
m365 pp copilot remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Chatbot Name" --asAdmin
```

## Response

The command won't return a response on success.
