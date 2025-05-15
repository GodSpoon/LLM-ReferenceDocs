-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# todo list add

Adds a new Microsoft To Do task list

## Usage

```sh
m365 todo list add [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The name of the task list to add.
```

<Global />

## Examples

Add a task list with the name _My task list_

```sh
m365 todo list add --name "My task list"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "displayName": "My task list",
    "isOwner": true,
    "isShared": false,
    "wellknownListName": "none",
    "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER="
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  displayName      : My task list
  id               : EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  isOwner          : true
  isShared         : false
  wellknownListName: none
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  displayName,isOwner,isShared,wellknownListName,id
  My task list,1,,none,EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # todo list add --name "My task list"

  Date: 26/5/2023

  ## My task list (EXAMPLE_SECRET_VALUE_PLACEHOLDER=)
  
  Property | Value
  ---------|-------
  displayName | My task list
  isOwner | true
  isShared | false
  wellknownListName | none
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  ```
  </TabItem>
</Tabs>
