-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage message list

Returns all accessible messages from the user's Viva Engage network

## Usage

```sh
m365 viva engage message list [options]
```

## Options

```md definition-list
`--olderThanId [olderThanId]`
: Returns messages older than the message ID specified as a numeric string

`--threaded`
: Will only return the thread starter (first message) for each thread. This parameter is intended for apps which need to display message threads collapsed

`--feedType [feedType]`
: Returns messages from a specific feed. Available options: `All`, `Top`, `My`, `Following`, `Sent`, `Private`, `Received`. Default `All`

`--groupId [groupId]`
: Returns the messages from a specific group

`--threadId [threadId]`
: Returns the messages from a specific thread

`--limit [limit]`
: Limits the messages returned
```

<Global />

## Remarks

:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::

Feed types

- All: Corresponds to “All” conversations in the Viva Engage web interface
- Top: The algorithmic feed for the user that corresponds to "Top" conversations. The Top conversations feed is the feed currently shown in the Viva Engage mobile apps
- My: The user’s feed, based on the selection they have made between "Following" and "Top" conversations
- Following: The "Following" feed which is conversations involving people and topics that the user is following
- Sent: All messages sent by the user
- Private: Private messages received by the user
- Received: All messages received by the user

## Examples

Returns all Viva Engage network messages

```sh
m365 viva engage message list
```

Returns all Viva Engage network messages older than the message ID 5611239081

```sh
m365 viva engage message list --olderThanId 5611239081
```

Returns all Viva Engage network thread starter (first message) for each thread

```sh
m365 viva engage message list --threaded
```

Returns the first 10 Viva Engage network messages

```sh
m365 viva engage message list --limit 10
```

Returns the first 10 Viva Engage network messages from the Viva Engage group 312891231

```sh
m365 viva engage message list --groupId 312891231 --limit 10
```

Returns the first 10 Viva Engage network messages from thread 5611239081

```sh
m365 viva engage message list --threadId 5611239081 --limit 10
```

Returns the first 20 Viva Engage message from the sent feed of the user

```sh
m365 viva engage message list --feedType Sent --limit 20
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": 2000337749565441,
      "sender_id": 36425097217,
      "delegate_id": null,
      "replied_to_id": null,
      "created_at": "2022/11/11 20:59:10 +0000",
      "network_id": 5897756673,
      "message_type": "update",
      "sender_type": "user",
      "url": "https://www.yammer.com/api/v1/messages/2000336575053825",
      "web_url": "https://www.yammer.com/contoso.onmicrosoft.com/messages/2000336575053825",
      "group_id": 31158067201,
      "body": {
        "parsed": "Hello everyone!",
        "plain": "Hello everyone!",
        "rich": "Hello everyone!"
      },
      "thread_id": 2000337749565441,
      "client_type": "O365 Api Auth",
      "client_url": "https://api.yammer.com",
      "system_message": false,
      "direct_message": false,
      "chat_client_sequence": null,
      "language": "no",
      "notified_user_ids": [],
      "privacy": "public",
      "attachments": [],
      "liked_by": {
        "count": 0,
        "names": []
      },
      "supplemental_reply": false,
      "content_excerpt": "Hello everyone!",
      "group_created_id": 31158067201,
      "shortBody": "Hello everyone!"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                replied_to_id  thread_id         group_id     shortBody
  ----------------  -------------  ----------------  -----------  ---------------
  2000337749565441  null           2000337749565441  31158067201  Hello everyone!
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,replied_to_id,thread_id,group_id,shortBody
  2000337749565441,,2000337749565441,31158067201,Hello everyone!
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # viva engage message list --limit "1" --feedType "All"

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
  language | no
  privacy | public
  supplemental\_reply | false
  content\_excerpt | Hello everyone!
  group\_created\_id | 123412865024
  shortBody | Hello everyone!
  ```

  </TabItem>
</Tabs>
