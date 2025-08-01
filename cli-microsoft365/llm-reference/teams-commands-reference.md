<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - TEAMS Commands Reference

*This is an automatically generated condensed reference of all TEAMS commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-08-01*

---

## Table of Contents

- [app-install](#app-install)
- [app-list](#app-list)
- [app-publish](#app-publish)
- [app-remove](#app-remove)
- [app-uninstall](#app-uninstall)
- [app-update](#app-update)
- [cache-remove](#cache-remove)
- [channel-add](#channel-add)
- [channel-get](#channel-get)
- [channel-list](#channel-list)
- [channel-member-add](#channel-member-add)
- [channel-member-list](#channel-member-list)
- [channel-member-remove](#channel-member-remove)
- [channel-member-set](#channel-member-set)
- [channel-remove](#channel-remove)
- [channel-set](#channel-set)
- [chat-get](#chat-get)
- [chat-list](#chat-list)
- [chat-member-add](#chat-member-add)
- [chat-member-list](#chat-member-list)
- [chat-member-remove](#chat-member-remove)
- [chat-message-list](#chat-message-list)
- [chat-message-send](#chat-message-send)
- [funsettings-list](#funsettings-list)
- [funsettings-set](#funsettings-set)
- [guestsettings-list](#guestsettings-list)
- [guestsettings-set](#guestsettings-set)
- [meeting-add](#meeting-add)
- [meeting-attendancereport-get](#meeting-attendancereport-get)
- [meeting-attendancereport-list](#meeting-attendancereport-list)
- [meeting-get](#meeting-get)
- [meeting-list](#meeting-list)
- [meeting-transcript-get](#meeting-transcript-get)
- [meeting-transcript-list](#meeting-transcript-list)
- [membersettings-list](#membersettings-list)
- [membersettings-set](#membersettings-set)
- [message-get](#message-get)
- [message-list](#message-list)
- [message-remove](#message-remove)
- [message-reply-list](#message-reply-list)
- [message-restore](#message-restore)
- [message-send](#message-send)
- [messagingsettings-list](#messagingsettings-list)
- [messagingsettings-set](#messagingsettings-set)
- [EXAMPLE_SECRET_VALUE_PLACEHOLDER](#EXAMPLE_SECRET_VALUE_PLACEHOLDER)
- [report-deviceusageusercounts](#report-deviceusageusercounts)
- [report-deviceusageuserdetail](#report-deviceusageuserdetail)
- [report-directroutingcalls](#report-directroutingcalls)
- [report-pstncalls](#report-pstncalls)
- [report-useractivitycounts](#report-useractivitycounts)
- [report-useractivityusercounts](#report-useractivityusercounts)
- [report-useractivityuserdetail](#report-useractivityuserdetail)
- [tab-add](#tab-add)
- [tab-get](#tab-get)
- [tab-list](#tab-list)
- [tab-remove](#tab-remove)
- [team-add](#team-add)
- [team-app-list](#team-app-list)
- [team-archive](#team-archive)
- [team-clone](#team-clone)
- [team-get](#team-get)
- [team-list](#team-list)
- [team-remove](#team-remove)
- [team-set](#team-set)
- [team-unarchive](#team-unarchive)
- [user-app-add](#user-app-add)
- [user-app-list](#user-app-list)
- [user-app-remove](#user-app-remove)
- [user-app-upgrade](#user-app-upgrade)
- [user-list](#user-list)

---

## app-install

### Syntax
```
m365 teams app install [options]
```

### Example
```
m365 teams app install --id EXAMPLE-GUID-PLACEHOLDER --teamId EXAMPLE-GUID-PLACEHOLDER

m365 teams app install --id EXAMPLE-GUID-PLACEHOLDER --userName steve@contoso.com

m365 teams app install --id EXAMPLE-GUID-PLACEHOLDER --userId EXAMPLE-GUID-PLACEHOLDER

m365 teams app install --name "Test app" --teamId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
The `id` has to be the ID of the app from the Microsoft Teams App Catalog. Do not use the ID from the manifest of the zip app package. Use the [teams app list](./app-list.mdx) command to get this ID instead.



---

## app-list

### Syntax
```
m365 teams app list [options]
```

### Example
```
m365 teams app list

m365 teams app list --distributionMethod 'store'

```

---

## app-publish

### Syntax
```
m365 teams app publish [options]
```

### Example
```
m365 teams app publish --filePath ./teams-manifest.zip

```

### Remarks
:::info

To use this command you must be a Global administrator.

:::



---

## app-remove

### Syntax
```
m365 teams app remove [options]
```

### Example
```
m365 teams app remove --id EXAMPLE-GUID-PLACEHOLDER

m365 teams app remove --name HelloWorld --force

```

### Remarks
You can only remove a Teams app as a global administrator.



---

## app-uninstall

### Syntax
```
m365 teams app uninstall [options]
```

### Example
```
m365 teams app uninstall --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --teamId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
The `id` has to be the id the app instance installed in the Microsoft Teams team.
Do not use the ID from the manifest of the zip app package or the id from the Microsoft Teams App Catalog.



---

## app-update

### Syntax
```
m365 teams app update [options]
```

### Example
```
m365 teams app update --id EXAMPLE-GUID-PLACEHOLDER --filePath ./teams-manifest.zip

m365 teams app update --name "Test app" --filePath ./teams-manifest.zip

```

### Remarks
You can only update a Teams app as a global administrator.



---

## cache-remove

### Syntax
```
m365 teams cache remove [options]
```

### Example
```
m365 teams cache remove

m365 teams cache remove --client classic

```

### Remarks
This command will execute the following steps.

:::info

:::

If you run the command in the CLI Docker container, you will get the following error message:

The command works only on Windows and macOS. If you run it on a different operating system, you will get the `'abc' platform is unsupported for this command` error.



---

## channel-add

### Syntax
```
m365 teams channel add [options]
```

### Example
```
m365 teams channel add --teamId EXAMPLE-GUID-PLACEHOLDER --name climicrosoft365 --description development

m365 teams channel add --teamName "Team Name" --name climicrosoft365 --description development

m365 teams channel add --teamName "Team Name" --name climicrosoft365 --type private --owner john.doe@contoso.com

m365 teams channel add --teamId EXAMPLE-GUID-PLACEHOLDER --name climicrosoft365 --type shared --owner EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
You can only add a channel to the Microsoft Teams team you are a member of.



---

## channel-get

### Syntax
```
m365 teams channel get [options]
```

### Example
```
m365 teams channel get --teamId EXAMPLE-GUID-PLACEHOLDER --id '19:493665404ebd4a18adb8a980a31b4986@thread.skype'

m365 teams channel get --teamName "Team Name" --name "Channel Name"

m365 teams channel get --teamName "Team Name" --primary

```

---

## channel-list

### Syntax
```
m365 teams channel list [options]
```

### Example
```
m365 teams channel list --teamId EXAMPLE-GUID-PLACEHOLDER

m365 teams channel list --teamName "Team Name"

m365 teams channel list --teamId EXAMPLE-GUID-PLACEHOLDER --type private

```

---

## channel-member-add

### Syntax
```
m365 teams channel member add [options]
```

### Example
```
m365 teams channel member add --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:586a8b9e36c4479bbbd378e439a96df2@thread.skype --userIds "EXAMPLE-GUID-PLACEHOLDER,john.doe@contoso.com"

m365 teams channel member add --teamName "Human Resources" --channelName "Private Channel" --userDisplayNames "Anne Matthews,John Doe" --owner

```

### Remarks
At least one owner must be assigned to a private or shared channel.

You can only add members and owners of a team to a private channel.



---

## channel-member-list

### Syntax
```
m365 teams channel member list [options]
```

### Example
```
m365 teams channel member list --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:00000000000000000000000000000000@thread.skype

m365 teams channel member list --teamName "Team Name" --channelName "Channel Name"

m365 teams channel member list --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:00000000000000000000000000000000@thread.skype --role owner

```

---

## channel-member-remove

### Syntax
```
m365 teams channel member remove [options]
```

### Example
```
m365 teams channel member remove --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:00000000000000000000000000000000@thread.skype --userName "johndoe@example.com"

m365 teams channel member remove --teamName "Team Name" --channelName "Channel Name" --userId EXAMPLE-GUID-PLACEHOLDER

```

---

## channel-member-set

### Syntax
```
m365 teams channel member set [options]
```

### Example
```
m365 teams channel member set --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:00000000000000000000000000000000@thread.skype --userName "johndoe@example.com" --role owner

m365 teams channel member set --teamName "Team Name" --channelName "Channel Name" --userId EXAMPLE-GUID-PLACEHOLDER --role member

```

---

## channel-remove

### Syntax
```
m365 teams channel remove [options]
```

### Example
```
m365 teams channel remove --id 19:f3dcbb1674574677abcae89cb626f1e6@thread.skype --teamId EXAMPLE-GUID-PLACEHOLDER

m365 teams channel remove --id 19:f3dcbb1674574677abcae89cb626f1e6@thread.skype --teamId EXAMPLE-GUID-PLACEHOLDER --force

m365 teams channel remove --name 'name' --teamName "Team Name"

m365 teams channel remove --name 'name' --teamName "Team Name" --force 

```

### Remarks
When deleted, Microsoft Teams channels are moved to a recycle bin and can be restored within 30 days. After that time, they are permanently deleted.



---

## channel-set

### Syntax
```
m365 teams channel set [options]
```

### Example
```
m365 teams channel set --teamId "EXAMPLE-GUID-PLACEHOLDER" --name Reviews --newName Projects --description "Channel for new projects"

m365 teams channel set --teamId "EXAMPLE-GUID-PLACEHOLDER" --name Reviews --newName Projects

```

---

## chat-get

### Syntax
```
m365 teams chat get [options]
```

### Example
```
m365 teams chat get --id 19:2da4c29f6d7041eca70b638b43d45437@thread.v2

m365 teams chat get --participants alexw@contoso.com

m365 teams chat get --participants alexw@contoso.com,meganb@contoso.com

m365 teams chat get --name "Just a conversation"

```

### Remarks
The output will not include the chat conversation members or messages. It will just retrieve the conversation details.
When using the `participants` option, the signed-in user will automatically be included as a participant. There's no need to add it to the list manually.



---

## chat-list

### Syntax
```
m365 teams chat list [options]
```

### Example
```
m365 teams chat list

m365 teams chat list --userId EXAMPLE-GUID-PLACEHOLDER --type oneOnOne

m365 teams chat list --userName 'john@contoso.com' --type group 

```

---

## chat-member-add

### Syntax
```
m365 teams chat member add [options]
```

### Example
```
m365 teams chat member add --chatId 19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@unq.gbl.spaces --userId EXAMPLE-GUID-PLACEHOLDER

m365 teams chat member add --chatId 19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@unq.gbl.spaces --userName john.doe@contoso.com --visibleHistoryStartDateTime 2023-05-03T12:00:00Z

m365 teams chat member add --chatId 19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@unq.gbl.spaces --userName nelson.wilke@fabrikam.com --role guest --withAllHistory

```

### Remarks
When you specify a value for `role`, consider the following:



---

## chat-member-list

### Syntax
```
m365 teams chat member list [options]
```

### Example
```
m365 teams chat member list --chatId 19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@unq.gbl.spaces

```

---

## chat-member-remove

### Syntax
```
m365 teams chat member remove [options]
```

### Example
```
m365 teams chat member remove --chatId 19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@unq.gbl.spaces --id EXAMPLE_SECRET_VALUE_PLACEHOLDER== --force

m365 teams chat member remove --chatId 19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@unq.gbl.spaces --userId EXAMPLE-GUID-PLACEHOLDER

m365 teams chat member remove --chatId 19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@unq.gbl.spaces --userName john.doe@contoso.com

```

---

## chat-message-list

### Syntax
```
m365 teams chat message list [options]
```

### Example
```
m365 teams chat message list --chatId 19:2da4c29f6d7041eca70b638b43d45437@thread.v2

```

---

## chat-message-send

### Syntax
```
m365 teams chat message send [options]
```

### Example
```
m365 teams chat message send --chatId 19:2da4c29f6d7041eca70b638b43d45437@thread.v2 --message "Welcome to Teams"

m365 teams chat message send --userEmails alexw@contoso.com --message "Welcome to Teams"

m365 teams chat message send --userEmails alexw@contoso.com,meganb@contoso.com --message "Welcome to Teams"

m365 teams chat message send --chatName "Just a conversation" --message "Welcome to Teams"

```

### Remarks
A new chat conversation will be created if no existing conversation with the participants specified with emails is found.



---

## funsettings-list

### Syntax
```
m365 teams funsettings list [options]
```

### Example
```
m365 teams funsettings list --teamId EXAMPLE-GUID-PLACEHOLDER

```

---

## funsettings-set

### Syntax
```
m365 teams funsettings set [options]
```

### Example
```
m365 teams funsettings set --teamId EXAMPLE-GUID-PLACEHOLDER --allowGiphy true --giphyContentRating Moderate

m365 teams funsettings set --teamId EXAMPLE-GUID-PLACEHOLDER --allowGiphy false

m365 teams funsettings set --teamId EXAMPLE-GUID-PLACEHOLDER --allowStickersAndMemes true

m365 teams funsettings set --teamId EXAMPLE-GUID-PLACEHOLDER --allowCustomMemes false

```

---

## guestsettings-list

### Syntax
```
m365 teams guestsettings list [options]
```

### Example
```
m365 teams guestsettings list --teamId EXAMPLE-GUID-PLACEHOLDER

```

---

## guestsettings-set

### Syntax
```
m365 teams guestsettings set [options]
```

### Example
```
m365 teams guestsettings set --teamId 'EXAMPLE-GUID-PLACEHOLDER' --allowCreateUpdateChannels true

m365 teams guestsettings set --teamId 'EXAMPLE-GUID-PLACEHOLDER' --allowDeleteChannels false

```

---

## meeting-add

### Syntax
```
m365 teams meeting add [options]
```

### Example
```
m365 teams meeting add```

### Remarks
:::info

This command creates a standalone meeting that is not associated with any event on the user's calendar; therefore, meetings created via this command will not show on the user's calendar.

:::

To create an online meeting for a specific organizer, use the `organizerEmail` option along with app-only permissions. The application should have the _OnlineMeetings.ReadWrite.All_ permissions, and a special policy should be assigned to the user specified in the `organizerEmail` option. You can find more information on how to assign this policy to a user [here](https://learn.microsoft.com/en-us/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER).



---

## meeting-attendancereport-get

### Syntax
```
m365 teams meeting attendancereport get [options]
```

### Example
```
m365 teams meeting attendancereport get --meetingId EXAMPLE_SECRET_VALUE_PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER

m365 teams meeting attendancereport list --userName garthf@contoso.com --meetingId EXAMPLE_SECRET_VALUE_PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::warning

To run this command with application permissions, tenant administrators must create an application access policy and grant it to a user. This authorizes the app configured in the policy to fetch online meetings and/or online meeting artifacts on behalf of that user. For more details, click [here](https://learn.microsoft.com/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER).

:::

:::note 

This method doesn't support channel meetings.

:::



---

## meeting-attendancereport-list

### Syntax
```
m365 teams meeting attendancereport list [options]
```

### Example
```
m365 teams meeting attendancereport list --meetingId EXAMPLE_SECRET_VALUE_PLACEHOLDER

m365 teams meeting attendancereport list --userName garthf@contoso.com --meetingId EXAMPLE_SECRET_VALUE_PLACEHOLDER

```

---

## meeting-get

### Syntax
```
m365 teams meeting get [options]
```

### Example
```
m365 teams meeting get --userId EXAMPLE-GUID-PLACEHOLDER --joinUrl 'https://teams.microsoft.com/l/meetup-join/19%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.v2/0?context=%7b%22Tid%22%3a%22909c6581-5130-43e9-88f3-fcb3582cde37%22%2c%22Oid%22%3a%22dc17674c-81d9-4adb-bfb2-8f6a442e4622%22%7d'```

### Remarks
:::info

When you connect with application permissions, you should [add an application access policy](https://learn.microsoft.com/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER) for the command to work.

:::



---

## meeting-list

### Syntax
```
m365 teams meeting list [options]
```

### Example
```
m365 teams meeting list --startDateTime '2022-01-01T10:00:00Z' --endDateTime '2022-03-31T23:59:59Z'

m365 teams meeting list --startDateTime '2022-01-01T10:00:00Z' --email user@tenant.com --isOrganizer

```

### Remarks
To use application permission for this command, an [application access policy](https://learn.microsoft.com/en-us/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER) must be created and assigned to a user. This authorizes the app configured in the policy to retrieve online meetings on behalf of that user.



---

## meeting-transcript-get

### Syntax
```
m365 teams meeting transcript get [options]
```

### Example
```
m365 teams meeting transcript get --meetingId EXAMPLE_SECRET_VALUE_PLACEHOLDER --id EXAMPLE_SECRET_VALUE_PLACEHOLDER

m365 teams meeting transcript get --userName garthf@contoso.com --meetingId EXAMPLE_SECRET_VALUE_PLACEHOLDER --id EXAMPLE_SECRET_VALUE_PLACEHOLDER --outputFile c:/Transcript.vtt

```

### Remarks
:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::

:::warning

To run this command with application permissions, tenant administrators must create an application access policy and grant it to a user. This authorizes the app configured in the policy to fetch online meetings and/or online meeting artifacts on behalf of that user. For more details, click [here](https://learn.microsoft.com/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER).

:::



---

## meeting-transcript-list

### Syntax
```
m365 teams meeting transcript list [options]
```

### Example
```
m365 teams meeting transcript list --meetingId EXAMPLE_SECRET_VALUE_PLACEHOLDER

m365 teams meeting transcript list --userName garthf@contoso.com --meetingId EXAMPLE_SECRET_VALUE_PLACEHOLDER

```

### Remarks
:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::

:::warning

To run this command with application permissions, tenant administrators must create an application access policy and grant it to a user. This authorizes the app configured in the policy to fetch online meetings and/or online meeting artifacts on behalf of that user. For more details, click [here](https://learn.microsoft.com/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER).

:::



---

## membersettings-list

### Syntax
```
m365 teams membersettings list [options]
```

### Example
```
m365 teams membersettings list --teamId EXAMPLE-GUID-PLACEHOLDER

```

---

## membersettings-set

### Syntax
```
m365 teams membersettings set [options]
```

### Example
```
m365 teams membersettings set --teamId 'EXAMPLE-GUID-PLACEHOLDER' --allowCreateUpdateChannels true

m365 teams membersettings set --teamId 'EXAMPLE-GUID-PLACEHOLDER' --allowAddRemoveApps false

```

---

## message-get

### Syntax
```
m365 teams message get [options]
```

### Example
```
m365 teams message get --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:88f7e66a8dfe42be92db19505ae912a8@thread.skype --id 1540747442203

```

### Remarks
You can only retrieve a message from a Microsoft Teams team if you are a member of that team.



---

## message-list

### Syntax
```
m365 teams message list [options]
```

### Example
```
m365 teams message list --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:eb30973b42a847a2a1df92d91e37c76a@thread.skype

m365 teams message list --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:eb30973b42a847a2a1df92d91e37c76a@thread.skype --since 2019-12-31T14:00:00Z

```

### Remarks
You can only retrieve a message from a Microsoft Teams team if you are a member of that team.



---

## message-remove

### Syntax
```
m365 teams message remove [options]
```

### Example
```
m365 teams message remove --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:4a95f7d8db4c4e7fae857bcebe0623e6@thread.tacv2 --id 1540747442203

m365 teams message remove --teamName Marketing --channelName Branding --id 1540747442203

```

### Remarks
:::info

This command does only support delegated permissions.  

:::

You can only remove Microsoft Teams messages that you created yourself.



---

## message-reply-list

### Syntax
```
m365 teams message reply list [options]
```

### Example
```
m365 teams message reply list --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:88f7e66a8dfe42be92db19505ae912a8@thread.skype --messageId 1540747442203

```

### Remarks
You can only retrieve replies to a message from a Microsoft Teams team if you are a member of that team.



---

## message-restore

### Syntax
```
m365 teams message restore [options]
```

### Example
```
m365 teams message restore --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:4a95f7d8db4c4e7fae857bcebe0623e6@thread.tacv2 --id 1540747442203

m365 teams message restore --teamName Marketing --channelName Branding --id 1540747442203

```

### Remarks
:::info

This command does only support delegated permissions.

:::

You can only restore Microsoft Teams messages that you created yourself.



---

## message-send

### Syntax
```
m365 teams message send [options]
```

### Example
```
m365 teams message send --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:88f7e66a8dfe42be92db19505ae912a8@thread.skype --message "Hello World!"

m365 teams message send --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:88f7e66a8dfe42be92db19505ae912a8@thread.skype --message "Hello <b>World</b>!"

```

### Remarks
You can only send a message to a channel in a Microsoft Teams team if you are a member of that team or channel.



---

## messagingsettings-list

### Syntax
```
m365 teams messagingsettings list [options]
```

### Example
```
m365 teams messagingsettings list --teamId EXAMPLE-GUID-PLACEHOLDER

```

---

## messagingsettings-set

### Syntax
```
m365 teams messagingsettings set [options]
```

### Example
```
m365 teams messagingsettings set --teamId 'EXAMPLE-GUID-PLACEHOLDER' --allowUserEditMessages true

m365 teams messagingsettings set --teamId 'EXAMPLE-GUID-PLACEHOLDER' --allowUserDeleteMessages false

```

---

## EXAMPLE_SECRET_VALUE_PLACEHOLDER

### Syntax
```
m365 teams report deviceusagedistributionusercounts [options]
```

### Example
```
m365 teams report deviceusagedistributionusercounts --period D7

m365 teams report deviceusagedistributionusercounts --period D7 --output text > "deviceusagedistributionusercounts.txt"

m365 teams report deviceusagedistributionusercounts --period D7 --output json > "deviceusagedistributionusercounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-deviceusageusercounts

### Syntax
```
m365 teams report deviceusageusercounts [options]
```

### Example
```
m365 teams report deviceusageusercounts --period D7

m365 teams report deviceusageusercounts --period D7 --output text > "deviceusageusercounts.txt"

m365 teams report deviceusageusercounts --period D7 --output json > "deviceusageusercounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-deviceusageuserdetail

### Syntax
```
m365 teams report deviceusageuserdetail [options]
```

### Example
```
m365 teams report deviceusageuserdetail --period D7

m365 teams report deviceusageuserdetail --date 2019-07-01

m365 teams report deviceusageuserdetail --period D7 --output text > "deviceusageuserdetail.txt"

m365 teams report deviceusageuserdetail --period D7 --output json > "deviceusageuserdetail.json"

```

### Remarks
As this report is only available for the past 28 days, date parameter value should be a date from that range.

:::info

This command supports only csv and json output.

:::



---

## report-directroutingcalls

### Syntax
```
m365 teams report directroutingcalls [options]
```

### Example
```
m365 teams report directroutingcalls --fromDateTime 2020-10-31

m365 teams report directroutingcalls --fromDateTime 2020-10-31 --toDateTime 2020-12-31 --output text > "directroutingcalls.txt"

m365 teams report directroutingcalls --fromDateTime 2020-10-31 --toDateTime 2020-12-31 --output json > "directroutingcalls.json"

```

### Remarks
This command only works with app-only permissions. You will need to create your own Microsoft Entra app with `CallRecords.Read.All` permission assigned. Instructions on how to create your own Microsoft Entra app can be found at [Using your own Microsoft Entra identity](../../../user-guide/using-own-identity.mdx)

The difference between `fromDateTime` and `toDateTime` cannot exceed a period of 90 days.

:::info

This command supports only csv and json output.

:::



---

## report-pstncalls

### Syntax
```
m365 teams report pstncalls [options]
```

### Example
```
m365 teams report pstncalls --fromDateTime 2020-10-31

m365 teams report pstncalls --fromDateTime 2020-10-31 --toDateTime 2020-12-31 --output text > "pstncalls.txt"

m365 teams report pstncalls --fromDateTime 2020-10-31 --toDateTime 2020-12-31 --output json > "pstncalls.json"

```

### Remarks
This command only works with app-only permissions. You will need to create your own Microsoft Entra app with `CallRecords.Read.All` permission assigned. Instructions on how to create your own Microsoft Entra app can be found at [Using your own Microsoft Entra identity](../../../user-guide/using-own-identity.mdx)

The difference between `fromDateTime` and `toDateTime` cannot exceed a period of 90 days.

:::info

This command supports only csv and json output.

:::



---

## report-useractivitycounts

### Syntax
```
m365 teams report useractivitycounts [options]
```

### Example
```
m365 teams report useractivitycounts --period D7

m365 teams report useractivitycounts --period D7 --output text > "useractivitycounts.txt"

m365 teams report useractivitycounts --period D7 --output json > "useractivitycounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-useractivityusercounts

### Syntax
```
m365 teams report useractivityusercounts [options]
```

### Example
```
m365 teams report useractivityusercounts --period D7

m365 teams report useractivityusercounts --period D7 --output text > "useractivityusercounts.txt"

m365 teams report useractivityusercounts --period D7 --output json > "useractivityusercounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-useractivityuserdetail

### Syntax
```
m365 teams report useractivityuserdetail [options]
```

### Example
```
m365 teams report useractivityuserdetail --period D7

m365 teams report useractivityuserdetail --date 2019-07-13

m365 teams report useractivityuserdetail --period D7 --output text > "useractivityuserdetail.txt"

m365 teams report useractivityuserdetail --period D7 --output json > "useractivityuserdetail.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## tab-add

### Syntax
```
m365 teams tab add [options]
```

### Example
```
m365 teams tab add --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:00000000000000000000000000000000@thread.skype --appId EXAMPLE-GUID-PLACEHOLDER --appName 'My Contoso Tab' --contentUrl 'https://www.contoso.com/Orders/2DCA2E6C7A10415CAF6B8AB6661B3154/tabView'```

### Remarks
The corresponding app must already be installed in the team.



---

## tab-get

### Syntax
```
m365 teams tab get [options]
```

### Example
```
m365 teams tab get --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:00000000000000000000000000000000@thread.skype --id EXAMPLE-GUID-PLACEHOLDER

m365 teams tab get --teamName "Team Name" --channelName "Channel Name" --name "Tab Name"

```

### Remarks
You can only retrieve tabs for teams of which you are a member.



---

## tab-list

### Syntax
```
m365 teams tab list [options]
```

### Example
```
m365 teams tab list --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:00000000000000000000000000000000@thread.skype

m365 teams tab list --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:00000000000000000000000000000000@thread.skype --output json

```

### Remarks
You can only retrieve tabs for teams of which you are a member.

Tabs _Conversations_ and _Files_ are present in every team and therefore not included in the list of available tabs.



---

## tab-remove

### Syntax
```
m365 teams tab remove [options]
```

### Example
```
m365 teams tab remove --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:00000000000000000000000000000000@thread.skype --id EXAMPLE-GUID-PLACEHOLDER

m365 teams tab remove --teamId EXAMPLE-GUID-PLACEHOLDER --channelId 19:00000000000000000000000000000000@thread.skype --id EXAMPLE-GUID-PLACEHOLDER --force

```

---

## team-add

### Syntax
```
m365 teams team add [options]
```

### Example
```
m365 teams team add --name "Architecture" --description "Architecture Discussion" --ownerIds "EXAMPLE-GUID-PLACEHOLDER"

m365 teams team add --name "Architecture" --description "Architecture Discussion" --template @template.json

m365 teams team add --name "Architecture" --description "Architecture Discussion" --template @template.json --wait --memberUserNames "john@contoso.com,doe@contoso.com"

```

### Remarks
If you want to add a Team to an existing Microsoft 365 Group use the [entra m365group teamify](../../entra/m365group/m365group-teamify.mdx) command instead.

This command will return different responses based on the presence of the `--wait` option. If present, the command will return a `group` resource in the response. If not present, the command will return a `teamsAsyncOperation` resource in the response.

:::info

When using application permissions, you have to specify atleast one owner using the `--ownerUserNames`, `--ownerIds` or `--ownerEmails` options. This will also result in the `--wait` option being enforced if more than one owner is being set.

:::



---

## team-app-list

### Syntax
```
m365 teams team app list [options]
```

### Example
```
m365 teams team app list --teamId EXAMPLE-GUID-PLACEHOLDER

m365 teams team app list --teamName "Team Name"

```

---

## team-archive

### Syntax
```
m365 teams team archive [options]
```

### Example
```
m365 teams team archive --id EXAMPLE-GUID-PLACEHOLDER

m365 teams team archive --name "Team Name"

m365 teams team archive --id EXAMPLE-GUID-PLACEHOLDER --shouldSetSpoSiteReadOnlyForMembers

```

### Remarks
Using this command, global admins and Microsoft Teams service admins can access teams that they are not a member of.

If the command finds multiple Microsoft Teams teams with the specified name, it will prompt you to disambiguate which team it should use, listing the discovered team IDs.

When a team is archived, users can no longer send or like messages on any channel in the team, edit the team's name, description, or other settings, or in general make most changes to the team. Membership changes to the team continue to be allowed.



---

## team-clone

### Syntax
```
m365 teams team clone [options]
```

### Example
```
m365 teams team clone --id EXAMPLE-GUID-PLACEHOLDER --name "Library Assist" --partsToClone "apps,tabs,settings,channels,members"

m365 teams team clone --id EXAMPLE-GUID-PLACEHOLDER --name "Library Assist" --partsToClone "apps,tabs,settings,channels,members" --description "Self help community for library" --classification "Library" --visibility "public"

```

### Remarks
Using this command, global admins and Microsoft Teams service admins can access teams that they are not a member of.

When tabs are cloned, they are put into an unconfigured state. The first time you open them, you'll go through the configuration screen. If the person opening the tab does not have permission to configure apps, they will see a message explaining that the tab hasn't been configured.



---

## team-get

### Syntax
```
m365 teams team get
```

### Example
```
m365 teams team get --id EXAMPLE-GUID-PLACEHOLDER

m365 teams team get --name "Team Name"

```

---

## team-list

### Syntax
```
m365 teams team list [options]
```

### Example
```
m365 teams team list

m365 teams team list --joined

m365 teams team list --associated

m365 teams team list --joined --userName john.doe@contoso.com

m365 teams team list --associated --userId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::note

To list `joined` or `associated` teams of another user, you have to be a Teams Administrator or use application permissions.

:::

You can only see the details or archived status of the Microsoft Teams you are a member of.



---

## team-remove

### Syntax
```
m365 teams team remove [options]
```

### Example
```
m365 teams team remove --id EXAMPLE-GUID-PLACEHOLDER

m365 teams team remove --name "Team Name"

m365 teams team remove --id EXAMPLE-GUID-PLACEHOLDER --force

```

### Remarks
When deleted, Microsoft 365 groups are moved to a temporary container and can be restored within 30 days. After that time, they are permanently deleted. This applies only to Microsoft 365 groups.

If the command finds multiple Microsoft Teams teams with the specified name, it will prompt you to disambiguate which team it should use, listing the discovered team IDs.



---

## team-set

### Syntax
```
m365 teams team set [options]
```

### Example
```
m365 teams team set --id "EXAMPLE-GUID-PLACEHOLDER" --visibility Private

m365 teams team set --id "EXAMPLE-GUID-PLACEHOLDER" --classification MBI

```

---

## team-unarchive

### Syntax
```
m365 teams team unarchive [options]
```

### Example
```
m365 teams team unarchive --id EXAMPLE-GUID-PLACEHOLDER

m365 teams team unarchive --name "Team Name"

```

### Remarks
This command supports admin permissions. Global admins and Microsoft Teams service admins can restore teams that they are not a member of.

If the command finds multiple Microsoft Teams teams with the specified name, it will prompt you to disambiguate which team it should use, listing the discovered team IDs.

This command restores users' ability to send messages and edit the team, abiding by tenant and team settings.



---

## user-app-add

### Syntax
```
m365 teams user app add [options]
```

### Example
```
m365 teams user app add --id EXAMPLE-GUID-PLACEHOLDER --userId EXAMPLE-GUID-PLACEHOLDER

m365 teams user app add --name HelloWorld --userName admin@contoso.com

```

### Remarks
The `id` has to be the ID of the app from the Microsoft Teams App Catalog. Do not use the ID from the manifest of the zip app package. Use the [teams app list](../app/app-list.mdx) command to get this ID.



---

## user-app-list

### Syntax
```
m365 teams user app list [options]
```

### Example
```
m365 teams user app list --userId EXAMPLE-GUID-PLACEHOLDER

m365 teams user app list --userName admin@contoso.com

```

---

## user-app-remove

### Syntax
```
m365 teams user app remove [options]
```

### Example
```
m365 teams user app remove --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userId EXAMPLE-GUID-PLACEHOLDER

m365 teams user app remove --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userName admin@contoso.com

m365 teams user app remove --name HelloWorld --userId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
The `id` has to be the id of the app instance installed for the user.
Do not use the ID from the manifest of the zip app package or the id from the Microsoft Teams App Catalog.



---

## user-app-upgrade

### Syntax
```
m365 teams user app upgrade [options]
```

### Example
```
m365 teams user app upgrade --name HelloWorld --userName admin@contoso.com

m365 teams user app upgrade --name HelloWorld --userId EXAMPLE-GUID-PLACEHOLDER

m365 teams user app upgrade --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userName admin@contoso.com

m365 teams user app upgrade --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userId EXAMPLE-GUID-PLACEHOLDER

```

---

## user-list

### Syntax
```
m365 teams user list [options]
```

### Example
```
m365 teams user list --teamId 'EXAMPLE-GUID-PLACEHOLDER'

m365 teams user list --teamId 'EXAMPLE-GUID-PLACEHOLDER' --role Owner

```

---
