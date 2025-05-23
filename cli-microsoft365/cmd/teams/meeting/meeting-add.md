-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams meeting add

Create a new online meeting

## Usage

```sh
m365 teams meeting add [options]
```

## Options

```md definition-list
`-s, --startTime [startTime]`
: The start time of the meeting. If not specified, the start time will be set to the current time.

`-e, --endTime [endTime]`
: The end time of the meeting. If not specified, the end time will be set to one hour after the start time.

`--subject [subject]`
: The subject of the meeting.

`-p, --participantUserNames [participantUserNames]`
: A comma-separated list of participant UPNs.

`--organizerEmail [organizerEmail]`
: The organizer's email address.

`-r, --recordAutomatically`
: When using this flag, the meeting will be recorded automatically.
```

<Global />

## Remarks

:::info

This command creates a standalone meeting that is not associated with any event on the user's calendar; therefore, meetings created via this command will not show on the user's calendar.

:::

To create an online meeting for a specific organizer, use the `organizerEmail` option along with app-only permissions. The application should have the _OnlineMeetings.ReadWrite.All_ permissions, and a special policy should be assigned to the user specified in the `organizerEmail` option. You can find more information on how to assign this policy to a user [here](https://learn.microsoft.com/en-us/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER).

## Examples

Create a new online meeting for the currently logged-in user, starting immediately and ending after one hour. 

```sh
m365 teams meeting add
```

Create a new online meeting for the currently logged-in user, with a specified start date and a duration of one hour.

```sh
m365 teams meeting add --startTime "2025-09-21T13:30:00Z"
```

Create a new online meeting for the currently logged-in user, with specified end date the current date as the start date.

```sh
m365 teams meeting add --endTime "2025-09-21T23:55:00Z"
```

Create a new online meeting for the currently logged-in user, with specified start and end dates.

```sh
m365 teams meeting add --startTime "2025-09-21T13:30:00Z" --endTime "2025-09-21T23:55:00Z"
```

Create a new online meeting for the currently logged-in user, with a specified subject.

```sh
m365 teams meeting add --startTime "2025-09-21T13:30:00Z" --endTime "2025-09-21T23:55:00Z" --subject "Test Subject"
```

Create a new online meeting for the currently logged-in user, with a specified subject and a list of participantUserNames.

```sh
m365 teams meeting add --subject "Test Subject" --participantUserNames "john.doe@contoso.com,olga.manager@contoso.com"
```

Create a new online meeting for the currently logged-in user, with a specified subject, a list of participantUserNames, and automatic meeting recording.

```sh
m365 teams meeting add --subject "Test Subject" --participantUserNames "john.doe@contoso.com,olga.manager@contoso.com" --recordAutomatically
```

Create a new online meeting for a selected organizer, with a specified subject, a list of participantUserNames, and automatic meeting recording. This option is available for app-only permissions.

```sh
m365 teams meeting add --organizerEmail "john.doe@contoso.com" --subject "Test Subject" --participantUserNames "olga.manager@contoso.com" --recordAutomatically
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "abc",
    "creationDateTime": "2023-07-25T19:29:32.033109Z",
    "startDateTime": "2023-07-17T03:00:00Z",
    "endDateTime": "2023-07-17T04:00:00Z",
    "joinUrl": "https://teams.microsoft.com/l/meetup-join/abc",
    "joinWebUrl": "https://teams.microsoft.com/l/meetup-join/abc",
    "meetingCode": "12345",
    "subject": "Subject",
    "isBroadcast": false,
    "autoAdmittedUsers": "unknownFutureValue",
    "outerMeetingAutoAdmittedUsers": null,
    "isEntryExitAnnounced": false,
    "allowedPresenters": "everyone",
    "allowMeetingChat": "enabled",
    "shareMeetingChatHistoryDefault": "none",
    "allowTeamworkReactions": true,
    "allowAttendeeToEnableMic": true,
    "allowAttendeeToEnableCamera": true,
    "recordAutomatically": false,
    "anonymizeIdentityForRoles": [],
    "capabilities": [],
    "videoTeleconferenceId": null,
    "externalId": null,
    "iCalUid": null,
    "meetingType": null,
    "allowParticipantsToChangeName": false,
    "allowRecording": true,
    "allowTranscription": true,
    "meetingMigrationMode": null,
    "broadcastSettings": null,
    "audioConferencing": null,
    "meetingInfo": null,
    "participants": {
      "organizer": {
        "upn": "john.doe@contoso.com",
        "role": "presenter",
        "identity": {
          "application": null,
          "device": null,
          "user": {
            "id": "12345678-1234-1234-1234-12345678",
            "displayName": null,
            "tenantId": "12345678-1234-1234-1234-12345678",
            "identityProvider": "AAD"
          }
        }
      },
      "attendees": [
        {
          "upn": "adele.vance@contoso.com",
          "role": "attendee",
          "identity": {
            "application": null,
            "device": null,
            "user": {
              "id": "12345678-1234-1234-1234-12345678",
              "displayName": null,
              "tenantId": "12345678-1234-1234-1234-12345678,
              "identityProvider": "AAD"
            }
          }
        }
      ]
    },
    "lobbyBypassSettings": {
      "scope": "unknownFutureValue",
      "isDialInBypassEnabled": false
    },
    "joinMeetingIdSettings": {
      "isPasscodeRequired": true,
      "joinMeetingId": "12345",
      "passcode": "123456"
    },
    "chatInfo": {
      "threadId": "abc",
      "messageId": "0",
      "replyChainMessageId": null
    },
    "joinInformation": {
      "content": "textContent",
      "contentType": "html"
    },
    "watermarkProtection": {
      "isEnabledForContentSharing": false,
      "isEnabledForVideo": false
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  allowAttendeeToEnableCamera   : true   
  allowAttendeeToEnableMic      : true   
  allowMeetingChat              : enabled
  allowParticipantsToChangeName : false  
  allowRecording                : true
  allowTeamworkReactions        : true
  allowTranscription            : true
  allowedPresenters             : everyone
  anonymizeIdentityForRoles     : []
  audioConferencing             : null
  autoAdmittedUsers             : everyoneInCompany
  broadcastSettings             : null
  capabilities                  : []
  chatInfo                      : {"threadId":"19:meeting_ID@thread.v2","messageId":"0","replyChainMessageId":null}
  chatRestrictions              : null
  creationDateTime              : 2023-11-13T16:02:12.5012352Z
  endDateTime                   : 2023-11-13T17:02:11.9711697Z
  externalId                    : null
  iCalUid                       : null
  id                            : meetingID
  isBroadcast                   : false
  isEntryExitAnnounced          : true
  joinInformation               : {"content":"data:text/html,htmlMessageTemplate","contentType":"html"}
  joinMeetingIdSettings         : {"isPasscodeRequired":false,"joinMeetingId":"123456789012","passcode":null}
  joinUrl                       : https://teams.microsoft.com/l/meetup-join/abc
  joinWebUrl                    : https://teams.microsoft.com/l/meetup-join/abc
  lobbyBypassSettings           : {"scope":"organization","isDialInBypassEnabled":false}
  meetingCode                   : 123456789012
  meetingInfo                   : null
  meetingMigrationMode          : null
  meetingType                   : null
  outerMeetingAutoAdmittedUsers : null
  participants                  : {"organizer":{"upn":"user@contoso.com","role":"presenter","identity":{"application":null,"device":null,"user":{"id":"12345678-1234-1234-1234-12345678","displayName":null,"tenantId":"12345678-1234-1234-1234-12345678","identityProvider":"AAD"}}},"attendees":[]}
  recordAutomatically           : false
  shareMeetingChatHistoryDefault: none
  startDateTime                 : 2023-11-13T16:02:11.9711697Z
  subject                       : null
  videoTeleconferenceId         : null
  watermarkProtection           : null
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,creationDateTime,startDateTime,endDateTime,joinUrl,meetingCode,isBroadcast,autoAdmittedUsers,joinWebUrl,isEntryExitAnnounced,allowedPresenters,allowAttendeeToEnableMic,allowAttendeeToEnableCamera,allowMeetingChat,shareMeetingChatHistoryDefault,allowTeamworkReactions,recordAutomatically,allowParticipantsToChangeName,allowTranscription,allowRecording
meetingId,2023-11-13T16:03:03.5669316Z,2023-11-13T16:03:03.2213499Z,2023-11-13T17:03:03.2213499Z,https://teams.microsoft.com/l/meetup-join/abc,123456789012,,everyoneInCompany,https://teams.microsoft.com/l/meetup-join/abc,1,everyone,1,1,enabled,none,1,,,1,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams meeting add 

  Date: 13/11/2023

  ## meetingId

  Property | Value
  ---------|-------
  id | meetingId
  creationDateTime | 2023-11-13T16:03:57.6531542Z
  startDateTime | 2023-11-13T16:03:56.8464734Z
  endDateTime | 2023-11-13T17:03:56.8464734Z
  joinUrl | https://teams.microsoft.com/l/meetup-join/abc
  meetingCode | 123456789012
  isBroadcast | false
  autoAdmittedUsers | everyoneInCompany
  joinWebUrl | https://teams.microsoft.com/l/meetup-join/abc
  isEntryExitAnnounced | true
  allowedPresenters | everyone
  allowAttendeeToEnableMic | true
  allowAttendeeToEnableCamera | true
  allowMeetingChat | enabled
  shareMeetingChatHistoryDefault | none
  allowTeamworkReactions | true
  recordAutomatically | false
  allowParticipantsToChangeName | false
  allowTranscription | true
  allowRecording | true
  ```

  </TabItem>
</Tabs>
