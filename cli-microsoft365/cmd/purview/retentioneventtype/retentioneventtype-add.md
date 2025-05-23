-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# purview retentioneventtype add

Create a retention event type

## Usage

```sh
m365 purview retentioneventtype add [options]
```

## Options

```md definition-list
`-n, --displayName <displayName>`
: The display name of the event type.

`-d, --description [description]`
: A description for the event type.
```

<Global />

## Remarks

:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::

## Examples

Create a retention event type *Contract Expiry*.

```sh
m365 purview retentioneventtype add --displayName 'Contract Expiry' --description 'A retention event type to start a retention period based on the date that a contract expired.'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    {
      "displayName": "Contract Expiry",
      "description": "A retention event type to start a retention period based on the date that a contract expired.",
      "createdDateTime": "2023-01-31T20:33:33Z",
      "lastModifiedDateTime": "2023-01-31T20:33:33Z",
      "id": "f15d2493-7ad2-4185-a3f6-9580542490a0",
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
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  createdBy           : {"user":{"id":null,"displayName":"John Doe"}}
  createdDateTime     : 2023-01-31T20:40:40Z
  description         : A retention event type to start a retention period based on the date that a contract expired.
  displayName         : Contract Expiry
  id                  : 806cb481-4cc6-47c3-af26-26d64f6e7aab
  lastModifiedBy      : {"user":{"id":null,"displayName":"John Doe"}}
  lastModifiedDateTime: 2023-01-31T20:40:40Z
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  displayName,description,createdDateTime,lastModifiedDateTime,id,createdBy,lastModifiedBy
  Contract Expiry,A retention event type to start a retention period based on the date that a contract expired.,2023-01-31T20:53:23Z,2023-01-31T20:53:23Z,b430ae4c-1e26-422f-9544-67df3abfb200,"{""user"":{""id"":null,""displayName"":""John Doe""}}","{""user"":{""id"":null,""displayName"":""John Doe""}}"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # purview retentioneventtype add --displayName "Contract Expiry" --description "A retention event type to start a retention period based on the date that a contract expired."

  Date: 31/01/2023

  ## Contract Expiry (ca0e1f8d-4e42-4a81-be85-022502d70c4e)

  Property | Value
  ---------|-------
  displayName | Contract Expiry
  description | A retention event type to start a retention period based on the date that a contract expired.
  createdDateTime | 2023-01-31T20:55:35Z
  lastModifiedDateTime | 2023-01-31T20:55:35Z
  id | ca0e1f8d-4e42-4a81-be85-022502d70c4e
  ```

  </TabItem>
</Tabs>

## More information

This command is part of a series of commands that have to do with event-based retention. Event-based retention is about starting a retention period when a specific event occurs, instead of the moment a document was labeled or created. [Read more about event-based retention here](https://learn.microsoft.com/microsoft-365/compliance/event-driven-retention?view=o365-worldwide)
