-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# purview retentioneventtype list

Get a list of retention event types

## Usage

```sh
m365 purview retentioneventtype list [options]
```

## Options

<Global />

## Remarks

:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::

## Examples

Get a list of retention event types.

```sh
m365 purview retentioneventtype list
```

## Response


<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "displayName": "Contract Expiry",
      "description": "",
      "createdDateTime": "2023-02-02T15:47:54Z",
      "lastModifiedDateTime": "2023-02-02T15:47:54Z",
      "id": "81fa91bd-66cd-4c6c-b0cb-71f37210dc74",
      "createdBy": {
        "user": {
          "id": "36155f4e-bdbd-4101-ba20-5e78f5fba9a9",
          "displayName": null
        }
      },
      "lastModifiedBy": {
        "user": {
          "id": "36155f4e-bdbd-4101-ba20-5e78f5fba9a9",
          "displayName": null
        }
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    displayName            createdDateTime
  ------------------------------------  ---------------------  --------------------
  81fa91bd-66cd-4c6c-b0cb-71f37210dc74  Contract Expiry  2023-02-02T15:47:54Z
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,createdDateTime
  81fa91bd-66cd-4c6c-b0cb-71f37210dc74,Contract Expiry,2023-02-02T15:47:54Z
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # purview retentioneventtype list

  Date: 8/2/2023

  ## Contract Expiry (81fa91bd-66cd-4c6c-b0cb-71f37210dc74)

  Property | Value
  ---------|-------
  displayName | Contract Expiry
  description | null
  createdDateTime | 2023-02-02T15:47:54Z
  lastModifiedDateTime | 2023-02-02T15:47:54Z
  id | 81fa91bd-66cd-4c6c-b0cb-71f37210dc74
  ```

  </TabItem>
</Tabs>

## More information

This command is part of a series of commands that have to do with event-based retention. Event-based retention is about starting a retention period when a specific event occurs, instead of the moment a document was labeled or created.
