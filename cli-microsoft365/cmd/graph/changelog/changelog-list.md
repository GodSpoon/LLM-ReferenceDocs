-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# graph changelog list

Gets an overview of specific API-level changes in Microsoft Graph v1.0 and beta

## Usage

```sh
m365 graph changelog list [options]
```

## Options

```md definition-list
`-v, --versions [versions]`
: Comma-separated list of versions to show changes for. `Beta`, `v1.0`. When no version is selected all versions are returned.

`-c, --changeType [changeType]`
: Change type to show changes for. `Addition`, `Change`, `Deletion`. When no changeType is selected all change types are returned.

`-s, --services [services]`
: Comma-separated list of services to show changes for. `Applications`, `Calendar`, `Change notifications`, `Cloud communications`, `Compliance`, `Cross-device experiences`, `Customer booking`, `Device and app management`, `Education`, `Files`, `Financials`, `Groups`, `Identity and access`, `Mail`, `Notes`, `Notifications`, `People and workplace intelligence`, `Personal contacts`, `Reports`, `Search`, `Security`, `Sites and lists`, `Tasks and plans`, `Teamwork`, `To-do tasks`, `Users`, `Workbooks and charts`. When no service is selected all services are returned.

`--startDate [startDate]`
: The startdate used to query for changes. Supported date format is `YYYY-MM-DD`. When no date is specified all changes are returned.

`--endDate [endDate]`
: The enddate used to query for changes. Supported date format is `YYYY-MM-DD`. When no date is specified all changes are returned.
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

## Examples

Get all changes within Microsoft Graph.

```sh
m365 graph changelog list
```

Get all changes within Microsoft Graph for the services _Groups_ and _Users_.

```sh
m365 graph changelog list --services 'Groups,Users'
```

Get all changes within Microsoft Graph that happend between _2021-01-01_ and _2021-05-01_.

```sh
m365 graph changelog list --startDate '2021-01-01' --endDate '2021-05-01'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "guid": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "category": "v1.0",
      "title": "Teamwork and communications",
      "description": "Added the **chatMessageActions** enumeration type.\
Added the [chatMessageHistoryItem](https://learn.microsoft.com/graph/api/resources/chatMessageHistoryItem?view=graph-rest-1.0) resource type.\
Added the **messageHistory** property to the [chatMessage](https://learn.microsoft.com/graph/api/resources/chatMessage?view=graph-rest-1.0) resource.\
",
      "pubDate": "2023-05-18T23:04:05.000Z"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  category  title                        description
  --------  ---------------------------  ----------------------------------------------
  v1.0      Teamwork and communications  Added the chatMessageActions enumeration type.
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  guid,category,title,description
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,v1.0,Teamwork and communications,"Added the **chatMessageActions** enumeration type.
  Added the [chatMessageHistoryItem](https://learn.microsoft.com/graph/api/resources/chatMessageHistoryItem?view=graph-rest-1.0) resource type.
  Added the **messageHistory** property to the [chatMessage](https://learn.microsoft.com/graph/api/resources/chatMessage?view=graph-rest-1.0) resource.
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # graph changelog list 

  Date: 2023-05-22

  ## Teamwork and communications

  Property | Value
  ---------|-------
  guid | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  category | v1.0
  title | Teamwork and communications
  description | Added the \*\*chatMessageActions\*\* enumeration type.
  <br>Added the [chatMessageHistoryItem](https://learn.microsoft.com/graph/api/resources/chatMessageHistoryItem?view=graph-rest-1.0) resource type.
  <br>Added the \*\*messageHistory\*\* property to the [chatMessage](https://learn.microsoft.com/graph/api/resources/chatMessage?view=graph-rest-1.0) resource.
  ```

  </TabItem>
</Tabs>
