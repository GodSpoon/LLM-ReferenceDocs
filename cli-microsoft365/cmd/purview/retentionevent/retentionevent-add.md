-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# purview retentionevent add

Create a retention event

## Usage

```sh
m365 purview retentionevent add [options]
```

## Options

```md definition-list
`-n, --displayName <displayName>`
: The display name of the event.

`-e, --eventTypeName [eventTypeName]`
: Name of the event type associated with the event. Specify either `eventTypeId` or `eventTypeName` but not both.

`-i, --eventTypeId [eventTypeId]`
: Id of the event type associated with the event. Specify either `eventTypeId` or `eventTypeName` but not both.

`-d, --description [description]`
: A description for the event.

`--triggerDateTime [triggerDateTime]`
: Optional time when the event should be triggered.

`-a, --assetIds [assetIds]`
: The Asset IDs for items in SharePoint and OneDrive that are related to this event. Only items that have labels associated with the event type you chose will be retained. Specify `assetIds` and/or `keywords`, but at least one.

`-k, --keywords [keywords]`
: The keywords for items in Exchange that are related to this event. Only items that have labels associated with the event type you chose will be retained. Specify `assetIds` and/or `keywords`, but at least one.
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

## Examples

Create a retention event to start retention at the end of 2022 for all employee documents that have been labeled and have the Asset ID _EmployeeNr1234_.

```sh
m365 purview retentionevent add --displayName 'Employee information expiration' --description 'Employee documents expired due to offboarding' --eventTypeName 'CustomRetentionTime' --triggerDateTime '2022-12-31' --assetIds 'ComplianceAssetId:EmployeeNr1234'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "displayName": "Event display name",
    "description": "Event description",
    "eventTriggerDateTime": "2023-04-02T15:47:54Z",
    "lastStatusUpdateDateTime": "0001-01-01T00:00:00Z",
    "createdDateTime": "2023-02-20T18:53:05Z",
    "lastModifiedDateTime": "2023-02-20T18:53:05Z",
    "id": "9f5c1a04-8f7a-4bff-e400-08db1373b324",
    "eventQueries": [
      {
        "queryType": "files",
        "query": "filesQuery,filesQuery1"
      },
      {
        "queryType": "messages",
        "query": "messagesQuery,messagesQuery1"
      }
    ],
    "eventStatus": {
      "error": null,
      "status": "pending"
    },
    "eventPropagationResults": [],
    "createdBy": {
      "user": {
        "id": null,
        "displayName": "John Doe"
      }
    },
    "lastModifiedBy": {
      "user": {
        "id": null,
        "displayName": "John Doe"
      }
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  createdBy               : {"user":{"id":null,"displayName":"John Doe"}}
  createdDateTime         : 2023-02-20T18:53:05Z
  description             : Event description
  displayName             : Event display name
  eventPropagationResults : []
  eventQueries            : [{"queryType":"files","query":"filesQuery,filesQuery1"},{"queryType":"messages","query":"messagesQuery,messagesQuery1"}]
  eventStatus             : {"error":null,"status":"pending"}
  eventTriggerDateTime    : 2023-04-02T15:47:54Z
  id                      : 9f5c1a04-8f7a-4bff-e400-08db1373b324
  lastModifiedBy          : {"user":{"id":null,"displayName":"John Doe"}}
  lastModifiedDateTime    : 2023-02-20T18:53:05Z
  lastStatusUpdateDateTime: 0001-01-01T00:00:00Z 
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  displayName,description,eventTriggerDateTime,lastStatusUpdateDateTime,createdDateTime,lastModifiedDateTime,id,eventQueries,eventStatus,eventPropagationResults,createdBy,lastModifiedBy
  Event display name,Event description,2023-04-02T15:47:54Z,0001-01-01T00:00:00Z,2023-02-20T18:53:05Z,2023-02-20T18:53:05Z,9f5c1a04-8f7a-4bff-e400-08db1373b324,"[{""queryType"":""files"",""query"":""filesQuery,filesQuery1""},{""queryType"":""messages"",""query"":""messagesQuery,messagesQuery1""}]","{""error"":null,""status"":""pending""}",[],"{""user"":{""id"":null,""displayName"":""John Doe""}}","{""user"":{""id"":null,""displayName"":""John Doe""}}"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # purview retentionevent add --displayName "Event display name" --eventType "Event Type" --description "Event description" --triggerDateTime "2023-04-02T15:47:54Z" --assetIds "filesQuery,filesQuery1" --keywords "messagesQuery,messagesQuery1"

  Date: 20/2/2023

  ## Event display name (9f5c1a04-8f7a-4bff-e400-08db1373b324)

  Property | Value
  ---------|-------
  displayName | Event display name
  description | Event description
  eventTriggerDateTime | 2023-04-02T15:47:54Z
  lastStatusUpdateDateTime | 0001-01-01T00:00:00Z
  createdDateTime | 2023-02-20T18:53:05Z
  lastModifiedDateTime | 2023-02-20T18:53:05Z
  id | 9f5c1a04-8f7a-4bff-e400-08db1373b324
  ```

  </TabItem>
</Tabs>

## More information

This command is part of a series of commands that have to do with event-based retention. Event-based retention is about starting a retention period when a specific event occurs, instead of the moment a document was labeled or created.

[Read more on event-based retention here](https://learn.microsoft.com/microsoft-365/compliance/event-driven-retention?view=o365-worldwide)
