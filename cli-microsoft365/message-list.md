<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# outlook message list

Gets all mail messages from the specified folder

## Usage

```sh
m365 outlook message list [options]
```

## Options

```md definition-list
`--folderName [folderName]`
: Name of the folder from which to list messages.

`--folderId [folderId]`
: ID of the folder from which to list messages.

`--startTime [startTime]`
: Time indicating the inclusive start of a time range when the message was received. This should be defined as a valid ISO 8601 string (2021-12-16T18:28:48.6964197Z).

`--endTime [endTime]`
: Time indicating the exclusive end of a time range when the message was received. This should be defined as a valid ISO 8601 string (2021-12-16T18:28:48.6964197Z).

`--userId [userId]`
: The Microsoft Entra user ID. Specify either `userId` or `userName`, not both. This option is required when using application permissions.

`--userName [userName]`
: User principal name of the user. Specify either `userId` or `userName`, not both. This option is required when using application permissions.
```

<Global />

## Examples

List all messages from a folder with the specified name received within a specific time frame.

```sh
m365 outlook message list --folderName Archive --startTime 2023-12-16T18:28:48.6964197Z --endTime 2024-02-01
```

List all messages from a specific folder of a user specified by ID.

```sh
m365 outlook message list --folderId EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userId 48d31887-5fad-4d73-a9f5-3c356e68a038
```

List all messages from a folder of a user specified by UPN.

```sh
m365 outlook message list --folderName inbox --userName john@contoso.com
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER=",
      "createdDateTime": "2023-01-26T19:22:44Z",
      "lastModifiedDateTime": "2023-01-26T19:22:46Z",
      "changeKey": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "categories": [],
      "receivedDateTime": "2023-01-26T19:22:45Z",
      "sentDateTime": "2023-01-26T19:22:42Z",
      "hasAttachments": true,
      "internetMessageId": "<HE1P190MB032953D4D9C86FCEF5FFA8C4CECF9@HE1P190MB0329.EURP190.PROD.OUTLOOK.COM>",
      "subject": "Lorem ipsum",
      "bodyPreview": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis vel diam gravida, auctor mauris nec, posuere tellus. Vivamus placerat, nunc ac cursus feugiat, arcu tellus mattis nisl, id cursus nisl lectus eu lacus. Praesent malesuada ut orci vitae viverra.",
      "importance": "normal",
      "parentFolderId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER=",
      "conversationId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER=",
      "conversationIndex": "AQHZMbuNl+8arvtgfEm9E3vf5CK5XA==",
      "isDeliveryReceiptRequested": false,
      "isReadReceiptRequested": false,
      "isRead": false,
      "isDraft": false,
      "webLink": "https://outlook.office365.com/owa/?ItemID=EXAMPLE_SECRET_VALUE_PLACEHOLDER%EXAMPLE_SECRET_VALUE_PLACEHOLDER%3D&exvsurl=1&viewmodel=ReadMessageItem",
      "inferenceClassification": "focused",
      "body": {
        "contentType": "html",
        "content": "<html><head>\
<meta http-equiv=\"Content-Type\" content=\"text/html; charset=utf-8\"><style type=\"text/css\" style=\"display:none\">\
<!--\
p\
	{margin-top:0;\
	margin-bottom:0}\
-->\
</style></head><body dir=\"ltr\"><div class=\"elementToProof ContentPasted0\" style=\"font-family:Calibri,Arial,Helvetica,sans-serif; font-size:12pt; color:rgb(0,0,0); background-color:rgb(255,255,255)\">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis vel diam gravida, auctor mauris nec, posuere tellus. Vivamus placerat, nunc ac cursus feugiat, arcu tellus mattis nisl, id cursus nisl lectus eu lacus. Praesent malesuada ut orci vitae viverra. Suspendisse cursus turpis vel urna volutpat congue. Etiam auctor nec nulla sed suscipit. Vestibulum rhoncus quis mi ac faucibus. Curabitur eget eleifend felis. Vestibulum ut dolor non elit molestie ornare. <br></div></body></html>"
      },
      "sender": {
        "emailAddress": {
          "name": "John Doe",
          "address": "john.doe@contoso.com"
        }
      },
      "from": {
        "emailAddress": {
          "name": "John Doe",
          "address": "john.doe@contoso.com"
        }
      },
      "toRecipients": [
        {
          "emailAddress": {
            "name": "Megan Bowen",
            "address": "megan.bowen@contoso.com"
          }
        }
      ],
      "ccRecipients": [],
      "bccRecipients": [],
      "replyTo": [],
      "flag": {
        "flagStatus": "notFlagged"
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  subject      receivedDateTime    
  -----------  --------------------
  Lorem ipsum  2023-01-26T19:22:45Z
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  subject,receivedDateTime
  Lorem ipsum,2023-01-26T19:22:45Z
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # outlook message list --folderName "inbox"

  Date: 4/2/2023

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER=

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  createdDateTime | 2023-01-26T19:22:44Z
  lastModifiedDateTime | 2023-01-26T19:22:46Z
  changeKey | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  receivedDateTime | 2023-01-26T19:22:45Z
  sentDateTime | 2023-01-26T19:22:42Z
  hasAttachments | true
  internetMessageId | <HE1P190MB032953D4D9C86FCEF5FFA8C4CECF9@HE1P190MB0329.EURP190.PROD.OUTLOOK.COM>
  subject | Lorem ipsum
  bodyPreview | Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis vel diam gravida, auctor mauris nec, posuere tellus. Vivamus placerat, nunc ac cursus feugiat, arcu tellus mattis nisl, id cursus nisl lectus eu lacus. Praesent malesuada ut orci vitae viverra.
  importance | normal
  parentFolderId | EXAMPLE_SECRET_VALUE_PLACEHOLDER\_VgXAQAhebtol4HnTZCmNsr9Gnh6AAAAAAEMAAA=
  conversationId | EXAMPLE_SECRET_VALUE_PLACEHOLDER\_QiuVw=
  conversationIndex | AQHZMbuNl+8arvtgfEm9E3vf5CK5XA==
  isDeliveryReceiptRequested | false
  isReadReceiptRequested | false
  isRead | true
  isDraft | false
  webLink | https://outlook.office365.com/owa/?ItemID=EXAMPLE_SECRET_VALUE_PLACEHOLDER%EXAMPLE_SECRET_VALUE_PLACEHOLDER%3D&exvsurl=1&viewmodel=ReadMessageItem
  inferenceClassification | focused
  ```

  </TabItem>
</Tabs>

## More information

- Well-known folder names: [https://learn.microsoft.com/graph/api/resources/mailfolder?view=graph-rest-1.0](https://learn.microsoft.com/graph/api/resources/mailfolder?view=graph-rest-1.0)
