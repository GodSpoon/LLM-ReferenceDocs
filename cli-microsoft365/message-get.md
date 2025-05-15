<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# outlook message get

Retrieves specified message

## Usage

```sh
m365 outlook message get [options]
```

## Options

```md definition-list
`-i, --id <id>`
: ID of the message.

`--userId [userId]`
: ID of the user from which to retrieve the message. Specify either `userId` or `userName`, but not both. This option is required when using application permissions.

`--userName [userName]`
: UPN of the user from which to retrieve the message Specify either `userId` or `userName`, but not both. This option is required when using application permissions.
```

<Global />

## Examples

Get a specific message using delegated permissions.

```sh
m365 outlook message get --id EXAMPLE_SECRET_VALUE_PLACEHOLDER=
```

Get a specific message using delegated permissions from a shared mailbox.

```sh
m365 outlook message get --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userName sharedmailbox@tenant.com
```

Get a specific message from a specific user retrieved by user ID using application permissions.

```sh
m365 outlook message get --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userId 6799fd1a-723b-4eb7-8e52-41ae530274ca
```

Get a specific message from a specific user retrieved by user principal name using application permissions.

```sh
m365 outlook message get --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userName user@tenant.com
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
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
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  bccRecipients             : []
  body                      : {"contentType":"html","content":"<html><head>
<meta http-equiv=\"Content-Type\" content=\"text/html; charset=utf-8\"><style type=\"text/css\" style=\"display:none\">
<!--
p
	{margin-top:0;
	margin-bottom:0}
-->
</style></head><body dir=\"ltr\"><div class=\"elementToProof ContentPasted0\" style=\"font-family:Calibri,Arial,Helvetica,sans-serif; font-size:12pt; color:rgb(0,0,0); background-color:rgb(255,255,255)\">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis vel diam gravida, auctor mauris nec, posuere tellus. Vivamus placerat, nunc ac cursus feugiat, arcu tellus mattis nisl, id cursus nisl lectus eu lacus. Praesent malesuada ut orci vitae viverra. Suspendisse cursus turpis vel urna volutpat congue. Etiam auctor nec nulla sed suscipit. Vestibulum rhoncus quis mi ac faucibus. Curabitur eget eleifend felis. Vestibulum ut dolor non elit molestie ornare. <br></div></body></html>"}
  bodyPreview               : Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis vel diam gravida, auctor mauris nec, posuere tellus. Vivamus placerat, nunc ac cursus feugiat, arcu tellus mattis nisl, id cursus nisl lectus eu lacus. Praesent malesuada ut orci vitae viverra.
  categories                : []
  ccRecipients              : []
  changeKey                 : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  conversationId            : EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  conversationIndex         : AQHZMbuNl+8arvtgfEm9E3vf5CK5XA==
  createdDateTime           : 2023-01-26T19:22:44Z
  flag                      : {"flagStatus":"notFlagged"}
  from                      : {"emailAddress":{"name":"John Doe","address":"john.doe@contoso.com"}}
  hasAttachments            : true
  id                        : EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  importance                : normal
  inferenceClassification   : focused
  internetMessageId         : <HE1P190MB032953D4D9C86FCEF5FFA8C4CECF9@HE1P190MB0329.EURP190.PROD.OUTLOOK.COM>
  isDeliveryReceiptRequested: false
  isDraft                   : false
  isRead                    : false
  isReadReceiptRequested    : false
  lastModifiedDateTime      : 2023-01-26T19:22:46Z
  parentFolderId            : EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  receivedDateTime          : 2023-01-26T19:22:45Z
  replyTo                   : []
  sender                    : {"emailAddress":{"name":"John Doe","address":"john.doe@contoso.com"}}
  sentDateTime              : 2023-01-26T19:22:42Z
  subject                   : Lorem ipsum
  toRecipients              : [{"emailAddress":{"name":"Megan Bowen","address":"megan.bowen@contoso.com"}}]
  webLink                   : https://outlook.office365.com/owa/?ItemID=EXAMPLE_SECRET_VALUE_PLACEHOLDER%EXAMPLE_SECRET_VALUE_PLACEHOLDER%3D&exvsurl=1&viewmodel=ReadMessageItem
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,createdDateTime,lastModifiedDateTime,changeKey,categories,receivedDateTime,sentDateTime,hasAttachments,internetMessageId,subject,bodyPreview,importance,parentFolderId,conversationId,conversationIndex,isDeliveryReceiptRequested,isReadReceiptRequested,isRead,isDraft,webLink,inferenceClassification,body,sender,from,toRecipients,ccRecipients,bccRecipients,replyTo,flag
  EXAMPLE_SECRET_VALUE_PLACEHOLDER=,2023-01-26T19:22:44Z,2023-01-26T19:22:46Z,EXAMPLE_SECRET_VALUE_PLACEHOLDER,[],2023-01-26T19:22:45Z,2023-01-26T19:22:42Z,1,<HE1P190MB032953D4D9C86FCEF5FFA8C4CECF9@HE1P190MB0329.EURP190.PROD.OUTLOOK.COM>,Lorem ipsum,"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis vel diam gravida, auctor mauris nec, posuere tellus. Vivamus placerat, nunc ac cursus feugiat, arcu tellus mattis nisl, id cursus nisl lectus eu lacus. Praesent malesuada ut orci vitae viverra.",normal,EXAMPLE_SECRET_VALUE_PLACEHOLDER=,EXAMPLE_SECRET_VALUE_PLACEHOLDER=,AQHZMbuNl+8arvtgfEm9E3vf5CK5XA==,,,,,https://outlook.office365.com/owa/?ItemID=EXAMPLE_SECRET_VALUE_PLACEHOLDER%EXAMPLE_SECRET_VALUE_PLACEHOLDER%3D&exvsurl=1&viewmodel=ReadMessageItem,focused,"{""contentType"":""html"",""content"":""<html><head>
<meta http-equiv=\""Content-Type\"" content=\""text/html; charset=utf-8\""><style type=\""text/css\"" style=\""display:none\"">
<!--
p
	{margin-top:0;
	margin-bottom:0}
-->
</style></head><body dir=\""ltr\""><div class=\""elementToProof ContentPasted0\"" style=\""font-family:Calibri,Arial,Helvetica,sans-serif; font-size:12pt; color:rgb(0,0,0); background-color:rgb(255,255,255)\"">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis vel diam gravida, auctor mauris nec, posuere tellus. Vivamus placerat, nunc ac cursus feugiat, arcu tellus mattis nisl, id cursus nisl lectus eu lacus. Praesent malesuada ut orci vitae viverra. Suspendisse cursus turpis vel urna volutpat congue. Etiam auctor nec nulla sed suscipit. Vestibulum rhoncus quis mi ac faucibus. Curabitur eget eleifend felis. Vestibulum ut dolor non elit molestie ornare. <br></div></body></html>""}","{""emailAddress"":{""name"":""John Doe"",""address"":""john.doe@contoso.com""}}","{""emailAddress"":{""name"":""John Doe"",""address"":""john.doe@contoso.com""}}","[{""emailAddress"":{""name"":""Megan Bowen"",""address"":""megan.bowen@contoso.com""}}]",[],[],[],"{""flagStatus"":""notFlagged""}"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # outlook message get --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER="

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
