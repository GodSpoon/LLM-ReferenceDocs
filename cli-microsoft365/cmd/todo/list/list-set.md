-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# todo list set

Updates a Microsoft To Do task list

## Usage

```sh
m365 todo list set [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the list to update. Specify either `id` or `name`, but not both.

`-n, --name [name]`
: The display name of the list to update. Specify either `id` or `name`, but not both.

`--newName <newName>`
: The new name for the task list.
```

<Global />

## Examples

Rename the list with a specific ID

```sh
m365 todo list set --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER=" --newName "My updated task list"
```

Rename a list with a specific title

```sh
m365 todo list set --name "My Task list" --newName "My updated task list"
```

## Response

The command won't return a response on success.
