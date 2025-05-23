-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams meeting attendancereport get

Gets attendance report for a given meeting

## Usage

```sh
m365 teams meeting attendancereport get [options]
```

## Options

```md definition-list
`-u, --userId [userId]`
: The id of the user, omit to get attendance report for the current signed in user. Use either  `id`, `userName` or `email`, but not multiple.

`-n, --userName [userName]`
: The name of the user, omit to get attendance report for the current signed in user. Use either `id`, `userName` or `email`, but not multiple.

`--email [email]`
: The email of the user, omit to get attendance report for the current signed in user. Use either `id`, `userName` or `email`, but not multiple.

`-m, --meetingId <meetingId>`
: The Id of the meeting.

`-i, --id <id>`
: The Id of the attendance report.
```

<Global />

## Remarks

:::warning

To run this command with application permissions, tenant administrators must create an application access policy and grant it to a user. This authorizes the app configured in the policy to fetch online meetings and/or online meeting artifacts on behalf of that user. For more details, click [here](https://learn.microsoft.com/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER).

:::

:::note 

This method doesn't support channel meetings.

:::

## Examples

Gets the specified attendance report made for the current signed in user and Microsoft Teams meeting with given id.

```sh
m365 teams meeting attendancereport get --meetingId EXAMPLE_SECRET_VALUE_PLACEHOLDER --id a8634e64-3147-4a56-9b19-cc822e9c7972
```

Gets the specified attendance report made for the garthf@contoso.com and Microsoft Teams meeting with given id.

```sh
m365 teams meeting attendancereport list --userName garthf@contoso.com --meetingId EXAMPLE_SECRET_VALUE_PLACEHOLDER --id a8634e64-3147-4a56-9b19-cc822e9c7972
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "a8634e64-3147-4a56-9b19-cc822e9c7972",
    "totalParticipantCount": 1,
    "meetingStartDateTime": "2024-04-06T08:18:21.668Z",
    "meetingEndDateTime": "2024-04-06T08:18:28.482Z",
    "attendanceRecords": [
      {
        "id": "de36f75e-c103-410b-a18a-2bf6df06ac3b",
        "emailAddress": "john@contoso.com",
        "totalAttendanceInSeconds": 3,
        "role": "Organizer",
        "identity": {
          "id": "de36f75e-c103-410b-a18a-2bf6df06ac3b",
          "displayName": "John Doe",
          "tenantId": "f1dd4023-a656-480a-8a0e-c1b1eec51e1e"
        },
        "attendanceIntervals": [
          {
            "joinDateTime": "2024-04-06T08:18:24.5069531Z",
            "leaveDateTime": "2024-04-06T08:18:28.4820462Z",
            "durationInSeconds": 3
          }
        ]
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  attendanceRecords    : [{"id":"fe36f75e-c103-410b-a18a-2bf6df06ac3a","emailAddress":"john@contoso.com","totalAttendanceInSeconds":3,"role":"Organizer","identity":{"id":"de36f75e-c103-410b-a18a-2bf6df06ac3b","displayName":"John Doe","tenantId":"f1dd4023-a656-480a-8a0e-c1b1eec51e1e"},"attendanceIntervals":[{"joinDateTime":"2024-04-06T08:18:24.5069531Z","leaveDateTime":"2024-04-06T08:18:28.4820462Z","durationInSeconds":3}]}]
  id                   : a8634e64-3147-4a56-9b19-cc822e9c7972
  meetingEndDateTime   : 2024-04-06T08:18:28.482Z
  meetingStartDateTime : 2024-04-06T08:18:21.668Z
  totalParticipantCount: 1
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,totalParticipantCount,meetingStartDateTime,meetingEndDateTime
  a8634e64-3147-4a56-9b19-cc822e9c7972,1,2024-04-06T08:18:21.668Z,2024-04-06T08:18:28.482Z
  ```

  </TabItem>

  <TabItem value="Markdown">

  ```md
  # teams meeting attendancereport get --meetingId "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --id "a8634e64-3147-4a56-9b19-cc822e9c7972"

  Date: 09/04/2024

  ## a8634e64-3147-4a56-9b19-cc822e9c7972

  Property | Value
  ---------|-------
  id | a8634e64-3147-4a56-9b19-cc822e9c7972
  totalParticipantCount | 1
  meetingStartDateTime | 2024-04-06T08:18:21.668Z
  meetingEndDateTime | 2024-04-06T08:18:28.482Z
  ```

  </TabItem>
</Tabs>
