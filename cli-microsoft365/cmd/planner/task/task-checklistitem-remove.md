-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# planner task checklistitem remove

Removes the checklist item from the Planner task.

## Usage

```sh
m365 planner task checklistitem remove [options]
```

## Options

```md definition-list
`-i, --id <id>`
: ID of the checklist item.

`--taskId <taskId>`
: ID of the task.

`-f, --force`
: Don't prompt for confirmation
```

<Global />

## Examples

Removes a checklist item with the id _40012_ from the Planner task with the id _2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2_

```sh
m365 planner task checklistitem remove --id "40012" --taskId "2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2" 
```

Removes a checklist item with the id _40012_ from the Planner task with the id _2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2_ without prompt

```sh
m365 planner task checklistitem remove --id "40012" --taskId "2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2" --force
```

## Response

The command won't return a response on success.
