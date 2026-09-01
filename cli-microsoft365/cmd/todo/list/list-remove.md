-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '../../_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# todo list remove

Removes a Microsoft To Do task list

## Usage

```sh
m365 todo list remove [options]
```

## Options

```md definition-list
`-n, --name [name]`
: The name of the task list to remove. Specify either `id` or `name`, but not both.

`-i, --id [id]`
: The ID of the task list to remove. Specify either `id` or `name`, but not both.

`-f, --force`
: Don't prompt for confirming removing the task list.
```

<Global />

## Permissions

<Tabs>
  <TabItem value="Delegated">

  | Resource        | Permissions     |
  |-----------------|-----------------|
  | Microsoft Graph | Tasks.ReadWrite |

  </TabItem>
  <TabItem value="Application">

  | Resource        | Permissions         |
  |-----------------|---------------------|
  | Microsoft Graph | Tasks.ReadWrite.All |

  </TabItem>
</Tabs>

## Examples

Remove a task list with specific name

```sh
m365 todo list remove --name "My task list"
```

Remove a task list with the ID without confirmation prompt

```sh
m365 todo list remove --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER=" --force
```

## Response

The command won't return a response on success.
