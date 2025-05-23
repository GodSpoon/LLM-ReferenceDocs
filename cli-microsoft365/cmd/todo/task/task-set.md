-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# todo task set

Update a task in a Microsoft To Do task list

## Usage

```sh
m365 todo task set [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The id of the task to update.

`-t, --title [title]`
: Sets the task title.

`-s, --status [status]`
: Sets the status of the task. Allowed values are `notStarted`, `inProgress`, `completed`, `waitingOnOthers`, `deferred`.

`--listName [listName]`
: The name of the task list in which the task exists. Specify either `listName` or `listId`, but not both.

`--listId [listId]`
: The id of the task list in which the task exists. Specify either `listName` or `listId`, but not both.

`--bodyContent [bodyContent]`
: The body content of the task. In the UI this is called 'notes'.

`--bodyContentType [bodyContentType]`
: The type of the body content. Allowed values: `text` and `html`. Defaults to `text`.

`--importance [importance]`
: The importance of the task. Allowed values: `low`, `normal`, `high`.

`--dueDateTime [dueDateTime]`
: The date and time when the task is due. This should be defined as a valid ISO 8601 string in the UTC time zone. Only date value is needed, time value is always ignored.

`--reminderDateTime [reminderDateTime]`
: The date and time for a reminder alert of the task to occur. This should be defined as a valid ISO 8601 string in the UTC time zone.

`--categories [categories]`
: Comma-separated list of categories associated with the task.

`--completedDateTime [completedDateTime]`
: The date and time when the task was finished. This should be defined as a valid ISO 8601 string. e.g. `2021-12-16T18:28:48.6964197Z`.

`--startDateTime [startDateTime]`
: The date and time when the task is scheduled to start. This should be defined as a valid ISO 8601 string. e.g. `2021-12-16T18:28:48.6964197Z`.
```

<Global />

## Remarks

When you specify the values for `categories`, each category can correspond to the displayName property of an [outlookCategory](https://learn.microsoft.com/graph/api/resources/outlookcategory?view=graph-rest-1.0). It is permissible to use distinct names.

## Examples

Update a task with title _New task_ to _Update doco_ in Microsoft To Do tasks list with a specific name.

```sh
m365 todo task set --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER=" --title "Update doco" --listName "My task list"
```

Update a task with status from _notStarted_ to _inProgress_ in Microsoft To Do tasks list with a specific name.

```sh
m365 todo task set --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER=" --status "inProgress" --listName "My task list"
```

Update a task with bodyContent and reminder and flag it as important in Microsoft To Do tasks list with a specific name.

```sh
m365 todo task set --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER=" --listName "My task list" --bodyContent "I should not forget this" --reminderDateTime 2023-01-01T12:00:00Z --importance high
```

Update a task with due date in Microsoft To Do tasks list with list id.

```sh
m365 todo task set --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER=" --listId "EXAMPLE_SECRET_VALUE_PLACEHOLDER==" --dueDateTime 2023-01-01
```

Update a task to Microsoft To Do with several categories.

```sh
m365 todo task set --title "New task" --listName "My task list" --categories "Red category,Important"
```

Update a task to Microsoft To Do with a start date and set a reminder for the task.

```sh
m365 todo task set --title "New task" --listName "My task list" --startDateTime "2023-12-16T18:28:48.6964197Z" --isReminderOn true
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "importance": "high",
    "isReminderOn": true,
    "status": "notStarted",
    "title": "Update doco",
    "createdDateTime": "2022-10-29T11:03:20.9175176Z",
    "lastModifiedDateTime": "2022-10-30T14:07:03.0718199Z",
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
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  body                : {"content":"I should not forget this","contentType":"text"}
  categories          : []
  createdDateTime     : 2022-10-29T11:03:20.9175176Z
  dueDateTime         : {"dateTime":"2023-01-01T00:00:00.0000000","timeZone":"UTC"}
  hasAttachments      : false
  id                  : EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  importance          : high
  isReminderOn        : true
  lastModifiedDateTime: 2022-10-30T14:08:17.6665299Z
  reminderDateTime    : {"dateTime":"2023-01-01T12:00:00.0000000","timeZone":"UTC"}
  status              : notStarted
  title               : Update doco
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  importance,isReminderOn,status,title,createdDateTime,lastModifiedDateTime,hasAttachments,categories,id,body,dueDateTime,reminderDateTime
  high,1,notStarted,Update doco,2022-10-29T11:03:20.9175176Z,2022-10-30T14:09:14.7687057Z,,[],EXAMPLE_SECRET_VALUE_PLACEHOLDER=,"{""content"":""I should not forget this"",""contentType"":""text""}","{""dateTime"":""2023-01-01T00:00:00.0000000"",""timeZone"":""UTC""}","{""dateTime"":""2023-01-01T12:00:00.0000000"",""timeZone"":""UTC""}"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # todo task set --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER=" --title "Update doco" --listName "My task list" --status "notStarted"

  Date: 4/3/2023

  ## Update doco (EXAMPLE_SECRET_VALUE_PLACEHOLDER=)

  Property | Value
  ---------|-------
  importance | high
  isReminderOn | true
  status | notStarted
  title | Update doco
  createdDateTime | 2022-10-29T11:03:20.9175176Z
  lastModifiedDateTime | 2022-10-30T14:07:03.0718199Z
  hasAttachments | false
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  reminderDateTime |  {"dateTime": "2023-01-01T12:00:00.0000000","timeZone": "UTC"}
  ```

  </TabItem>
</Tabs>
