-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
﻿import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# outlook mailbox settings set

Updates user mailbox settings

## Usage

```sh
m365 outlook mailbox settings set [options]
```

## Options

```md definition-list
`-i, --userId [userId]`
: The ID of the Microsoft Entra user to update mailbox settings for. Either `userId` or `userName` is required when using application permissions.

`-n, --userName [userName]`
: The UPN of the Microsoft Entra user to update mailbox settings for. Either `userId` or `userName` is required when using application permissions.

`--dateFormat [dateFormat]`
: The date format for the user's mailbox. Example: `dd.MM.yyyy`.

`--timeFormat [timeFormat]`
: The time format for the user's mailbox. Example: `H:mm`.

`--timeZone [timeZone]`
: The default time zone for the user's mailbox. Should follow [Windows time zone name](https://learn.microsoft.com/windows-hardware/manufacture/desktop/default-time-zones?view=windows-11#time-zones) or [IANA time zone identifier](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones#List). Example: `Central Europe Standard Time`.

`--language [language]`
: The preferred language for the user. Should follow [ISO 639-1 Code](https://learn.microsoft.com/openspecs/office_standards/ms-oe376/6c085406-a698-4e12-9d4d-c3b0ee3dbc4a). Example: `en-US`.

`--delegateMeetingMessageDeliveryOptions [delegateMeetingMessageDeliveryOptions]`
: Specifies who can receive meeting messages and meeting responses. Allowed values are `sendToDelegateOnly`, `sendToDelegateAndPrincipal`, or `sendToDelegateAndInformationToPrincipal`.

`--workingDays [workingDays]`
: The days of the week on which the user works, separated by a comma. Allowed values are `monday`, `tuesday`, `wednesday`, `thursday`, `friday`, `saturday`, or `sunday`.

`--workingHoursStartTime [workingHoursStartTime]`
: The time of the day that the user starts working. Example: `09:00`.

`--workingHoursEndTime [workingHoursEndTime]`
: The time of the day that the user stops working. Example: `17:00`.

`--workingHoursTimeZone [workingHoursTimeZone]`
: The name of a time zone to which the working hours apply. Should follow [Windows time zone name](https://learn.microsoft.com/windows-hardware/manufacture/desktop/default-time-zones?view=windows-11#time-zones) or [IANA time zone identifier](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones#List). Example: `Central Europe Standard Time`.

`--autoReplyExternalAudience [autoReplyExternalAudience]`
: Specifies external audience who will receive reply message. Allowed values are `none`, `contactsOnly`, or `all`.

`--autoReplyExternalMessage [autoReplyExternalMessage]`
: The reply message for the external audience.

`--autoReplyInternalMessage [autoReplyInternalMessage]`
: The reply message for the audience from the signed-in user's organization.

`--autoReplyStartDateTime [autoReplyStartDateTime]`
: The date and time that automatic replies are set to begin. Example: `2025-01-06T11:00:00.0000000`.

`--autoReplyStartTimeZone [autoReplyStartTimeZone]`
: The time zone that automatic replies are set to begin. 

`--autoReplyEndDateTime [autoReplyEndDateTime]`
: The date and time that automatic replies are set to end. Example: `2025-01-07T11:00:00.0000000`.

`--autoReplyEndTimeZone [autoReplyEndTimeZone]`
: The time zone that automatic replies are set to end.

`--autoReplyStatus [autoReplyStatus]`
: The status for automatic replies. Allowed values are `disabled`, `alwaysEnabled`, or `scheduled`.
```

<Global />

## Examples

Update date, time format and time zone of the signed-in user.

```sh
m365 outlook mailbox settings set --dateFormat 'dd.MM.yyyy' --timeFormat 'H:mm' --timeZone 'Central Europe Standard Time' --language 'en-US'
```

Update working hours of a user specified by id

```sh
m365 outlook mailbox settings set --userId 1caf7dcd-7e83-4c3a-94f7-932a1299c844 --workingDays 'monday,tuesday,thursday,friday' --workingHoursStartTime '08:00' --workingHoursEndTime '16:30' --workingHoursTimeZone 'Central Europe Standard Time'
```

Set scheduled automatic replies for the internal audience of a user specified by UPN

```sh
m365 outlook mailbox settings set --userName john.doe@contoso.com --autoReplyExternalAudience none --autoReplyInternalMessage 'On vacation' --autoReplyStartDateTime '2024-08-05T08:00:00.0000000' --autoReplyStartTimeZone 'Central Europe Standard Time' --autoReplyEndDateTime  '2024-08-09T16:00:00.0000000' --autoReplyEndTimeZone 'Central Europe Standard Time' --autoReplyStatus scheduled
```

## Response

The command returns the updated properties of the user mailbox settings.

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "timeZone": "Central Europe Standard Time",
    "timeFormat": "H:mm",
    "dateFormat": "dd.MM.yyyy",
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
  dateFormat  : dd.MM.yyyy
  language    : {"locale":"en-US","displayName":"English (United States)"}
  timeFormat  : H:mm
  timeZone    : Central Europe Standard Time
  workingHours: {"daysOfWeek":["monday","tuesday","wednesday","thursday","friday"],"startTime":"08:00:00.0000000","endTime":"16:30:00.0000000","timeZone":{"name":"Central Europe Standard Time"}}
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  dateFormat,timeZone,timeFormat
  dd.MM.yyy,Central Europe Standard Time,H:mm
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # outlook mailbox settings set --dateFormat "dd.MM.yyyy" --timeFormat "H:mm" --timeZone "Central Europe Standard Time" --language "en-US" --workingDays "monday,tuesday,wednesday,thursday,friday" --workingHoursStartTime "08:00:00.0000000" --workingHoursEndTime "16:30:00.0000000" --workingHoursTimeZone "Central Europe Standard Time"

  Date: 1/6/2025

  Property | Value
  ---------|-------
  dateFormat | dd.MM.yyyy
  timeZone | Central Europe Standard Time
  timeFormat | H:mm
  ```

  </TabItem>
</Tabs>
