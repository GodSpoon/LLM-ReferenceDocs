-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# todo list get

Returns a specific Microsoft To Do task list

## Usage

```sh
m365 todo list get [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The id of the list. Specify either `id` or `name`, but not both.

`-n, --name [name]`
: The name of the list. Specify either `id` or `name`, but not both.
```

<Global />

## Examples

Get a specific Microsoft To Do task list based on id.

```sh
m365 todo list get --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER="
```

Get a specific Microsoft To Do task list based on name.

```sh
m365 todo list get --name "Task list"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "displayName": "Task list",
    "isOwner": true,
    "isShared": false,
    "wellknownListName": "defaultList",
    "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER="
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  displayName      : Task list
  id               : EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  isOwner          : true
  isShared         : false
  wellknownListName: defaultList
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  displayName,id
  Task list,EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # todo list get --name "Task list"

  Date: 25/5/2023

  ## Task list (EXAMPLE_SECRET_VALUE_PLACEHOLDER=)
  
  Property | Value
  ---------|-------
  displayName | Task list
  isOwner | true
  isShared | false
  wellknownListName | defaultList
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  ```
  
  </TabItem>
</Tabs>
