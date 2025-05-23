-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo list webhook add

Adds a new webhook to the specified list

## Usage

```sh
m365 spo list webhook add [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list is located.

`-l, --listId [listId]`
: ID of the list. Specify either `listTitle`, `listId` or `listUrl`.

`-t, --listTitle [listTitle]`
: Title of the list. Specify either `listTitle`, `listId` or `listUrl`.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listTitle`, `listId` or `listUrl`.

`-n, --notificationUrl <notificationUrl>`
: The notification URL.

`-e, --expirationDateTime [expirationDateTime]`
: The expiration date. Will be set to max (6 months from today) if not provided.

`-c, --clientState [clientState]`
: A client state information that will be passed through notifications.
```

<Global />

## Examples

Add a web hook to the list retrieved by Title located in a specific site with a specific notification url and the default expiration date

```sh
m365 spo list webhook add --webUrl https://contoso.sharepoint.com/sites/ninja --listTitle Documents --notificationUrl https://contoso-funcions.azurewebsites.net/webhook
```

Add a web hook to the list retrieved by URL located in a specific site with a specific notification url and a specific expiration date

```sh
m365 spo list webhook add --webUrl https://contoso.sharepoint.com/sites/ninja --listUrl '/sites/ninja/Documents' --notificationUrl https://contoso-funcions.azurewebsites.net/webhook --expirationDateTime 2019-01-21
```

Add a web hook to the list retrieved by ID located in a specific site with a specific notification url, a specific expiration date and a client state


```sh
m365 spo list webhook add --webUrl https://contoso.sharepoint.com/sites/ninja --listId '3d6aefa0-f438-4789-b0cd-6e865f5d65b5' --notificationUrl https://contoso-funcions.azurewebsites.net/webhook --expirationDateTime '2019-03-02T18:15' --clientState "Hello State!"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "clientState": "random client state",
    "expirationDateTime": "2019-05-29T23:00:00.000Z",
    "id": "ef69c37d-cb0e-46d9-9758-5ebdeffd6959",
    "notificationUrl": "https://contoso-funcions.azurewebsites.net/webhook",
    "resource": "0987cfd9-f02c-479b-9fb4-3f0550462848",
    "resourceData": null
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  clientState       : random client state
  expirationDateTime: 2019-05-29T23:00:00.000Z
  id                : ef69c37d-cb0e-46d9-9758-5ebdeffd6959
  notificationUrl   : https://contoso-funcions.azurewebsites.net/webhook
  resource          : 0987cfd9-f02c-479b-9fb4-3f0550462848
  resourceData      : null
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  clientState,expirationDateTime,id,notificationUrl,resource,resourceData
  random client state,2019-05-29T23:00:00.000Z,ef69c37d-cb0e-46d9-9758-5ebdeffd6959,https://contoso-funcions.azurewebsites.net/webhook,0987cfd9-f02c-479b-9fb4-3f0550462848,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo list webhook add --webUrl "https://contoso.sharepoint.com/sites/ninja" --listUrl "/sites/ninja/Documents" --notificationUrl "https://contoso-funcions.azurewebsites.net/webhook" --expirationDateTime "2019-01-21"

  Date: 2/20/2023

  ## ef69c37d-cb0e-46d9-9758-5ebdeffd6959

  Property | Value
  ---------|-------
  clientState | random client state
  expirationDateTime | 2019-05-29T23:00:00.000Z
  id | ef69c37d-cb0e-46d9-9758-5ebdeffd6959
  notificationUrl | https://contoso-funcions.azurewebsites.net/webhook
  resource | 0987cfd9-f02c-479b-9fb4-3f0550462848
  resourceData | null
  ```

  </TabItem>
</Tabs>
