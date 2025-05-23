-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# purview retentionevent get

Get a retention event

## Usage

```sh
m365 purview retentionevent get [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The Id of the retention event.
```

<Global />

## Examples

Get a retention event by id.

```sh
m365 purview retentionevent get --id c37d695e-d581-4ae9-82a0-9364eba4291e
```

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
      "displayName": "Contract xyz expired",
      "description": "The retention period for documents related to Contract xyz started because the contract expired.",
      "eventTriggerDateTime": "2023-02-01T09:16:37Z",
      "lastStatusUpdateDateTime": "2023-02-01T09:21:15Z",
      "createdDateTime": "2023-02-01T09:17:40Z",
      "lastModifiedDateTime": "2023-02-01T09:17:40Z",
      "id": "c37d695e-d581-4ae9-82a0-9364eba4291e",
      "eventQueries": [
          {
              "queryType": "files",
              "query": "1234"
          },
          {
              "queryType": "messages",
              "query": "Terminate"
          }
      ],
      "eventStatus": {
          "error": null,
          "status": "success"
      },
      "eventPropagationResults": [
          {
              "serviceName": "SharePoint",
              "location": null,
              "status": "none",
              "statusInformation": null
          }
      ],
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
  createdDateTime         : 2023-02-01T09:17:40Z
  description             : The retention period for documents related to Contract xyz started because the contract expired.
  displayName             : Contract xyz expired    
  eventTriggerDateTime    : 2023-02-01T09:16:37Z
  id                      : c37d695e-d581-4ae9-82a0-9364eba4291e
  lastModifiedBy          : {"user":{"id":null,"displayName":"John Doe"}}
  lastModifiedDateTime    : 2023-02-01T09:17:40Z
  lastStatusUpdateDateTime: 2023-02-01T09:21:15Z    
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  displayName,description,eventTriggerDateTime,lastStatusUpdateDateTime,createdDateTime,lastModifiedDateTime,id,createdBy,lastModifiedBy
  Contract xyz expired,The retention period for documents related to Contract xyz started because the contract expired.,2023-02-01T09:16:37Z,2023-02-01T09:21:15Z,2023-02-01T09:17:40Z,2023-02-01T09:17:40Z,c37d695e-d581-4ae9-82a0-9364eba4291e,{"user":{"id":null,"displayName":"John Doe"}},{"user":{"id":null,"displayName":"John Doe"}}
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # purview retentionevent get --id "c37d695e-d581-4ae9-82a0-9364eba4291e"

  Date: 2/1/2023

  ## Contract xyz expired (c37d695e-d581-4ae9-82a0-9364eba4291e)

  Property | Value
  ---------|-------
  displayName | Contract xyz expired
  description | The retention period for documents related to Contract xyz started because the contract expired.
  eventTriggerDateTime | 2023-02-01T09:16:37Z
  lastStatusUpdateDateTime: 2023-02-01T09:21:15Z
  createdDateTime | 2023-02-01T09:17:40Z
  lastModifiedDateTime | 2023-02-01T09:17:40Z
  id | c37d695e-d581-4ae9-82a0-9364eba4291e
  ```

  </TabItem>
</Tabs>

## More information

This command is part of a series of commands that have to do with event-based retention. Event-based retention is about starting a retention period when a specific event occurs, instead of the moment a document was labeled or created.

[Read more on event-based retention here](https://learn.microsoft.com/microsoft-365/compliance/event-driven-retention?view=o365-worldwide)
