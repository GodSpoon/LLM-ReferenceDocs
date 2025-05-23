-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage message add

Posts a Viva Engage network message on behalf of the current user

## Usage

```sh
m365 viva engage message add [options]
```

## Options

```md definition-list
`-b, --body <body>`
: The text of the message body.

`--groupId [groupId]`
: Post the message to this group, specified by ID. If this is set then the networkId is inferred from it. You must either specify `groupId`, `repliedToId`, or `directToUserIds` to send the message.

`-r, --repliedToId [repliedToId]`
: The message ID this message is in reply to. If this is set then groupId and networkId are inferred from it. You must either specify `groupId`, `repliedToId`, or `directToUserIds` to send the message.

`-d, --directToUserIds [directToUserIds]`
: Send a private message to one or more users, specified by ID. Alternatively, you can use the Viva Engage network e-mail addresses instead of the IDs. You must either specify `groupId`, `repliedToId`, or `directToUserIds` to send the message.

`--networkId [networkId]`
: Specify the network to post a message.
```

<Global />

## Remarks

:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::

## Examples

Replies to a message with the ID 1231231231.

```sh
m365 viva engage message add --body "Hello everyone!" --repliedToId 1231231231
```

Sends a private conversation to the user with the ID 1231231231.

```sh
m365 viva engage message add --body "Hello everyone!" --directToUserIds 1231231231
```

Sends a private conversation to multiple users by ID.

```sh
m365 viva engage message add --body "Hello everyone!" --directToUserIds "1231231231,1121312"
```

Sends a private conversation to the user with several e-mail addresses.

```sh
m365 viva engage message add --body "Hello everyone!" --directToUserIds "pl@nubo.eu,sc@nubo.eu"
```

Posts a message to the group with the ID 12312312312.

```sh
m365 viva engage message add --body "Hello everyone!" --groupId 12312312312
```

Posts a message to the group with the ID 12312312312 in the network 11112312.

```sh
m365 viva engage message add --body "Hello everyone!" --groupId 12312312312 --networkId 11112312
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": 2000337346863105,
    "sender_id": 36425097217,
    "delegate_id": null,
    "replied_to_id": null,
    "created_at": "2022/11/11 20:59:56 +0000",
    "network_id": 5897756673,
    "message_type": "update",
    "sender_type": "user",
    "url": "https://www.yammer.com/api/v1/messages/2000337346863105",
    "web_url": "https://www.yammer.com/contoso.onmicrosoft.com/messages/2000337346863105",
    "group_id": 31158067201,
    "body": {
      "parsed": "Hello everyone!",
      "plain": "Hello everyone!",
      "rich": "Hello everyone!"
    },
    "thread_id": 2000337346863105,
    "client_type": "O365 Api Auth",
    "client_url": "https://api.yammer.com",
    "system_message": false,
    "direct_message": false,
    "chat_client_sequence": null,
    "language": null,
    "notified_user_ids": [],
    "privacy": "public",
    "attachments": [],
    "liked_by": {
      "count": 0,
      "names": []
    },
    "supplemental_reply": false,
    "content_excerpt": "Hello everyone!",
    "group_created_id": 31158067201
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  attachments         : []
  body                : {"parsed":"Hello everyone!","plain":"Hello everyone!","rich":"Hello everyone!"}
  chat_client_sequence: null
  client_type         : O365 Api Auth
  client_url          : https://api.yammer.com
  content_excerpt     : Hello everyone!
  created_at          : 2022/11/11 20:59:56 +0000
  delegate_id         : null
  direct_message      : false
  group_created_id    : 31158067201
  group_id            : 31158067201
  id                  : 2000337346863105
  language            : null
  liked_by            : {"count":0,"names":[]}
  message_type        : update
  network_id          : 5897756673
  notified_user_ids   : []
  privacy             : public
  replied_to_id       : null
  sender_id           : 36425097217
  sender_type         : user
  supplemental_reply  : false
  system_message      : false
  thread_id           : 2000337346863105
  url                 : https://www.yammer.com/api/v1/messages/2000337346863105
  web_url             : https://www.yammer.com/contoso.onmicrosoft.com/messages/2000337346863105
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id
  2000337749565441
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # viva engage message add --body "Hello everyone!" --groupId "123412865024"

  Date: 2023-05-16

  ## 2269815632207872

  Property | Value
  ---------|-------
  id | 2269815632207872
  sender\_id | 1842170699776
  created\_at | 2023/05/16 18:42:34 +0000
  published\_at | 2023/05/16 18:42:34 +0000
  network\_id | 98327945216
  message\_type | update
  sender\_type | user
  url | https://www.yammer.com/api/v1/messages/2269815632207872
  web\_url | https://www.yammer.com/contoso.onmicrosoft.com/messages/2269815632207872
  group\_id | 123412865024
  thread\_id | 2269815632207872
  client\_type | O365 Api Auth
  client\_url | https://api.yammer.com
  system\_message | false
  direct\_message | false
  privacy | public
  supplemental\_reply | false
  content\_excerpt | Hello everyone!
  group\_created\_id | 123412865024
  ```

  </TabItem>
</Tabs>
