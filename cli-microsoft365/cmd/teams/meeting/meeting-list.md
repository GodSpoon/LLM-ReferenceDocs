-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams meeting list

Retrieve all online meetings for a given user or shared mailbox

## Usage

```sh
m365 teams meeting list [options]
```

## Options

```md definition-list
`--startDateTime <startDateTime>`
: Time indicating the **inclusive** start of a time range of content to return.

`--endDateTime [endDateTime]`
: Time indicating the **exclusive** end of a time range of content to return.

`--isOrganizer`
: Set to retrieve only meetings the user is organizer for.

`-u, --userId [userId]`
: The id of the user or shared mailbox, omit to retrieve meetings for current signed in user. Use either `userId`, `userName` or `email`, but not multiple. Use only when using application permissions.

`-n, --userName [userName]`
: The name of the user or shared mailbox, omit to retrieve meetings for current signed in user. Use either `userId`, `userName` or `email`, but not multiple. Use only when using application permissions.

`--email [email]`
: The email of the user or shared mailbox, omit to retrieve meetings for current signed in user. Use either `userId`, `userName` or `email`, but not multiple. Use only when using application permissions.
```

<Global />

## Remarks

To use application permission for this command, an [application access policy](https://learn.microsoft.com/en-us/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER) must be created and assigned to a user. This authorizes the app configured in the policy to retrieve online meetings on behalf of that user.

## Examples

List all meetings of the currently logged in user between two specific dates

```sh
m365 teams meeting list --startDateTime '2022-01-01T10:00:00Z' --endDateTime '2022-03-31T23:59:59Z'
```

List all meetings for a specific user retrieved by email of which the user is an organizer using application permissions

```sh
m365 teams meeting list --startDateTime '2022-01-01T10:00:00Z' --email user@tenant.com --isOrganizer
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "creationDateTime": "2023-07-25T19:29:32.033109Z",
      "startDateTime": "2023-07-17T03:00:00Z",
      "endDateTime": "2023-07-17T04:00:00Z",
      "joinUrl": "https://teams.microsoft.com/l/meetup-join/19%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.v2/0?context=%7b%22Tid%22%3a%22ad4f158a-97c7-4914-a9bd-038ecde40ff3%22%2c%22Oid%22%3a%22b2091e18-7882-4efe-b7d1-90703f5a5c65%22%7d",
      "joinWebUrl": "https://teams.microsoft.com/l/meetup-join/19%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.v2/0?context=%7b%22Tid%22%3a%22ad4f158a-97c7-4914-a9bd-038ecde40ff3%22%2c%22Oid%22%3a%22b2091e18-7882-4efe-b7d1-90703f5a5c65%22%7d",
      "meetingCode": "396464591835",
      "subject": "Team meeting",
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
              "id": "b2091e18-7882-4efe-b7d1-90703f5a5c65",
              "displayName": null,
              "tenantId": "ad4f158a-97c7-4914-a9bd-038ecde40ff3",
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
                "id": "52bd2d9c-2d89-416f-96c4-ca94245e22c8",
                "displayName": null,
                "tenantId": "ad4f158a-97c7-4914-a9bd-038ecde40ff3",
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
        "joinMeetingId": "396464591835",
        "passcode": "Z3GYtQ"
      },
      "chatInfo": {
        "threadId": "19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@thread.v2",
        "messageId": "0",
        "replyChainMessageId": null
      },
      "joinInformation": {
        "content": "data:text/html,%3cdiv+style%3d%22width%3a100%25%3b%22%3e%0d%0a++++%3cspan+style%3d%22white-space%3anowrap%3bcolor%3a%235F5F5F%3bopacity%3a.36%3b%22%EXAMPLE_SECRET_VALUE_PLACEHOLDER%3c%2fspan%3e%0d%0a%3c%2fdiv%3e%0d%0a+%0d%0a+%3cdiv+class%3d%22me-email-text%22+style%3d%22color%3a%23252424%3bfont-family%3a%27Segoe+UI%27%2c%27Helvetica+Neue%27%2cHelvetica%2cArial%2csans-serif%3b%22+lang%3d%22en-US%22%3e%0d%0a++++%3cdiv+style%3d%22margin-top%3a+24px%3b+margin-bottom%3a+20px%3b%22%3e%0d%0a++++++++%3cspan+style%3d%22font-size%3a+24px%3b+color%3a%23252424%22%3eMicrosoft+Teams+meeting%3c%2fspan%3e%0d%0a++++%3c%2fdiv%3e%0d%0a++++%3cdiv+style%3d%22margin-bottom%3a+20px%3b%22%3e%0d%0a++++++++%3cdiv+style%3d%22margin-top%3a+0px%3b+margin-bottom%3a+0px%3b+font-weight%3a+bold%22%3e%0d%0a++++++++++%3cspan+style%3d%22font-size%3a+14px%3b+color%3a%23252424%22%3eJoin+on+your+computer%2c+mobile+app+or+room+device%3c%2fspan%3e%0d%0a++++++++%3c%2fdiv%3e%0d%0a++++++++%3ca+class%3d%22me-email-headline%22+style%3d%22font-size%3a+14px%3bfont-family%3a%27Segoe+UI+Semibold%27%2c%27Segoe+UI%27%2c%27Helvetica+Neue%27%2cHelvetica%2cArial%2csans-serif%3btext-decoration%3a+underline%3bcolor%3a+%236264a7%3b%22+href%3d%22https%3a%2f%2fteams.microsoft.com%2fl%2fmeetup-join%2f19%EXAMPLE_SECRET_VALUE_PLACEHOLDER%2540thread.v2%2f0%3fcontext%3d%257b%2522Tid%2522%253a%EXAMPLE_SECRET_VALUE_PLACEHOLDER%2522%252c%2522Oid%2522%253a%EXAMPLE_SECRET_VALUE_PLACEHOLDER%2522%257d%22+target%3d%22_blank%22+rel%3d%22noreferrer+noopener%22%3eClick+here+to+join+the+meeting%3c%2fa%3e%0d%0a++++%3c%2fdiv%3e%0d%0a++++%3cdiv+style%3d%22margin-bottom%3a20px%3b+margin-top%3a20px%22%3e%0d%0a++++%3cdiv+style%3d%22margin-bottom%3a4px%22%3e%0d%0a++++++++%3cspan+data-tid%3d%22meeting-code%22+style%3d%22font-size%3a+14px%3b+color%3a%23252424%3b%22%3e%0d%0a++++++++++++Meeting+ID%3a+%3cspan+style%3d%22font-size%3a16px%3b+color%3a%23252424%3b%22%3e396+464+591+835%3c%2fspan%3e%0d%0a+++++++%3c%2fspan%3e%0d%0a+++++++++++%3cbr+%2f%3e%3cspan+style%3d%22font-size%3a+14px%3b+color%3a%23252424%3b%22%3e+Passcode%3a+%3c%2fspan%3e+%3cspan+style%3d%22font-size%3a+16px%3b+color%3a%23252424%3b%22%3e+Z3GYtQ+%3c%2fspan%3e%0d%0a++++++++%3cdiv+style%3d%22font-size%3a+14px%3b%22%3e%3ca+class%3d%22me-email-link%22+style%3d%22font-size%3a+14px%3btext-decoration%3a+underline%3bcolor%3a+%236264a7%3bfont-family%3a%27Segoe+UI%27%2c%27Helvetica+Neue%27%2cHelvetica%2cArial%2csans-serif%3b%22+target%3d%22_blank%22+href%3d%22https%3a%2f%2fwww.microsoft.com%2fen-us%2fmicrosoft-teams%2fdownload-app%22+rel%3d%22noreferrer+noopener%22%3e%0d%0a++++++++Download+Teams%3c%2fa%3e+%7c+%3ca+class%3d%22me-email-link%22+style%3d%22font-size%3a+14px%3btext-decoration%3a+underline%3bcolor%3a+%236264a7%3bfont-family%3a%27Segoe+UI%27%2c%27Helvetica+Neue%27%2cHelvetica%2cArial%2csans-serif%3b%22+target%3d%22_blank%22+href%3d%22https%3a%2f%2fwww.microsoft.com%2fmicrosoft-teams%2fjoin-a-meeting%22+rel%3d%22noreferrer+noopener%22%3eJoin+on+the+web%3c%2fa%3e%3c%2fdiv%3e%0d%0a++++%3c%2fdiv%3e%0d%0a+%3c%2fdiv%3e%0d%0a++++%0d%0a++++++%0d%0a++++%0d%0a++++%0d%0a++++%0d%0a++++%3cdiv+style%3d%22margin-bottom%3a+24px%3bmargin-top%3a+20px%3b%22%3e%0d%0a++++++++%3ca+class%3d%22me-email-link%22+style%3d%22font-size%3a+14px%3btext-decoration%3a+underline%3bcolor%3a+%236264a7%3bfont-family%3a%27Segoe+UI%27%2c%27Helvetica+Neue%27%2cHelvetica%2cArial%2csans-serif%3b%22+target%3d%22_blank%22+href%3d%22https%3a%2f%2faka.ms%2fJoinTeamsMeeting%22+rel%3d%22noreferrer+noopener%22%3eLearn+More%3c%2fa%3e++%7c+%3ca+class%3d%22me-email-link%22+style%3d%22font-size%3a+14px%3btext-decoration%3a+underline%3bcolor%3a+%236264a7%3bfont-family%3a%27Segoe+UI%27%2c%27Helvetica+Neue%27%2cHelvetica%2cArial%2csans-serif%3b%22+target%3d%22_blank%22+href%3d%22https%3a%2f%2fteams.microsoft.com%2fmeetingOptions%2f%3forganizerId%3db2091e18-7882-4efe-b7d1-90703f5a5c65%26tenantId%3dad4f158a-97c7-4914-a9bd-038ecde40ff3%26threadId%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.v2%26messageId%3d0%26language%3den-US%22+rel%3d%22noreferrer+noopener%22%3eMeeting+options%3c%2fa%3e+%0d%0a++++++%3c%2fdiv%3e%0d%0a%3c%2fdiv%3e%0d%0a%3cdiv+style%3d%22font-size%3a+14px%3b+margin-bottom%3a+4px%3bfont-family%3a%27Segoe+UI%27%2c%27Helvetica+Neue%27%2cHelvetica%2cArial%2csans-serif%3b%22%3e%0d%0a%0d%0a%3c%2fdiv%3e%0d%0a%3cdiv+style%3d%22font-size%3a+12px%3b%22%3e%0d%0a%0d%0a%3c%2fdiv%3e%0d%0a%0d%0a%3c%2fdiv%3e%0d%0a%3cdiv+style%3d%22width%3a100%25%3b%22%3e%0d%0a++++%3cspan+style%3d%22white-space%3anowrap%3bcolor%3a%235F5F5F%3bopacity%3a.36%3b%22%EXAMPLE_SECRET_VALUE_PLACEHOLDER%3c%2fspan%3e%0d%0a%3c%2fdiv%3e",
        "contentType": "html"
      },
      "watermarkProtection": {
        "isEnabledForContentSharing": false,
        "isEnabledForVideo": false
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  subject       startDateTime         endDateTime
  ------------  --------------------  --------------------
  Team meeting  2023-07-17T03:00:00Z  2023-07-17T04:00:00Z
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,creationDateTime,startDateTime,endDateTime,joinUrl,joinWebUrl,meetingCode,subject,isBroadcast,autoAdmittedUsers,isEntryExitAnnounced,allowedPresenters,allowMeetingChat,shareMeetingChatHistoryDefault,allowTeamworkReactions,allowAttendeeToEnableMic,allowAttendeeToEnableCamera,recordAutomatically,allowParticipantsToChangeName,allowRecording,allowTranscription
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,2023-07-25T19:29:32.033109Z,2023-07-17T03:00:00Z,2023-07-17T04:00:00Z,https://teams.microsoft.com/l/meetup-join/19%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.v2/0?context=%7b%22Tid%22%3a%22ad4f158a-97c7-4914-a9bd-038ecde40ff3%22%2c%22Oid%22%3a%22b2091e18-7882-4efe-b7d1-90703f5a5c65%22%7d,https://teams.microsoft.com/l/meetup-join/19%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.v2/0?context=%7b%22Tid%22%3a%22ad4f158a-97c7-4914-a9bd-038ecde40ff3%22%2c%22Oid%22%3a%22b2091e18-7882-4efe-b7d1-90703f5a5c65%22%7d,396464591835,Team meeting,,unknownFutureValue,,everyone,enabled,none,1,1,1,,,1,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams meeting list --startDateTime "2023-07-17"

  Date: 25/7/2023

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  creationDateTime | 2023-07-25T19:29:32.033109Z
  startDateTime | 2023-07-17T03:00:00Z
  endDateTime | 2023-07-17T04:00:00Z
  joinUrl | https://teams.microsoft.com/l/meetup-join/19%3ameeting\EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.v2/0?context=%7b%22Tid%22%3a%22ad4f158a-97c7-4914-a9bd-038ecde40ff3%22%2c%22Oid%22%3a%22b2091e18-7882-4efe-b7d1-90703f5a5c65%22%7d
  joinWebUrl | https://teams.microsoft.com/l/meetup-join/19%3ameeting\EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.v2/0?context=%7b%22Tid%22%3a%22ad4f158a-97c7-4914-a9bd-038ecde40ff3%22%2c%22Oid%22%3a%22b2091e18-7882-4efe-b7d1-90703f5a5c65%22%7d
  meetingCode | 396464591835
  subject | Team meeting
  isBroadcast | false
  autoAdmittedUsers | unknownFutureValue
  isEntryExitAnnounced | false
  allowedPresenters | everyone
  allowMeetingChat | enabled
  shareMeetingChatHistoryDefault | none
  allowTeamworkReactions | true
  allowAttendeeToEnableMic | true
  allowAttendeeToEnableCamera | true
  recordAutomatically | false
  allowParticipantsToChangeName | false
  allowRecording | true
  allowTranscription | true
  ```

  </TabItem>
</Tabs>
