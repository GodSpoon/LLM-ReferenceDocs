-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo eventreceiver list

Retrieves event receivers for the specified web, site or list.

## Usage

```sh
m365 spo eventreceiver list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the web for which to retrieve the event receivers.

`--listTitle [listTitle]`
: The title of the list for which to retrieve the event receivers, _if the event receivers should be retrieved from a list_. Specify either `listTitle`, `listId` or `listUrl`.

`--listId [listId]`
: The id of the list for which to retrieve the event receivers, _if the event receivers should be retrieved from a list_. Specify either `listTitle`, `listId` or `listUrl`.

`--listUrl [listUrl]`
: The url of the list for which to retrieve the event receivers, _if the event receivers should be retrieved from a list_. Specify either `listTitle`, `listId` or `listUrl`.

`-s, --scope [scope]`
: The scope of which to retrieve the Event Receivers. Can be either "site" or "web". Defaults to "web". Only applicable when not specifying any of the list properties.
```

<Global />

## Examples

Retrieves event receivers in the specified site.

```sh
m365 spo eventreceiver list --webUrl https://contoso.sharepoint.com/sites/contoso-sales
```

Retrieves event receivers in the specified site.

```sh
m365 spo eventreceiver list --webUrl https://contoso.sharepoint.com/sites/contoso-sales --scope site
```

Retrieves event receivers for list with given title in the specified site.

```sh
m365 spo eventreceiver list --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listTitle Events
```

Retrieves event receivers for list with given ID in the specified site.

```sh
m365 spo eventreceiver list --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listId '202b8199-b9de-43fd-9737-7f213f51c991'
```

Retrieves event receivers for list with given url in the specified site.

```sh
m365 spo eventreceiver list --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listUrl '/sites/contoso-sales/lists/Events'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
    "ReceiverAssembly": "Microsoft.Office.Server.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c",
    "ReceiverClass": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "ReceiverId": "c5a6444a-9c7f-4a0d-9e29-fc6fe30e34ec",
    "ReceiverName": "PnP Test Receiver",
    "SequenceNumber": 10000,
    "Synchronization": 2,
    "EventType": 10204,
    "ReceiverUrl": "https://northeurope1-0.pushnp.svc.ms/notifications?token=b4c0def2-a5ea-490a-bb85-c2e423b1384b"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  ReceiverId                            ReceiverName
  ------------------------------------  -------------------------------------------------------------------------
  c5a6444a-9c7f-4a0d-9e29-fc6fe30e34ec  PnP Test Receiver
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ReceiverAssembly,ReceiverClass,ReceiverId,ReceiverName,SequenceNumber,Synchronization,EventType
  "Microsoft.Office.Server.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c",EXAMPLE_SECRET_VALUE_PLACEHOLDER,c5a6444a-9c7f-4a0d-9e29-fc6fe30e34ec,PnP Test Receiver,10000,2,10204
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo eventreceiver list --webUrl "https://contoso.sharepoint.com/sites/contoso-sales"

  Date: 10/2/2023

  Property | Value
  ---------|-------
  ReceiverAssembly | Microsoft.Office.Server.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c
  ReceiverClass | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ReceiverId | c5a6444a-9c7f-4a0d-9e29-fc6fe30e34ec
  ReceiverName | PnP Test Receiver
  SequenceNumber | 10000
  Synchronization | 2
  EventType | 10204
  ```

  </TabItem>
</Tabs>
