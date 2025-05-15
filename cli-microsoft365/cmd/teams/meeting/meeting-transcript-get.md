-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams meeting transcript get

Downloads a transcript for a given meeting

## Usage

```sh
m365 teams meeting transcript get [options]
```

## Options

```md definition-list
`-u, --userId [userId]`
: The id of the user, omit to get meeting transcript for the currently signed-in user. Use either `id`, `userName` or `email`, but not multiple.

`-n, --userName [userName]`
: The name of the user, omit to get the meeting transcript for the currently signed-in user. Use either `id`, `userName` or `email`, but not multiple.

`--email [email]`
: The email of the user, omit to get the meeting transcript for the currently signed-in user. Use either `id`, `userName` or `email`, but not multiple.

`-m, --meetingId <meetingId>`
: The Id of the meeting.

`-i, --id <id>`
: The Id of the transcript.

`-f, --outputFile [outputFile]`
: Destination path for the report file.
```

<Global />

## Examples

Gets the specified transcript made for the current signed in user and Microsoft Teams meeting with given id.

```sh
m365 teams meeting transcript get --meetingId EXAMPLE_SECRET_VALUE_PLACEHOLDER --id EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

Saves the specified transcript made for a given user and Microsoft Teams meeting with the given id.

```sh
m365 teams meeting transcript get --userName garthf@contoso.com --meetingId EXAMPLE_SECRET_VALUE_PLACEHOLDER --id EXAMPLE_SECRET_VALUE_PLACEHOLDER --outputFile c:/Transcript.vtt
```

## Remarks

:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::

:::warning

To run this command with application permissions, tenant administrators must create an application access policy and grant it to a user. This authorizes the app configured in the policy to fetch online meetings and/or online meeting artifacts on behalf of that user. For more details, click [here](https://learn.microsoft.com/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER).

:::

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "meetingId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "meetingOrganizerId": "e1251b10-1ba4-49e3-b35a-933e3f21772b",
    "transcriptContentUrl": "https://graph.microsoft.com/beta/users/e1251b10-1ba4-49e3-b35a-933e3f21772b/onlineMeetings/EXAMPLE_SECRET_VALUE_PLACEHOLDER/transcripts/EXAMPLE_SECRET_VALUE_PLACEHOLDER/content",
    "createdDateTime": "2024-04-08T05:26:21.1936844Z",
    "meetingOrganizer": {
      "application": null,
      "device": null,
      "user": {
        "id": "e1251b10-1ba4-49e3-b35a-933e3f21772b",
        "displayName": null,
        "userIdentityType": "aadUser",
        "tenantId": "de348bc7-1aeb-4406-8cb3-97db021cadb4"
      }
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  createdDateTime     : 2024-04-08T05:26:21.1936844Z
  id                  : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  meetingId           : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  meetingOrganizer    : {"application":null,"device":null,"user":{"id":"e1251b10-1ba4-49e3-b35a-933e3f21772b","displayName":null,"userIdentityType":"aadUser","tenantId":"de348bc7-1aeb-4406-8cb3-97db021cadb4"}}
  meetingOrganizerId  : e1251b10-1ba4-49e3-b35a-933e3f21772b
  transcriptContentUrl: https://graph.microsoft.com/beta/users/e1251b10-1ba4-49e3-b35a-933e3f21772b/onlineMeetings/EXAMPLE_SECRET_VALUE_PLACEHOLDER/transcripts/EXAMPLE_SECRET_VALUE_PLACEHOLDER/content
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,meetingId,meetingOrganizerId,transcriptContentUrl,createdDateTime
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,EXAMPLE_SECRET_VALUE_PLACEHOLDER,e1251b10-1ba4-49e3-b35a-933e3f21772b,https://graph.microsoft.com/beta/users/e1251b10-1ba4-49e3-b35a-933e3f21772b/onlineMeetings/EXAMPLE_SECRET_VALUE_PLACEHOLDER/transcripts/EXAMPLE_SECRET_VALUE_PLACEHOLDER/content,2024-04-08T05:26:21.1936844Z
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams meeting transcript get --meetingId "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

  Date: 4/9/2024

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  meetingId | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  meetingOrganizerId | e1251b10-1ba4-49e3-b35a-933e3f21772b
  transcriptContentUrl | https://graph.microsoft.com/beta/users/e1251b10-1ba4-49e3-b35a-933e3f21772b/onlineMeetings/EXAMPLE_SECRET_VALUE_PLACEHOLDER/transcripts/EXAMPLE_SECRET_VALUE_PLACEHOLDER/content
  createdDateTime | 2024-04-08T05:26:21.1936844Z
  ```

  </TabItem>
</Tabs>
