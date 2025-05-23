-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
﻿import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# outlook mailbox settings get

Get the user's mailbox settings

## Usage

```sh
m365 outlook mailbox settings get [options]
```

## Options

```md definition-list
`-i, --userId [userId]`
: The ID of the Microsoft Entra user for which you want to get mailbox settings. Specify either `userId` or `userName`, but not both. This option is required when using application permissions.

`-n, --userName [userName]`
: The UPN of the Microsoft Entra user for which you want to get mailbox settings. Specify either `userId` or `userName`, but not both. This option is required when using application permissions.
```

<Global />

## Examples

Get mailbox settings of the signed-in user

```sh
m365 outlook mailbox settings get
```

Get mailbox settings of a user specified by id

```sh
m365 outlook mailbox settings get --userId 1caf7dcd-7e83-4c3a-94f7-932a1299c844
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "archiveFolder": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "timeZone": "Central Europe Standard Time",
    "delegateMeetingMessageDeliveryOptions": "sendToDelegateOnly",
    "dateFormat": "dd.MM.yyyy",
    "timeFormat": "H:mm",
    "userPurpose": "user",
    "automaticRepliesSetting": {
      "status": "disabled",
      "externalAudience": "all",
      "internalReplyMessage": "On vacation. Will be back.",
      "externalReplyMessage": "Vacation",
      "scheduledStartDateTime": {
        "dateTime": "2025-01-20T08:00:00.0000000",
        "timeZone": "UTC"
      },
      "scheduledEndDateTime": {
        "dateTime": "2025-01-25T18:00:00.0000000",
        "timeZone": "UTC"
      }
    },
    "language": {
      "locale": "en-US",
      "displayName": "English (United States)"
    },
    "workingHours": {
      "daysOfWeek": [
        "monday",
        "tuesday",
        "wednesday",
        "thursday",
        "friday"
      ],
      "startTime": "08:00:00.0000000",
      "endTime": "16:30:00.0000000",
      "timeZone": {
        "name": "Central Europe Standard Time"
      }
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  archiveFolder                        : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  automaticRepliesSetting              : {"status":"disabled","externalAudience":"all","internalReplyMessage":"","externalReplyMessage":"","scheduledStartDateTime":{"dateTime":"2025-01-20T08:00:00.0000000","timeZone":"UTC"},"scheduledEndDateTime":{"dateTime":"2025-01-25T18:00:00.0000000","timeZone":"UTC"}}
  dateFormat                           : dd.MM.yyyy
  delegateMeetingMessageDeliveryOptions: sendToDelegateOnly
  language                             : {"locale":"en-US","displayName":"English (United States)"}
  timeFormat                           : H:mm
  timeZone                             : Central Europe Standard Time
  userPurpose                          : user
  workingHours                         : {"daysOfWeek":["monday","tuesday","wednesday","thursday","friday"],"startTime":"08:00:00.0000000","endTime":"16:30:00.0000000","timeZone":{"name":"Central Europe Standard Time"}}
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  archiveFolder,timeZone,delegateMeetingMessageDeliveryOptions,dateFormat,timeFormat,userPurpose
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,Central Europe Standard Time,sendToDelegateOnly,dd.MM.yyyy,H:mm,user
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # outlook mailbox settings get

  Date: 1/17/2025

  Property | Value
  ---------|-------
  archiveFolder | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  timeZone | Central Europe Standard Time
  delegateMeetingMessageDeliveryOptions | sendToDelegateOnly
  dateFormat | dd.MM.yyyy
  timeFormat | H:mm
  userPurpose | user
  ```

  </TabItem>
</Tabs>
