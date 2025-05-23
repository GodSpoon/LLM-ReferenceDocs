-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo eventreceiver get

Retrieves specific event receiver for the specified web, site or list by event receiver name or id.

## Usage

```sh
m365 spo eventreceiver get [options]
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

`-n, --name [name]`
: The name of the event receiver to retrieve. Specify either `name` or `id` but not both.

`-i, --id [id]`
: The id of the event receiver to retrieve. Specify either `name` or `id` but not both.

`-s, --scope [scope]`
: The scope of which to retrieve the event receivers. Can be either `site` or `web`. Defaults to `web`. Only applicable when not specifying any of the list properties.
```

<Global />

## Examples

Retrieve an event receiver with the given name in the specified site.

```sh
m365 spo eventreceiver get --webUrl https://contoso.sharepoint.com/sites/contoso-sales --name 'PnP Test Receiver'
```

Retrieve an event receiver with the given id in the specified site.

```sh
m365 spo eventreceiver get --webUrl https://contoso.sharepoint.com/sites/contoso-sales --scope site --id c5a6444a-9c7f-4a0d-9e29-fc6fe30e34ec
```

Retrieve an event receiver with the given name for a list with the given title in the specified site.

```sh
m365 spo eventreceiver get --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listTitle Events --name 'PnP Test Receiver'
```

Retrieve an event receiver with the given id for a list with the given ID in the specified site.

```sh
m365 spo eventreceiver get --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listId '202b8199-b9de-43fd-9737-7f213f51c991' --id c5a6444a-9c7f-4a0d-9e29-fc6fe30e34ec
```

Retrieve an event receiver with the given name for a list with the given url in the specified site.

```sh
m365 spo eventreceiver get --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listUrl '/sites/contoso-sales/lists/Events' --name 'PnP Test Receiver'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
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
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  EventType       : 10204
  ReceiverAssembly: Microsoft.Office.Server.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c
  ReceiverClass   : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ReceiverId      : c5a6444a-9c7f-4a0d-9e29-fc6fe30e34ec
  ReceiverName    : PnP Test Receiver
  ReceiverUrl     : https://northeurope1-0.pushnp.svc.ms/notifications?token=b4c0def2-a5ea-490a-bb85-c2e423b1384b
  SequenceNumber  : 10000
  Synchronization : 2
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ReceiverAssembly,ReceiverClass,ReceiverId,ReceiverName,SequenceNumber,Synchronization,EventType,ReceiverUrl
  "Microsoft.Office.Server.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c",EXAMPLE_SECRET_VALUE_PLACEHOLDER,c5a6444a-9c7f-4a0d-9e29-fc6fe30e34ec,PnP Test Receiver,10000,2,10204,https://northeurope1-0.pushnp.svc.ms/notifications?token=b4c0def2-a5ea-490a-bb85-c2e423b1384b
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo eventreceiver get --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --id "c5a6444a-9c7f-4a0d-9e29-fc6fe30e34ec"

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
