-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# todo task get

Gets a specific task from a Microsoft To Do task list

## Usage

```sh
m365 todo task get [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The ID of the task in the list.

`--listName [listName]`
: The name of the task list to return tasks from. Specify either `listName` or `listId`, but not both.

`--listId [listId]`
: The id of the task list to return tasks from. Specify either `listName` or `listId`, but not both.
```

<Global />

## Examples

Gets a specific task from a Microsoft To Do tasks list based on the name of the list and the task id.

```sh
m365 todo task get --listName "My task list" --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER="
```

Gets a specific task from a Microsoft To Do tasks list based on the id of the list and the task id.

```sh
m365 todo task get --listId "EXAMPLE_SECRET_VALUE_PLACEHOLDER==" --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER="
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "importance": "normal",
    "isReminderOn": false,
    "status": "notStarted",
    "title": "Stay healthy",
    "createdDateTime": "2022-10-23T14:05:09.2673009Z",
    "lastModifiedDateTime": "2022-10-23T14:15:11.3180312Z",
    "hasAttachments": false,
    "categories": [],
    "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER=",
    "body": {
      "content": "",
      "contentType": "text"
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  body                : {"content":"","contentType":"text"}
  categories          : []
  createdDateTime     : 2022-10-23T14:05:09.2673009Z
  hasAttachments      : false
  id                  : EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  importance          : normal
  isReminderOn        : false
  lastModifiedDateTime: 2022-10-23T14:15:11.3180312Z
  status              : notStarted
  title               : Stay healthy
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,title,status,createdDateTime,lastModifiedDateTime
  EXAMPLE_SECRET_VALUE_PLACEHOLDER=,Stay healthy,notStarted,2022-10-23T14:05:09.2673009Z,2022-10-23T14:15:11.3180312Z
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # todo task get --listName "My task list" --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER="

  Date: 25/5/2023

  ## List down the To do lists using CLI for M365 (EXAMPLE_SECRET_VALUE_PLACEHOLDER=)
  
  Property | Value
  ---------|-------
  importance | normal
  isReminderOn | false
  status | notStarted
  title | Stay healthy
  createdDateTime | 2022-10-23T14:05:09.2673009Z
  lastModifiedDateTime | 2022-10-23T14:15:11.3180312Z
  hasAttachments | false
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  ```

  </TabItem>
</Tabs>
