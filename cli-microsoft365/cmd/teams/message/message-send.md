-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams message send

Sends a message to a channel in a Microsoft Teams team

## Usage

```sh
m365 teams message send [options]
```

## Options

```md definition-list
`-t, --teamId <teamId>`
: The ID of the team where the channel is located.

`-c, --channelId <channelId>`
: The ID of the channel.

`-m, --message <message>`
: The message to send.
```

<Global />

## Remarks

You can only send a message to a channel in a Microsoft Teams team if you are a member of that team or channel.

## Examples

Send a message to a specified channel in a Microsoft Teams team.

```sh
m365 teams message send --teamId 5f5d7b71-1161-44d8-bcc1-3da710eb4171 --channelId 19:88f7e66a8dfe42be92db19505ae912a8@thread.skype --message "Hello World!"
```

Send an HTML formatted message to a specified channel in a Microsoft Teams team.

```sh
m365 teams message send --teamId 5f5d7b71-1161-44d8-bcc1-3da710eb4171 --channelId 19:88f7e66a8dfe42be92db19505ae912a8@thread.skype --message "Hello <b>World</b>!"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "1674320428077",
    "replyToId": null,
    "etag": "1674320428077",
    "messageType": "message",
    "createdDateTime": "2023-01-21T17:00:28.077Z",
    "lastModifiedDateTime": "2023-01-21T17:00:28.077Z",
    "lastEditedDateTime": null,
    "deletedDateTime": null,
    "subject": null,
    "summary": null,
    "chatId": null,
    "importance": "normal",
    "locale": "en-us",
    "webUrl": "https://teams.microsoft.com/l/message/19%3Aeeafac000f844fcc8d98fdbc4ca17570%40thread.skype/1674320428077?groupId=6fb1231b-b2ad-4a81-b5d8-ed40ec7b3cd2&tenantId=189eb7cd-b689-4d93-88d8-8b8d30cd8847&createdTime=1674320428077&parentMessageId=1674320428077",
    "policyViolation": null,
    "eventDetail": null,
    "from": {
      "application": null,
      "device": null,
      "user": {
        "id": "b2091e18-7882-4efe-b7d1-90703f5a5c65",
        "displayName": "John Doe",
        "userIdentityType": "aadUser"
      }
    },
    "body": {
      "contentType": "html",
      "content": "<h2>Header</h2><ol><li>item 1</li><li>item 2</li><li>item 3</li></ol><p>This is <b>bold</b> text</p>"
    },
    "channelIdentity": {
      "teamId": "6fb1231b-b2ad-4a81-b5d8-ed40ec7b3cd2",
      "channelId": "19:eeafac000f844fcc8d98fdbc4ca17570@thread.skype"
    },
    "attachments": [],
    "mentions": [],
    "reactions": []
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  attachments         : []
  body                : {"contentType":"html","content":"<h2>Header</h2><ol><li>item 1</li><li>item 2</li><li>item 3</li></ol><p>This is <b>bold</b> text</p>"}
  channelIdentity     : {"teamId":"6fb1231b-b2ad-4a81-b5d8-ed40ec7b3cd2","channelId":"19:eeafac000f844fcc8d98fdbc4ca17570@thread.skype"}
  chatId              : null
  createdDateTime     : 2023-01-21T17:04:52.284Z
  deletedDateTime     : null
  etag                : 1674320692284
  eventDetail         : null
  from                : {"application":null,"device":null,"user":{"id":"b2091e18-7882-4efe-b7d1-90703f5a5c65","displayName":"John Doe","userIdentityType":"aadUser"}}
  id                  : 1674320692284
  importance          : normal
  lastEditedDateTime  : null
  lastModifiedDateTime: 2023-01-21T17:04:52.284Z
  locale              : en-us
  mentions            : []
  messageType         : message
  policyViolation     : null
  reactions           : []
  replyToId           : null
  subject             : null
  summary             : null
  webUrl              : https://teams.microsoft.com/l/message/19%3Aeeafac000f844fcc8d98fdbc4ca17570%40thread.skype/1674320428077?groupId=6fb1231b-b2ad-4a81-b5d8-ed40ec7b3cd2&tenantId=189eb7cd-b689-4d93-88d8-8b8d30cd8847&createdTime=1674320428077&parentMessageId=1674320428077
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,replyToId,etag,messageType,createdDateTime,lastModifiedDateTime,lastEditedDateTime,deletedDateTime,subject,summary,chatId,importance,locale,webUrl,policyViolation,eventDetail,from,body,channelIdentity,attachments,mentions,reactions
  1674320748808,,1674320748808,message,2023-01-21T17:05:48.808Z,2023-01-21T17:05:48.808Z,,,,,,normal,en-us,https://teams.microsoft.com/l/message/19%3Aeeafac000f844fcc8d98fdbc4ca17570%40thread.skype/1674320428077?groupId=6fb1231b-b2ad-4a81-b5d8-ed40ec7b3cd2&tenantId=189eb7cd-b689-4d93-88d8-8b8d30cd8847&createdTime=1674320428077&parentMessageId=1674320428077,,,"{""application"":null,""device"":null,""user"":{""id"":""b2091e18-7882-4efe-b7d1-90703f5a5c65"",""displayName"":""John Doe"",""userIdentityType"":""aadUser""}}","{""contentType"":""html"",""content"":""<h2>Header</h2><ol><li>item 1</li><li>item 2</li><li>item 3</li></ol><p>This is <b>bold</b> text</p>""}","{""teamId"":""6fb1231b-b2ad-4a81-b5d8-ed40ec7b3cd2"",""channelId"":""19:eeafac000f844fcc8d98fdbc4ca17570@thread.skype""}",[],[],[]
  ```

  </TabItem>
</Tabs>
