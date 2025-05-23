-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams meeting transcript list

Lists all transcripts for a given meeting

## Usage

```sh
m365 teams meeting transcript list [options]
```

## Options

```md definition-list
`-u, --userId [userId]`
: The id of the user, omit to list meeting transcripts list for current signed in user. Use either `id`, `userName` or `email`, but not multiple.

`-n, --userName [userName]`
: The upn of the user, omit to list meeting transcripts list for current signed in user. Use either `id`, `userName` or `email`, but not multiple.

`--email [email]`
: The email of the user, omit to list meeting transcripts list for current signed in user. Use either `id`, `userName` or `email`, but not multiple.

`-m, --meetingId <meetingId>`
: The id of the meeting.
```

<Global />

## Examples

Lists all transcripts made for the current signed in user and Microsoft Teams meeting with given id

```sh
m365 teams meeting transcript list --meetingId EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

Lists all transcripts for a meeting of a specific user

```sh
m365 teams meeting transcript list --userName garthf@contoso.com --meetingId EXAMPLE_SECRET_VALUE_PLACEHOLDER
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
  [
    {
        "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
        "meetingId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
        "meetingOrganizerId": "be11f523-2a4d-4eae-9d42-277410893c41",
        "transcriptContentUrl": "https://graph.microsoft.com/beta/users/be11f523-2a4d-4eae-9d42-277410893c41/onlineMeetings/EXAMPLE_SECRET_VALUE_PLACEHOLDER/transcripts/EXAMPLE_SECRET_VALUE_PLACEHOLDER/content",
        "createdDateTime": "2021-09-17T06:09:24.8968037Z"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                                        createdDateTime
  --------------------------------------------------------  ---------------------
  EXAMPLE_SECRET_VALUE_PLACEHOLDER  2021-09-17T06:09:24.8968037Z
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,meetingId,meetingOrganizerId,transcriptContentUrl,createdDateTime
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,EXAMPLE_SECRET_VALUE_PLACEHOLDER,be11f523-2a4d-4eae-9d42-277410893c41,https://graph.microsoft.com/beta/users/be11f523-2a4d-4eae-9d42-277410893c41/onlineMeetings/EXAMPLE_SECRET_VALUE_PLACEHOLDER/transcripts/EXAMPLE_SECRET_VALUE_PLACEHOLDER/content,2023-03-25T21:32:08.5586288Z
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams meeting transcript list --meetingId "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

  Date: 3/25/2023
  
  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER
  
  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  meetingId | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  meetingOrganizerId | be11f523-2a4d-4eae-9d42-277410893c41
  transcriptContentUrl | https://graph.microsoft.com/beta/users/be11f523-2a4d-4eae-9d42-277410893c41/onlineMeetings/EXAMPLE_SECRET_VALUE_PLACEHOLDER/transcripts/EXAMPLE_SECRET_VALUE_PLACEHOLDER/content
  createdDateTime | 2023-03-25T21:32:08.5586288Z
  ```

  </TabItem>
</Tabs>
