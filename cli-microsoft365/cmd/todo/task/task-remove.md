-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# todo task remove

Removes the specified Microsoft To Do task

## Usage

```sh
m365 todo task remove [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The id of the task to remove.

`--listName [listName]`
: The name of the task list in which the task exists. Specify either `listId` or `listName`, but not both.

`--listId [listId]`
: The id of the task list in which the task exists. Specify either `listId` or `listName`, but not both.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Removes Microsoft To Do task with the specified id in a list with the specified name

```sh
m365 todo task remove --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER=" --listName "Tasks"
```

Removes Microsoft To Do task with the specified id in a list with the specified id

```sh
m365 todo task remove --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER=" --listId "EXAMPLE_SECRET_VALUE_PLACEHOLDER="
```

## Response

The command won't return a response on success.
