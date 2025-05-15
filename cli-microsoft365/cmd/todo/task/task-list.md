-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# todo task list

List tasks from a Microsoft To Do task list

## Usage

```sh
m365 todo task list [options]
```

## Options

```md definition-list
`--listName [listName]`
: The name of the task list to return tasks from. Specify either `listName` or `listId`, not both

`--listId [listId]`
: The id of the task list to return tasks from. Specify either `listName` or `listId`, not both
```

<Global />

## Examples

List tasks from Microsoft To Do tasks list with the name _My task list_

```sh
m365 todo task list --listName "My task list"
```

List tasks from Microsoft To Do tasks list with the id EXAMPLE_SECRET_VALUE_PLACEHOLDER==

```sh
m365 todo task list --listId "EXAMPLE_SECRET_VALUE_PLACEHOLDER=="
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "importance": "high",
      "isReminderOn": true,
      "status": "notStarted",
      "title": "New task",
      "createdDateTime": "2022-10-29T11:03:20.9175176Z",
      "lastModifiedDateTime": "2022-10-29T11:13:23.6672968Z",
      "hasAttachments": false,
      "categories": [],
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER=",
      "body": {
        "content": "I should not forget this",
        "contentType": "text"
      },
      "dueDateTime": {
        "dateTime": "2023-01-01T00:00:00.0000000",
        "timeZone": "UTC"
      },
      "reminderDateTime": {
        "dateTime": "2023-01-01T12:00:00.0000000",
        "timeZone": "UTC"
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                                                                                                                                        title           status      createdDateTime               lastModifiedDateTime
  --------------------------------------------------------------------------------------------------------------------------------------------------------  --------------  ----------  ----------------------------  ----------------------------
  EXAMPLE_SECRET_VALUE_PLACEHOLDER=  New task        notStarted  2022-10-29T11:03:20.9175176Z  2022-10-29T11:13:23.6672968Z
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,title,status,createdDateTime,lastModifiedDateTime
  EXAMPLE_SECRET_VALUE_PLACEHOLDER=,New task,notStarted,2022-10-29T11:03:20.9175176Z,2022-10-29T11:13:23.6672968Z
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # todo task list --listName "My task list"

  Date: 25/5/2023

  ## List down the To do lists using CLI for M365 (EXAMPLE_SECRET_VALUE_PLACEHOLDER=)
  
  Property | Value
  ---------|-------
  importance | high
  isReminderOn | true
  status | notStarted
  title | New task
  createdDateTime | 2022-10-29T11:03:20.9175176Z
  lastModifiedDateTime | 2022-10-29T11:13:23.6672968Z
  hasAttachments | false
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  ```

  </TabItem>
</Tabs>
