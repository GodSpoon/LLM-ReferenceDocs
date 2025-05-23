-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams meeting attendancereport list

Lists all attendance reports for a given meeting

## Usage

```sh
m365 teams meeting attendancereport list [options]
```

## Options

```md definition-list
`-u, --userId [userId]`
: The id of the user, omit to list attendance reports for current signed in user. Use either  `id`, `userName` or `email`, but not multiple.

`-n, --userName [userName]`
: The name of the user, omit to list attendance reports for current signed in user. Use either `id`, `userName` or `email`, but not multiple.

`--email [email]`
: The email of the user, omit to list attendance reports for current signed in user. Use either `id`, `userName` or `email`, but not multiple.

`-m, --meetingId <meetingId>`
: The Id of the meeting.
```

<Global />

## Examples

Lists all attendance reports made for the current signed in user and Microsoft Teams meeting with given id

```sh
m365 teams meeting attendancereport list --meetingId EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

Lists all attendance reports made for the garthf@contoso.com and Microsoft Teams meeting with given id

```sh
m365 teams meeting attendancereport list --userName garthf@contoso.com --meetingId EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "ae6ddf54-5d48-4448-a7a9-780eee17fa13",
      "totalParticipantCount": 6,
      "meetingStartDateTime": "2022-11-22T22:46:46.981Z",
      "meetingEndDateTime": "2022-11-22T22:47:07.703Z"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    totalParticipantCount
  ------------------------------------  ---------------------
  ae6ddf54-5d48-4448-a7a9-780eee17fa13  6
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,totalParticipantCount
  ae6ddf54-5d48-4448-a7a9-780eee17fa13,6
  ```

  </TabItem>
</Tabs>
