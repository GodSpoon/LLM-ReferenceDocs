-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# v7 Upgrade Guidance

The v7 of CLI for Microsoft 365 introduces several breaking changes. To help you upgrade to the latest version of CLI for Microsoft 365, we've listed those changes along with any actions you may need to take.

## Entra ID

### Renamed `entra o365group` commands to `entra m365group`

In version 7 of the CLI for Microsoft 365, we have renamed all `entra o365group` commands to `entra m365group`. It has been some time since Office 365 was renamed to Microsoft 365. Office 365 groups have been named Microsoft 365 groups since then. It was time for CLI for Microsoft 365 to go along with this change.

#### What action do I need to take?

Replace every `entra o365group` command with its `entra m365group` equivalent in your scripts.


### Removed `deleted` flag from certain `entra` commands

In previous versions of CLI for Microsoft 365, we had a few commands under the Entra group that had a `--deleted` flag. This flag was used to get deleted users and groups in Entra ID. In this major release, we have removed this flag from the commands. To get all deleted users and groups in your tenant, you should now use different commands.

**Affected commands:**

Old way | New way
--- | ---
`entra group list --deleted` [^1] | [entra m365group recyclebinitem list](./cmd/entra/m365group/m365group-recyclebinitem-list.mdx)
`entra o365group list --deleted` | [entra m365group recyclebinitem list](./cmd/entra/m365group/m365group-recyclebinitem-list.mdx)
`entra user list --deleted` | [entra user recyclebinitem list](./cmd/entra/user/user-recyclebinitem-list.mdx)

#### What action do I need to take?

Use the above table to replace the old commands with the new ones in your scripts.

### All `entra m365group` commands now only work with Microsoft 365 groups

Previously using `entra m365group` commands allowed to retrieve, update, or remove other than just M365 groups. In version 7 of the CLI for Microsoft 365, we added an additional validation that will throw an error when you are using the command against groups that are not unified (Microsoft 365 group).

**Affected commands:**

- [entra m365group get](./cmd/entra/m365group/m365group-get.mdx)
- [entra m365group remove](./cmd/entra/m365group/m365group-remove.mdx)
- [entra m365group renew](./cmd/entra/m365group/m365group-renew.mdx)
- [entra m365group set](./cmd/entra/m365group/m365group-set.mdx)
- [entra m365group teamify](./cmd/entra/m365group/m365group-teamify.mdx)
- [entra m365group conversation list](./cmd/entra/m365group/m365group-conversation-list.mdx)
- [entra m365group conversation post list](./cmd/entra/m365group/m365group-conversation-post-list.mdx)
- [entra m365group user add](./cmd/entra/m365group/m365group-user-add.mdx)
- [entra m365group user list](./cmd/entra/m365group/m365group-user-list.mdx)
- [entra m365group user remove](./cmd/entra/m365group/m365group-user-remove.mdx)
- [entra m365group user set](./cmd/entra/m365group/m365group-user-set.mdx)

#### What action do I need to take?

If you are using one of the commands listed above, make sure you use them against Microsoft 365 groups.

## Power Apps

### Removed `pa pcf` commands

In CLI for Microsoft 365 v7 the following commands were removed:

- `pa pcf init`
- `pa solution init`
- `pa solution reference add`

As the PAC CLI evolved, our implementation of these commands got out of date. Since building Power Apps components is still possible only on Windows and we can't improve the process compared to the PAC CLI, we decided to remove these commands.

#### What action do I need to take?

Use the PAC CLI to build Power Apps components and solutions.

## Power Automate

### Updated output for certain `flow` commands

In this major release of CLI for Microsoft 365, we have made an enhancement for the data returned by certain flow commands. In previous versions, when no items were found, the commands gave no output. This made these commands very unpredictable to use in scripts. This has now been changed so an empty array will be used as output when no items are found.

Besides that, when using JSON output, we had duplicate properties in the result. These redundant properties have now been removed.

**Affected commands:**

- [flow environment get](./cmd/flow/environment/environment-get.mdx)
- [flow environment list](./cmd/flow/environment/environment-list.mdx)
- [flow run list](./cmd/flow/run/run-list.mdx)

#### What action do I need to take?

- Make sure that your scripts expect an empty array instead of no output when no results are found.
- When you are expecting a JSON output, make sure to recheck the response, few duplicate properties have been removed.

## Power Platform

### Updated output of `pp chatbot list`

The output of [pp chatbot list](./cmd/pp/copilot/copilot-list.mdx) contained a `displayName` property. However, the actual property coming from the API was called `name`. We changed `displayName` back to `name` so that it now aligns with the other chatbot commands where a `name` option can be used and a `name` property may be returned.

#### What action do I need to take?

If you use the `displayName` property from the command output in your scripts, expect a property called `name` instead.

## SharePoint

### Updated `spo file move`, `spo folder copy`, and `spo folder move` options

Nearly all commands to move and copy files and folders in SharePoint online have been updated. In v6 we already updated the [spo file copy](./cmd/spo/file/file-copy.mdx) command to use a new endpoint. This major release it was time for the other copy and move commands to follow. The improved functionality supports copying moving files with `#` and `%` chars in their name. When you specify an URL for options `webUrl`, `sourceUrl`, and `targetUrl`, make sure that you specify a decoded URL.

Because of this rework, we were able to add new options, but we also had to remove existing ones.

**Affected commands:**

- [spo file move](./cmd/spo/file/file-move.mdx)
- [spo folder copy](./cmd/spo/folder/folder-copy.mdx)
- [spo folder move](./cmd/spo/folder/folder-move.mdx)

**Removed options:**

- `--deleteIfAlreadyExists`
- `--allowSchemaMismatch`

#### What action do I need to take?

Update your scripts to use the new options. Verify that your scripts work as intended.

- Ensure all the URLs you provide are **decoded**.
- Remove the option `--allowSchemaMismatch`, this is the default behavior now.
- Replace option `--deleteIfAlreadyExists` with `--nameConflictBehavior replace`.

### Removed `deleted` flag from `spo site list` command

In the previous versions of CLI for Microsoft 365, you could get deleted sites from your SharePoint tenant using the command [spo site list](./cmd/spo/tenant/tenant-site-list.mdx) by providing the flag `--deleted`. In the latest release, we have removed this option from the command. To get all deleted sites in your tenant, you can now use the command [spo tenant recyclebinitem list](./cmd/spo/tenant/tenant-recyclebinitem-list.mdx).

#### What action do I need to take?

In your scripts, use the [spo tenant recyclebinitem list](./cmd/spo/tenant/tenant-recyclebinitem-list.mdx) command instead of `spo site list --deleted`.

### Removed `ID` property from certain outputs

When retrieving certain SharePoint objects, such as list items, the response contained two ID properties: `ID` and `Id`. This is the way SharePoint returns the data. In version 7 of the CLI for Microsoft 365, we have removed the `ID` property from the response. This to make it easier to convert the JSON response to for example a PowerShell object. Because JSON parsing in PowerShell is case-insensitive, this would result in an error.

The `ID` property has been removed for the following commands:

- [spo file get](./cmd/spo/file/file-get.mdx)
- [spo listitem add](./cmd/spo/listitem/listitem-add.mdx)
- [spo listitem set](./cmd/spo/listitem/listitem-set.mdx)
- [spo page get](./cmd/spo/page/page-get.mdx)
- [spo page list](./cmd/spo/page/page-list.mdx)
- [spo tenant applicationcustomizer list](./cmd/spo/tenant/tenant-applicationcustomizer-list.mdx)
- [spo tenant commandset list](./cmd/spo/tenant/tenant-commandset-list.mdx)

#### What action do I need to take?

If you are using one of the affected commands listed above, make sure to update your scripts to use the `Id` property instead of `ID`.

### Removal of deprecated command aliases

In version 7 of the CLI for Microsoft 365, we have removed deprecated command aliases. These aliases were introduced in the previous version to prevent the introduction of breaking changes. The following table lists the deprecated aliases and their replacements.

Deprecated alias | Replacement
--- | ---
spo list label get | [spo list retentionlabel get](./cmd/spo/list/list-retentionlabel-get.mdx)
spo list label set | [spo list retentionlabel ensure](./cmd/spo/list/list-retentionlabel-ensure.mdx)

#### What action do I need to take?

Update your scripts to use the new commands instead of the deprecated aliases.

### Updated `spo theme list` command output

In version 7 of the CLI For Microsoft 365, we have made an adjustment for the data returned by the command [spo theme list](./cmd/spo/theme/theme-list.mdx). Previously, when no items were found, the command had no output. This made this command very unpredictable to use in scripts. The command has now been updated so an empty array will be used as output when no items are found.

#### What action do I need to take?

Make sure that your script expects an empty array when there are no themes found.

### Removed option `schemaXml` for `spo list` commands

In this version of the CLI for Microsoft 365, the option `schemaXml` has been removed for the [spo list add](./cmd/spo/list/list-add.mdx) and [spo list set](./cmd/spo/list/list-set.mdx) commands. This option was used to specify the list schema XML when creating a list. This option has been removed as it is no longer supported by Microsoft 365.

#### What action do I need to take?

Remove the references to the option `schemaXml` from your scripts. Verify that your scripts work as intended.

### Updated `spo tenant commandset set` command with more options

In previous versions of CLI for Microsoft 365, to update a ListView Command Set, you could only specify option `id` using the command [spo tenant commandset set](./cmd/spo/tenant/tenant-commandset-set.mdx). In this release, we have expanded the feature so that you can also update existing ListView Command Sets using either `id`, `title`, or `clientSideComponentId`.

#### What action do I need to take?

Because option `id` was mandatory in v6, if your scripts are dependent on the default mandatory error output that the command would return, you may have to update your scripts accordingly.

### Removed deprecated options for `spo list retentionlabel ensure` command

In this version of the CLI for Microsoft 365, we have removed the options `label`, `blockDelete`, and `blockEdit` from the [spo list retentionlabel ensure](./cmd/spo/list/list-retentionlabel-ensure.mdx) command. Both options `blockDelete` and `blockEdit` were currently being ignored even though they were set when calling the command. The option `label` has been removed to match our naming conventions.

#### What action do I need to take? 

Remove the references to the option `blockDelete` and `blockEdit` from commands and replace the option `label` to `name` in scripts.

### Updated `spo tenant applicationcustomizer get` id property to list item id

In version 7 of the CLI for Microsoft 365, the `id` option of [spo tenant applicationcustomizer get](./cmd/spo/tenant/tenant-applicationcustomizer-get.mdx) has been updated. As of this release, it should be the list item ID instead of the product ID (GUID).

#### What action do I need to take? 

Update your scripts to use the list item ID for the `id` option instead of the UniqueId product ID.

## Teams

### Updated `teams meeting list` command output

In the past versions of CLI for Microsoft 365, the command [teams meeting list](./cmd/teams/meeting/meeting-list.mdx) returned Outlook calendar objects as a result. Because of this, the IDs displayed in the output were not the same as the IDs used in other `teams meeting` commands. This problem has been solved in v7. We have updated the output of the command to return Teams meeting objects instead of Outlook calendar objects. This means that the IDs displayed in the output are now the same as the IDs used in the other `teams meeting` commands.

<details>
  <summary>Click here to compare the different command outputs</summary>

<Tabs>
  <TabItem value="v6 output">

  ```json
  [
    {
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER=",
      "createdDateTime": "2022-06-26T12:39:34.224055Z",
      "lastModifiedDateTime": "2022-06-26T12:41:36.4357085Z",
      "changeKey": "YjgvMb2JnU+hthPoSzCuZAACMHITIQ==",
      "categories": [],
      "transactionId": null,
      "originalStartTimeZone": "W. Europe Standard Time",
      "originalEndTimeZone": "W. Europe Standard Time",
      "iCalUId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "reminderMinutesBeforeStart": 15,
      "isReminderOn": true,
      "hasAttachments": false,
      "subject": "Test meeting",
      "bodyPreview": "EXAMPLE_SECRET_VALUE_PLACEHOLDER\
Microsoft Teams meeting\
Join on your computer or mobile app\
Click here to join the meeting\
Learn More | Meeting options\\EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "importance": "normal",
      "sensitivity": "normal",
      "isAllDay": false,
      "isCancelled": false,
      "isOrganizer": true,
      "responseRequested": true,
      "seriesMasterId": null,
      "showAs": "busy",
      "type": "singleInstance",
      "webLink": "https://outlook.office365.com/owa/?itemid=EXAMPLE_SECRET_VALUE_PLACEHOLDER%2BhLMK5kAAAAAAENAABiOC8xvYmdT6G2E%2BhLMK5kAAIw3TQIAAA%3D&exvsurl=1&path=/calendar/item",
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
<div><br>\
<br>\
<br>\
<div style=\"width:100%; height:20px\"><span style=\"white-space:nowrap; color:#5F5F5F; opacity:.36\">EXAMPLE_SECRET_VALUE_PLACEHOLDER</span>\
</div>\
<div class=\"me-email-text\" lang=\"en-US\" style=\"color:#252424; font-family:'Segoe UI','Helvetica Neue',Helvetica,Arial,sans-serif\">\
<div style=\"margin-top:24px; margin-bottom:20px\"><span style=\"font-size:24px; color:#252424\">Microsoft Teams meeting</span>\
</div>\
<div style=\"margin-bottom:20px\">\
<div style=\"margin-top:0px; margin-bottom:0px; font-weight:bold\"><span style=\"font-size:14px; color:#252424\">Join on your computer or mobile app</span>\
</div>\
<a href=\"https://teams.microsoft.com/l/meetup-join/19%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.v2/0?context=%7b%22Tid%22%3a%22e1dd4023-a656-480a-8a0e-c1b1eec51e1d%22%2c%22Oid%22%3a%22fe36f75e-c103-410b-a18a-2bf6df06ac3a%22%7d\" class=\"me-email-headline\" style=\"font-size:14px; font-family:'Segoe UI Semibold','Segoe UI','Helvetica Neue',Helvetica,Arial,sans-serif; text-decoration:underline; color:#6264a7\">Click\
 here to join the meeting</a> </div>\
<div style=\"margin-bottom:24px; margin-top:20px\"><a href=\"https://aka.ms/JoinTeamsMeeting\" class=\"me-email-link\" style=\"font-size:14px; text-decoration:underline; color:#6264a7; font-family:'Segoe UI','Helvetica Neue',Helvetica,Arial,sans-serif\">Learn More</a>\
 | <a href=\"https://teams.microsoft.com/meetingOptions/?organizerId=fe36f75e-c103-410b-a18a-2bf6df06ac3a&amp;tenantId=e1dd4023-a656-480a-8a0e-c1b1eec51e1d&amp;threadId=EXAMPLE_SECRET_VALUE_PLACEHOLDER@thread.v2&amp;messageId=0&amp;language=en-US\" class=\"me-email-link\" style=\"font-size:14px; text-decoration:underline; color:#6264a7; font-family:'Segoe UI','Helvetica Neue',Helvetica,Arial,sans-serif\">\
Meeting options</a> </div>\
</div>\
<div style=\"font-size:14px; margin-bottom:4px; font-family:'Segoe UI','Helvetica Neue',Helvetica,Arial,sans-serif\">\
</div>\
<div style=\"font-size:12px\"></div>\
</div>\
<div style=\"width:100%; height:20px\"><span style=\"white-space:nowrap; color:#5F5F5F; opacity:.36\">EXAMPLE_SECRET_VALUE_PLACEHOLDER</span>\
</div>\
<div></div>\
</body>\
</html>\
"
      },
      "start": {
        "dateTime": "2022-06-26T12:30:00.0000000",
        "timeZone": "UTC"
      },
      "end": {
        "dateTime": "2022-06-26T13:00:00.0000000",
        "timeZone": "UTC"
      },
      "location": {
        "displayName": "",
        "locationType": "default",
        "uniqueIdType": "unknown",
        "address": {},
        "coordinates": {}
      },
      "locations": [],
      "recurrence": null,
      "attendees": [
        {
          "type": "required",
          "status": {
            "response": "none",
            "time": "0001-01-01T00:00:00Z"
          },
          "emailAddress": {
            "name": "User D",
            "address": "userD@outlook.com"
          }
        }
      ],
      "organizer": {
        "emailAddress": {
          "name": "User",
          "address": "user@tenant.com"
        }
      },
      "onlineMeeting": {
        "joinUrl": "https://teams.microsoft.com/l/meetup-join/19%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.v2/0?context=%7b%22Tid%22%3a%22e1dd4023-a656-480a-8a0e-c1b1eec51e1d%22%2c%22Oid%22%3a%22fe36f75e-c103-410b-a18a-2bf6df06ac3a%22%7d"
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="v7 output">

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
</Tabs>
</details>

#### What action do I need to take?

Update your scripts to expect the new output output displayed above.

## General

### Renamed option `confirm` to `force` in all commands

When doing destructive things like deleting a site, CLI for Microsoft 365 asks you to confirm your intention. In version 7 of the CLI for Microsoft 365, we have renamed the option `confirm` to `force` in **all** commands. This change aims to be more consistent with other CLI tools where `force` is used to suppress warnings.

#### What action do I need to take?

Update your scripts to use the new flag `--force` instead of `--confirm` for destructive commands.

### Aligned options with the naming convention

In version 7 of the CLI for Microsoft 365, we have made updates to the options for specific commands, aligning with our naming convention. This includes renaming options to ensure consistency and improve the CLI experience. Some other options have been renamed to align with the response output of the commands.
These changes aim to make it easier for you to use the CLI.

We've updated the following commands and options:

Command|Old option|New option
--|--|--
[entra app set](./cmd/entra/app/app-set.mdx)|`uri`|`uris`
[entra approleassignment add](./cmd/entra/approleassignment/approleassignment-add.mdx)|`scope`|`scopes`
[entra approleassignment remove](./cmd/entra/approleassignment/approleassignment-remove.mdx)|`scope`|`scopes`
[entra group get](./cmd/entra/group/group-get.mdx)|`title`|`displayName`
[entra user set](./cmd/entra/user/user-set.mdx)|`objectId`|`id`
[entra user set](./cmd/entra/user/user-set.mdx)|`userPrincipalName`|`userName`
[flow connector export](./cmd/pa/connector/connector-export.mdx)|`connector`|`name`
[flow export](./cmd/teams/channel/channel-member-add.mdx)|`id`|`name`
[graph subscription add](./cmd/graph/subscription/subscription-add.mdx)|`changeType`|`changeTypes`
[pa app consent set](./cmd/pa/app/app-consent-set.mdx)|`environment`|`environmentName`
[pa app export](./cmd/pa/app/app-export.mdx)|`environment`|`environmentName`
[pa app export](./cmd/pa/app/app-export.mdx)|`id`|`name`
[pa app export](./cmd/pa/app/app-export.mdx)|`n` (short)|`packageDisplayName`
[pa app list](./cmd/pa/app/app-list.mdx)|`environment`|`environmentName`
[pa connector export](./cmd/pa/connector/connector-export.mdx)|`connector`|`name`
[pp aibuildermodel get](./cmd/pp/aibuildermodel/aibuildermodel-get.mdx)|`environment`|`environmentName`
[pp aibuildermodel list](./cmd/pp/aibuildermodel/aibuildermodel-list.mdx)|`environment`|`environmentName`
[pp aibuildermodel remove](./cmd/pp/aibuildermodel/aibuildermodel-remove.mdx)|`environment`|`environmentName`
[pp card clone](./cmd/pp/card/card-clone.mdx)|`environment`|`environmentName`
[pp card get](./cmd/pp/card/card-get.mdx)|`environment`|`environmentName`
[pp card list](./cmd/pp/card/card-list.mdx)|`environment`|`environmentName`
[pp card remove](./cmd/pp/card/card-remove.mdx)|`environment`|`environmentName`
[pp chatbot get](./cmd/pp/copilot/copilot-get.mdx)|`environment`|`environmentName`
[pp chatbot list](./cmd/pp/copilot/copilot-list.mdx)|`environment`|`environmentName`
[pp chatbot remove](./cmd/pp/copilot/copilot-remove.mdx)|`environment`|`environmentName`
[pp dataverse table get](./cmd/pp/dataverse/dataverse-table-get.mdx)|`environment`|`environmentName`
[pp dataverse table list](./cmd/pp/dataverse/dataverse-table-list.mdx)|`environment`|`environmentName`
[pp dataverse table remove](./cmd/pp/dataverse/dataverse-table-remove.mdx)|`environment`|`environmentName`
[pp dataverse table row list](./cmd/pp/dataverse/dataverse-table-row-list.mdx)|`environment`|`environmentName`
[pp dataverse table row remove](./cmd/pp/dataverse/dataverse-table-row-remove.mdx)|`environment`|`environmentName`
[pp solution get](./cmd/pp/solution/solution-get.mdx)|`environment`|`environmentName`
[pp solution list](./cmd/pp/solution/solution-list.mdx)|`environment`|`environmentName`
[pp solution remove](./cmd/pp/solution/solution-remove.mdx)|`environment`|`environmentName`
[pp solution publish](./cmd/pp/solution/solution-publish.mdx)|`environment`|`environmentName`
[pp solution publisher add](./cmd/pp/solution/solution-publisher-add.mdx)|`environment`|`environmentName`
[pp solution publisher get](./cmd/pp/solution/solution-publisher-get.mdx)|`environment`|`environmentName`
[pp solution publisher list](./cmd/pp/solution/solution-publisher-list.mdx)|`environment`|`environmentName`
[pp solution publisher remove](./cmd/pp/solution/solution-publisher-remove.mdx)|`environment`|`environmentName`
[spo file get](./cmd/spo/file/file-get.mdx)|`w` (short)|`u` (short)
[spo file get](./cmd/spo/file/file-get.mdx)|`u` (short)|`url`
[spo file list](./cmd/spo/file/file-list.mdx)|`folder`|`folderUrl`
[spo file remove](./cmd/spo/file/file-remove.mdx)|`w` (short)|`u` (short)
[spo file remove](./cmd/spo/file/file-remove.mdx)|`u` (short)|`url`
[spo file version clear](./cmd/spo/file/file-version-clear.mdx)|`w` (short)|`u` (short)
[spo file version clear](./cmd/spo/file/file-version-clear.mdx)|`u` (short)|`fileUrl`
[spo file version get](./cmd/spo/file/file-version-get.mdx)|`w` (short)|`u` (short)
[spo file version get](./cmd/spo/file/file-version-get.mdx)|`u` (short)|`fileUrl`
[spo file version list](./cmd/spo/file/file-version-list.mdx)|`w` (short)|`u` (short)
[spo file version list](./cmd/spo/file/file-version-list.mdx)|`u` (short)|`fileUrl`
[spo file version remove](./cmd/spo/file/file-version-remove.mdx)|`w` (short)|`u` (short)
[spo file version remove](./cmd/spo/file/file-version-remove.mdx)|`u` (short)|`fileUrl`
[spo file version restore](./cmd/spo/file/file-version-restore.mdx)|`w` (short)|`u` (short)
[spo file version restore](./cmd/spo/file/file-version-restore.mdx)|`u` (short)|`fileUrl`
[spo group member add](./cmd/spo/group/group-member-add.mdx)|`userName`|`userNames`
[spo group member add](./cmd/spo/group/group-member-add.mdx)|`email`|`emails`
[spo group member add](./cmd/spo/group/group-member-add.mdx)|`userId`|`userIds`
[spo group member add](./cmd/spo/group/group-member-add.mdx)|`aadGroupId`|`aadGroupIds`
[spo group member add](./cmd/spo/group/group-member-add.mdx)|`aadGroupName`|`aadGroupNames`
[spo group member add](./cmd/spo/group/group-member-add.mdx)|`email`|`emails`
[spo group member add](./cmd/spo/group/group-member-add.mdx)|`userId`|`userIds`
[spo group member add](./cmd/spo/group/group-member-add.mdx)|`userName`|`userNames`
[spo listitem attachment list](./cmd/spo/listitem/listitem-attachment-list.mdx)|`itemId`|`listItemId`
[teams channel member add](./cmd/teams/channel/channel-member-add.mdx)|`userDisplayName`|`userDisplayNames`
[teams channel member add](./cmd/teams/channel/channel-member-add.mdx)|`userId`|`userIds`

#### What action do I need to take?

If you use any of the commands listed above, ensure that you use the new option names.

[^1]: Note that only Microsoft 365 groups can go to the recycle bin of your tenant. Therefore this command did exactly the same as its `m365group` equivalent.
