-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# todo list list

Returns a list of Microsoft To Do task lists

## Usage

```sh
m365 todo list list [options]
```

## Options

<Global />

## Examples

Get the list of Microsoft To Do task lists

```sh
m365 todo list list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "displayName": "Tasks",
      "isOwner": true,
      "isShared": false,
      "wellknownListName": "defaultList",
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  displayName     id                                                                                                      
  --------------  ------------------------------------------------------------------------------------------------------------------------
  Tasks           EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  displayName,id
  Tasks,EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # todo list list

  Date: 25/5/2023

  ## Tasks (EXAMPLE_SECRET_VALUE_PLACEHOLDER)
  
  Property | Value
  ---------|-------
  displayName | Tasks
  isOwner | true
  isShared | false
  wellknownListName | defaultList
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
</Tabs>
