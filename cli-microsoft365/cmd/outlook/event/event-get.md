-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '../../_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# outlook event get

Retrieve an event from a specific calendar of a user

## Usage

```sh
m365 outlook event get [options]
```

## Options

```md definition-list
`-i, --id <id>`
: ID of the event.

`--userId [userId]`
: ID of the user. Specify either `userId` or `userName`, but not both.

`--userName [userName]`
: UPN of the user. Specify either `userId` or `userName`, but not both.

`--calendarId [calendarId]`
: ID of the calendar. Specify either `calendarId` or `calendarName`, but not both.

`--calendarName [calendarName]`
: Name of the calendar. Specify either `calendarId` or `calendarName`, but not both.

`--timeZone [timeZone]`
: The time zone for the event start and end times. If not specified, the start and end times are in UTC.
```

<Global />

## Permissions

<Tabs>
  <TabItem value="Delegated">

  | Resource        | Permissions                         |
  |-----------------|-------------------------------------|
  | Microsoft Graph | Calendars.ReadBasic, Calendars.Read |

  </TabItem>
  <TabItem value="Application">

  | Resource        | Permissions                         |
  |-----------------|-------------------------------------|
  | Microsoft Graph | Calendars.ReadBasic, Calendars.Read |

  </TabItem>
</Tabs>

:::note

When you specify a value for timeZone, consider the options of the [time zone list](https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/default-time-zones?view=windows-11#time-zones), or [additional time zone list](https://learn.microsoft.com/en-us/graph/api/resources/datetimetimezone?view=graph-rest-1.0#additional-time-zones).

:::

## Examples

Get an event for the current signed-in user from a calendar specified by id.

```sh
m365 outlook event get --id "AAMkAGVmMDEzMTM4L" --userId "@meId" --calendarId "AAMkAGRkZ"
```

Get an event for the user from a calendar specified by id and return event times in Pacific Standard Time time zone.

```sh
m365 outlook event get --id "AAMkAGVmMDEzMTM4L" --userName "john.doe@contoso.com" --calendarId "AAMkAGRkZ" --timeZone 'Pacific Standard Time'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER==",
    "createdDateTime": "2026-04-04T11:03:22.881996Z",
    "lastModifiedDateTime": "2026-04-04T11:05:26.2216557Z",
    "changeKey": "xMBBaLl1lk+dAn8KkjfXKQAGLmp8jA==",
    "categories": [],
    "transactionId": "localevent:93639269-b1b2-d604-5170-283b0e470da5",
    "originalStartTimeZone": "UTC",
    "originalEndTimeZone": "UTC",
    "iCalUId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "uid": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "reminderMinutesBeforeStart": 15,
    "isReminderOn": true,
    "hasAttachments": false,
    "subject": "New Product Regulations Touchpoint",
    "bodyPreview": "New Product Regulations Strategy Online Touchpoint Meeting\
\
You're receiving this message because you're a member of the Engineering group. If you don't want to receive any messages or events from this group, stop following it in your inbox.\
\
________",
    "importance": "normal",
    "sensitivity": "normal",
    "isAllDay": false,
    "isCancelled": false,
    "isOrganizer": true,
    "responseRequested": true,
    "seriesMasterId": null,
    "showAs": "busy",
    "type": "singleInstance",
    "webLink": "https://outlook.office365.com/owa/?itemid=EXAMPLE_SECRET_VALUE_PLACEHOLDER%2F7V4K8g0q%2Badetip1DygcAxMBBaLl1lk%2BdAn8KkjfXKQAAAgENAAAAxMBBaLl1lk%2BdAn8KkjfXKQAGMVCCQQAAAA%3D%3D&exvsurl=1&path=/calendar/item",
    "onlineMeetingUrl": null,
    "isOnlineMeeting": true,
    "onlineMeetingProvider": "teamsForBusiness",
    "allowNewTimeProposals": true,
    "occurrenceId": null,
    "isDraft": false,
    "hideAttendees": false,
    "responseStatus": {
      "response": "organizer",
      "time": "0001-01-01T00:00:00Z"
    },
    "body": {
      "contentType": "html",
      "content": "<html>\
<head>\
<meta http-equiv=\"Content-Type\" content=\"text/html; charset=utf-8\">\
</head>\
<body>\
<div style=\"font-family:Aptos,Aptos_EmbeddedFont,Aptos_MSFontService,Calibri,Helvetica,sans-serif; font-size:12pt; color:rgb(0,0,0)\">\
New Product Regulations Strategy Online Touchpoint Meeting</div>\
<div style=\"font-family:Aptos,Aptos_EmbeddedFont,Aptos_MSFontService,Calibri,Helvetica,sans-serif; font-size:12pt; color:rgb(0,0,0)\">\
<br>\
</div>\
<div style=\"font-family:Aptos,Aptos_EmbeddedFont,Aptos_MSFontService,Calibri,Helvetica,sans-serif; font-size:12pt; color:rgb(0,0,0)\">\
You're receiving this message because you're a member of the Engineering group. If you don't want to receive any messages or events from this group, stop following it in&nbsp;your inbox.</div>\
<br>\
<div class=\"me-email-text\" lang=\"en-US\" style=\"max-width:1024px; color:#242424; font-family:'Segoe UI','Helvetica Neue',Helvetica,Arial,sans-serif\">\
<div aria-hidden=\"true\" style=\"margin-bottom:24px; overflow:hidden; white-space:nowrap\">\\EXAMPLE_SECRET_VALUE_PLACEHOLDER</div>\
<div style=\"margin-bottom:12px\"><span class=\"me-email-text\" style=\"font-size:20px; color:#242424; font-weight:600\">Microsoft Teams meeting</span>\
</div>\
<div style=\"margin-bottom:6px\"><span class=\"me-email-text\" style=\"font-size:20px; color:#242424; font-weight:600\">Join:\
</span><a href=\"https://teams.microsoft.com/meet/48803137263631?p=YXe9K6OhVD94VIC23M\" id=\"meet_invite_block.action.join_link\" title=\"Meeting join\" aria-label=\"Meeting join\" class=\"me-email-link\" style=\"font-size:20px; text-decoration:underline; color:#5B5FC7\">https://teams.microsoft.com/meet/48803137263631?p=YXe9K6OhVD94VIC23M</a>\
</div>\
<div style=\"margin-bottom:6px\"><span class=\"me-email-text-secondary\" style=\"font-size:14px; color:#616161\">Meeting ID:\
</span><span class=\"me-email-text\" style=\"font-size:14px; color:#242424\">488 031 372 636 31</span>\
</div>\
<div style=\"margin-bottom:32px\"><span class=\"me-email-text-secondary\" style=\"font-size:14px; color:#616161\">Passcode:\
</span><span class=\"me-email-text\" style=\"font-size:14px; color:#242424\">uN2Np6PN</span>\
</div>\
<div style=\"margin-bottom:12px; max-width:1024px\">\
<hr style=\"border:0; background:#616161; height:1px\">\
</div>\
<div style=\"margin-bottom:24px\"><a href=\"https://aka.ms/JoinTeamsMeeting?omkt=en-US\" id=\"meet_invite_block.action.help\" class=\"me-email-link\" style=\"font-size:14px; text-decoration:underline; color:#5B5FC7\">Need help?</a>\
<span style=\"color:#616161\">|</span> <a href=\"https://teams.microsoft.com/l/meetup-join/19%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.v2/0?context=%7b%22Tid%22%3a%22f2c94a41-d33d-4b60-bb3d-0bed4cdf9855%22%2c%22Oid%22%3a%229bd29c6c-181e-41f5-a1b6-bc30bbf652d3%22%7d\" id=\"EXAMPLE_SECRET_VALUE_PLACEHOLDER\" class=\"me-email-link\" style=\"font-size:14px; text-decoration:underline; color:#5B5FC7\">\
System reference</a> </div>\
<div><span class=\"me-email-text-secondary\" style=\"font-size:14px; color:#616161\">For organizers:\
</span><a href=\"https://teams.microsoft.com/meetingOptions/?organizerId=9bd29c6c-181e-41f5-a1b6-bc30bbf652d3&amp;tenantId=f2c94a41-d33d-4b60-bb3d-0bed4cdf9855&amp;threadId=EXAMPLE_SECRET_VALUE_PLACEHOLDER@thread.v2&amp;messageId=0&amp;language=en-US\" id=\"EXAMPLE_SECRET_VALUE_PLACEHOLDER\" class=\"me-email-link\" style=\"font-size:14px; text-decoration:underline; color:#5B5FC7\">Meeting\
 options</a> </div>\
<div style=\"margin-top:24px; margin-bottom:6px\"></div>\
<div style=\"margin-bottom:24px\"></div>\
<div aria-hidden=\"true\" style=\"margin-bottom:24px; overflow:hidden; white-space:nowrap\">\\EXAMPLE_SECRET_VALUE_PLACEHOLDER</div>\
</div>\
</body>\
</html>\
"
    },
    "start": {
      "dateTime": "2026-04-04T11:30:00.0000000",
      "timeZone": "UTC"
    },
    "end": {
      "dateTime": "2026-04-04T12:00:00.0000000",
      "timeZone": "UTC"
    },
    "location": {
      "displayName": "Microsoft Teams Meeting",
      "locationType": "default",
      "uniqueId": "Microsoft Teams Meeting",
      "uniqueIdType": "private"
    },
    "locations": [
      {
        "displayName": "Microsoft Teams Meeting",
        "locationType": "default",
        "uniqueId": "Microsoft Teams Meeting",
        "uniqueIdType": "private"
      }
    ],
    "recurrence": null,
    "attendees": [
      {
        "type": "required",
        "status": {
          "response": "none",
          "time": "0001-01-01T00:00:00Z"
        },
        "emailAddress": {
          "name": "Debra Berger",
          "address": "debraB@contoso.com"
        }
      }
    ],
    "organizer": {
      "emailAddress": {
        "name": "John Doe",
        "address": "john.doe@contoso.com"
      }
    },
    "onlineMeeting": {
      "joinUrl": "https://teams.microsoft.com/l/meetup-join/19%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.v2/0?context=%7b%22Tid%22%3a%22f2c94a41-d33d-4b60-bb3d-0bed4cdf9855%22%2c%22Oid%22%3a%229bd29c6c-181e-41f5-a1b6-bc30bbf652d3%22%7d"
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  allowNewTimeProposals     : true
  attendees                 : [{"type":"required","status":{"response":"none","time":"0001-01-01T00:00:00Z"},"emailAddress":{"name":"Debra Berger","address":"debraB@contoso.com"}}]
  body                      : {"contentType":"html","content":"<html>
<head>
<meta http-equiv=\"Content-Type\" content=\"text/html; charset=utf-8\">
</head>
<body>
<div style=\"font-family:Aptos,Aptos_EmbeddedFont,Aptos_MSFontService,Calibri,Helvetica,sans-serif; font-size:12pt; color:rgb(0,0,0)\">
New Product Regulations Strategy Online Touchpoint Meeting</div>
<div style=\"font-family:Aptos,Aptos_EmbeddedFont,Aptos_MSFontService,Calibri,Helvetica,sans-serif; font-size:12pt; color:rgb(0,0,0)\">
<br>
</div>
<div style=\"font-family:Aptos,Aptos_EmbeddedFont,Aptos_MSFontService,Calibri,Helvetica,sans-serif; font-size:12pt; color:rgb(0,0,0)\">
You're receiving this message because you're a member of the Engineering group. If you don't want to receive any messages or events from this group, stop following it in&nbsp;your inbox.</div>
<br>
<div class=\"me-email-text\" lang=\"en-US\" style=\"max-width:1024px; color:#242424; font-family:'Segoe UI','Helvetica Neue',Helvetica,Arial,sans-serif\">
<div aria-hidden=\"true\" style=\"margin-bottom:24px; overflow:hidden; white-space:nowrap\">\EXAMPLE_SECRET_VALUE_PLACEHOLDER</div>
<div style=\"margin-bottom:12px\"><span class=\"me-email-text\" style=\"font-size:20px; color:#242424; font-weight:600\">Microsoft Teams meeting</span>
</div>
<div style=\"margin-bottom:6px\"><span class=\"me-email-text\" style=\"font-size:20px; color:#242424; font-weight:600\">Join:
</span><a href=\"https://teams.microsoft.com/meet/48803137263631?p=YXe9K6OhVD94VIC23M\" id=\"meet_invite_block.action.join_link\" title=\"Meeting join\" aria-label=\"Meeting join\" class=\"me-email-link\" style=\"font-size:20px; text-decoration:underline; color:#5B5FC7\">https://teams.microsoft.com/meet/48803137263631?p=YXe9K6OhVD94VIC23M</a>
</div>
<div style=\"margin-bottom:6px\"><span class=\"me-email-text-secondary\" style=\"font-size:14px; color:#616161\">Meeting ID:
</span><span class=\"me-email-text\" style=\"font-size:14px; color:#242424\">488 031 372 636 31</span>
</div>
<div style=\"margin-bottom:32px\"><span class=\"me-email-text-secondary\" style=\"font-size:14px; color:#616161\">Passcode:
</span><span class=\"me-email-text\" style=\"font-size:14px; color:#242424\">uN2Np6PN</span>
</div>
<div style=\"margin-bottom:12px; max-width:1024px\">
<hr style=\"border:0; background:#616161; height:1px\">
</div>
<div style=\"margin-bottom:24px\"><a href=\"https://aka.ms/JoinTeamsMeeting?omkt=en-US\" id=\"meet_invite_block.action.help\" class=\"me-email-link\" style=\"font-size:14px; text-decoration:underline; color:#5B5FC7\">Need help?</a>
<span style=\"color:#616161\">|</span> <a href=\"https://teams.microsoft.com/l/meetup-join/19%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.v2/0?context=%7b%22Tid%22%3a%22f2c94a41-d33d-4b60-bb3d-0bed4cdf9855%22%2c%22Oid%22%3a%229bd29c6c-181e-41f5-a1b6-bc30bbf652d3%22%7d\" id=\"EXAMPLE_SECRET_VALUE_PLACEHOLDER\" class=\"me-email-link\" style=\"font-size:14px; text-decoration:underline; color:#5B5FC7\">
System reference</a> </div>
<div><span class=\"me-email-text-secondary\" style=\"font-size:14px; color:#616161\">For organizers:
</span><a href=\"https://teams.microsoft.com/meetingOptions/?organizerId=9bd29c6c-181e-41f5-a1b6-bc30bbf652d3&amp;tenantId=f2c94a41-d33d-4b60-bb3d-0bed4cdf9855&amp;threadId=EXAMPLE_SECRET_VALUE_PLACEHOLDER@thread.v2&amp;messageId=0&amp;language=en-US\" id=\"EXAMPLE_SECRET_VALUE_PLACEHOLDER\" class=\"me-email-link\" style=\"font-size:14px; text-decoration:underline; color:#5B5FC7\">Meeting
 options</a> </div>
<div style=\"margin-top:24px; margin-bottom:6px\"></div>
<div style=\"margin-bottom:24px\"></div>
<div aria-hidden=\"true\" style=\"margin-bottom:24px; overflow:hidden; white-space:nowrap\">\EXAMPLE_SECRET_VALUE_PLACEHOLDER</div>
</div>
</body>
</html>
"}
  bodyPreview               : New Product Regulations Strategy Online Touchpoint Meeting

  You're receiving this message because you're a member of the Engineering group. If you don't want to receive any messages or events from this group, stop following it in your inbox.

  ________
  categories                : []
  changeKey                 : xMBBaLl1lk+dAn8KkjfXKQAGLmp8jA==
  createdDateTime           : 2026-04-04T11:03:22.881996Z
  end                       : {"dateTime":"2026-04-04T12:00:00.0000000","timeZone":"UTC"}
  hasAttachments            : false
  hideAttendees             : false
  iCalUId                   : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  id                        : EXAMPLE_SECRET_VALUE_PLACEHOLDER==
  importance                : normal
  isAllDay                  : false
  isCancelled               : false
  isDraft                   : false
  isOnlineMeeting           : true
  isOrganizer               : true
  isReminderOn              : true
  lastModifiedDateTime      : 2026-04-04T11:05:26.2216557Z
  location                  : {"displayName":"Microsoft Teams Meeting","locationType":"default","uniqueId":"Microsoft Teams Meeting","uniqueIdType":"private"}
  locations                 : [{"displayName":"Microsoft Teams Meeting","locationType":"default","uniqueId":"Microsoft Teams Meeting","uniqueIdType":"private"}]
  occurrenceId              : null
  onlineMeeting             : {"joinUrl":"https://teams.microsoft.com/l/meetup-join/19%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.v2/0?context=%7b%22Tid%22%3a%22f2c94a41-d33d-4b60-bb3d-0bed4cdf9855%22%2c%22Oid%22%3a%229bd29c6c-181e-41f5-a1b6-bc30bbf652d3%22%7d"}
  onlineMeetingProvider     : teamsForBusiness
  onlineMeetingUrl          : null
  organizer                 : {"emailAddress":{"name":"John Doe","address":"john.doe@contoso.com"}}
  originalEndTimeZone       : UTC
  originalStartTimeZone     : UTC
  recurrence                : null
  reminderMinutesBeforeStart: 15
  responseRequested         : true
  responseStatus            : {"response":"organizer","time":"0001-01-01T00:00:00Z"}
  sensitivity               : normal
  seriesMasterId            : null
  showAs                    : busy
  start                     : {"dateTime":"2026-04-04T11:30:00.0000000","timeZone":"UTC"}
  subject                   : New Product Regulations Touchpoint
  transactionId             : localevent:93639269-b1b2-d604-5170-283b0e470da5
  type                      : singleInstance
  uid                       : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  webLink                   : https://outlook.office365.com/owa/?itemid=EXAMPLE_SECRET_VALUE_PLACEHOLDER%2F7V4K8g0q%2Badetip1DygcAxMBBaLl1lk%2BdAn8KkjfXKQAAAgENAAAAxMBBaLl1lk%2BdAn8KkjfXKQAGMVCCQQAAAA%3D%3D&exvsurl=1&path=/calendar/item
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,createdDateTime,lastModifiedDateTime,changeKey,transactionId,originalStartTimeZone,originalEndTimeZone,iCalUId,uid,reminderMinutesBeforeStart,isReminderOn,hasAttachments,subject,bodyPreview,importance,sensitivity,isAllDay,isCancelled,isOrganizer,responseRequested,seriesMasterId,showAs,type,webLink,onlineMeetingUrl,isOnlineMeeting,onlineMeetingProvider,allowNewTimeProposals,occurrenceId,isDraft,hideAttendees,recurrence
  EXAMPLE_SECRET_VALUE_PLACEHOLDER==,2026-04-04T11:03:22.881996Z,2026-04-04T11:05:26.2216557Z,xMBBaLl1lk+dAn8KkjfXKQAGLmp8jA==,localevent:93639269-b1b2-d604-5170-283b0e470da5,UTC,UTC,EXAMPLE_SECRET_VALUE_PLACEHOLDER,EXAMPLE_SECRET_VALUE_PLACEHOLDER,15,1,0,New Product Regulations Touchpoint,"New Product Regulations Strategy Online Touchpoint Meeting

  You're receiving this message because you're a member of the Engineering group. If you don't want to receive any messages or events from this group, stop following it in your inbox.

  ________",normal,normal,0,0,1,1,,busy,singleInstance,https://outlook.office365.com/owa/?itemid=EXAMPLE_SECRET_VALUE_PLACEHOLDER%2F7V4K8g0q%2Badetip1DygcAxMBBaLl1lk%2BdAn8KkjfXKQAAAgENAAAAxMBBaLl1lk%2BdAn8KkjfXKQAGMVCCQQAAAA%3D%3D&exvsurl=1&path=/calendar/item,,1,teamsForBusiness,1,,0,0,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # outlook event get --debug "false" --verbose "false" --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER==" --userId "9bd29c6c-181e-41f5-a1b6-bc30bbf652d3" --calendarName "Calendar"

  Date: 4/4/2026

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER==

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER\_adetip1DygcAxMBBaLl1lk\_dAn8KkjfXKQAAAgENAAAAxMBBaLl1lk\_dAn8KkjfXKQAGMVCCQQAAAA==
  createdDateTime | 2026-04-04T11:03:22.881996Z
  lastModifiedDateTime | 2026-04-04T11:05:26.2216557Z
  changeKey | xMBBaLl1lk+dAn8KkjfXKQAGLmp8jA==
  transactionId | localevent:93639269-b1b2-d604-5170-283b0e470da5
  originalStartTimeZone | UTC
  originalEndTimeZone | UTC
  iCalUId | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  uid | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  reminderMinutesBeforeStart | 15
  isReminderOn | true
  hasAttachments | false
  subject | New Product Regulations Touchpoint
  <br>You're receiving this message because you're a member of the Engineering group. If you don't want to receive any messages or events from thi<br>\_\_\_\_\_\_\_\_ing it in your inbox.
  importance | normal
  sensitivity | normal
  isAllDay | false
  isCancelled | false
  isOrganizer | true
  responseRequested | true
  showAs | busy
  type | singleInstance
  webLink | https://outlook.office365.com/owa/?itemid=EXAMPLE_SECRET_VALUE_PLACEHOLDER%2F7V4K8g0q%2Badetip1DygcAxMBBaLl1lk%2BdAn8KkjfXKQAAAgENAAAAxMBBaLl1lk%2BdAn8KkjfXKQAGMVCCQQAAAA%3D%3D&exvsurl=1&path=/calendar/item
  isOnlineMeeting | true
  onlineMeetingProvider | teamsForBusiness
  allowNewTimeProposals | true
  isDraft | false
  hideAttendees | false
  ```

  </TabItem>
</Tabs>
