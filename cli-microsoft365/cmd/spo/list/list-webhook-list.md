-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo list webhook list

Lists all webhooks for the specified list

## Usage

```sh
m365 spo list webhook list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list is located.

`-i, --listId [listId]`
: ID of the list. Specify either `listTitle`, `listId` or `listUrl`.

`-t, --listTitle [listTitle]`
: Title of the list. Specify either `listTitle`, `listId` or `listUrl`.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listTitle`, `listId` or `listUrl`.
```

<Global />

## Examples

List all webhooks for a list with a specific ID in a specific site

```sh
m365 spo list webhook list --webUrl https://contoso.sharepoint.com/sites/project-x --listId 0cd891ef-afce-4e55-b836-fce03286cccf
```

List all webhooks for a list with a specific title in a specific site

```sh
m365 spo list webhook list --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle Documents
```

List all webhooks for a list with a specific URL in a specific site

```sh
m365 spo list webhook list --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl '/sites/project-x/Documents'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "clientState": "system-managed:8082D436-D8DA-458D-96AD-34C902B73F37",
      "expirationDateTime": "2022-11-16T20:25:12.2735056Z",
      "id": "b8838bbb-9ddb-44fb-9016-0aacb9e02b77",
      "notificationUrl": "https://northeurope1-0.pushnp.svc.ms/notifications?token=1e263e06-4bea-4da1-9f9f-5c8f713eef76",
      "resource": "97d19285-b8a6-4c7f-9c6c-d6b850a6561a",
      "resourceData": null
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  clientState                                          expirationDateTime            id                                    resource
  ---------------------------------------------------  ----------------------------  ------------------------------------  ------------------------------------
  system-managed:8082D436-D8DA-458D-96AD-34C902B73F37  2022-11-16T20:25:12.2735056Z  b8838bbb-9ddb-44fb-9016-0aacb9e02b77  97d19285-b8a6-4c7f-9c6c-d6b850a6561a
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,clientState,expirationDateTime,resource
  b8838bbb-9ddb-44fb-9016-0aacb9e02b77,system-managed:8082D436-D8DA-458D-96AD-34C902B73F37,2022-11-16T20:25:12.2735056Z,97d19285-b8a6-4c7f-9c6c-d6b850a6561a
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo list webhook list --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "Documents"

  Date: 2/20/2023

  ## b8838bbb-9ddb-44fb-9016-0aacb9e02b77

  Property | Value
  ---------|-------
  clientState| system-managed:8082D436-D8DA-458D-96AD-34C902B73F37
  expirationDateTime| 2022-11-16T20:25:12.2735056Z
  id| b8838bbb-9ddb-44fb-9016-0aacb9e02b77
  notificationUrl| https://northeurope1-0.pushnp.svc.ms/notifications?token=1e263e06-4bea-4db1-9f9f-5c8f713eef76
  resource| 97d19285-b8a6-4c7f-9c6c-d6b850a6561a
  resourceData| null
  ```

  </TabItem>
</Tabs>
