-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra m365group conversation list

Lists conversations for the specified Microsoft 365 group

## Usage

```sh
m365 entra m365group conversation list [options]
```

## Options

```md definition-list
`-i, --groupId [groupId]`
: The ID of the Microsoft 365 Group. Specify either `groupId` or `groupName`, but not both.

`-n, --groupName [groupName]`
: Display name of the Microsoft 365 Group. Specify either `groupId` or `groupName`, but not both.
```

<Global />

## Examples

Lists conversations for the Microsoft 365 group specified by id.

```sh
m365 entra m365group conversation list --groupId '00000000-0000-0000-0000-000000000000'
```

Lists conversations for the Microsoft 365 group specified by displayName.

```sh
m365 entra m365group conversation list --groupName Finance
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER=",
      "topic": "The new Finance group is ready",
      "hasAttachments": false,
      "lastDeliveredDateTime": "2023-06-01T20:31:57Z",
      "uniqueSenders": [
        "Finance"
      ],
      "preview": "Welcome to the Finance group.\
Use the group to share ideas, files, and important dates.\
Start a conversation\
Read group conversations or start your own.\
Add to the team site\
Start sharing and collaborating on content in SharePoint.\
Share files\
View"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  topic                           lastDeliveredDateTime  id
  ------------------------------  ---------------------  --------------------------------------------------------------------------------
  The new Finance group is ready  2023-06-01T20:31:57Z   EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,topic,hasAttachments,lastDeliveredDateTime,preview
  EXAMPLE_SECRET_VALUE_PLACEHOLDER=,The new Finance group is ready,,2023-06-01T20:31:57Z,"Welcome to the Finance group.
  Use the group to share ideas, files, and important dates.
  Start a conversation
  Read group conversations or start your own.
  Add to the team site
  Start sharing and collaborating on content in SharePoint.
  Share files
  View"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra m365group conversation list --groupId "1cdce329-46a9-4fd3-8826-fe6587d25a8c"

  Date: 2023-06-01

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER=

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  topic | The new Finance group is ready
  hasAttachments | false
  lastDeliveredDateTime | 2023-06-01T20:31:57Z
  <br>Viewe filesng and collaborating on content in SharePoint
  ```

  </TabItem>
</Tabs>
