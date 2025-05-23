-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams channel member list

Lists members of the specified Microsoft Teams team channel

## Usage

```sh
m365 teams channel member list [options]
```

## Options

```md definition-list
`-i, --teamId [teamId]`
: The Id of the Microsoft Teams team. Specify either `teamId` or `teamName` but not both

`--teamName [teamName]`
: The display name of the Microsoft Teams team. Specify either `teamId` or `teamName` but not both

`-c, --channelId [channelId]`
: The Id of the Microsoft Teams team channel. Specify either `channelId` or `channelName` but not both

`--channelName [channelName]`
: The display name of the Microsoft Teams team channel. Specify either `channelId` or `channelName` but not both

`-r, --role [role]`
: Filter the results to only users with the given role: owner, member, guest
```

<Global />

## Examples
  
List the members of a specified Microsoft Teams team with the specified id and channel with the specified id.

```sh
m365 teams channel member list --teamId 00000000-0000-0000-0000-000000000000 --channelId 19:00000000000000000000000000000000@thread.skype
```

List the members of a specified Microsoft Teams team with the specified name and channel with the specified name.

```sh
m365 teams channel member list --teamName "Team Name" --channelName "Channel Name"
```

List all owners of the specified Microsoft Teams team with the specified id and channel the specified id.

```sh
m365 teams channel member list --teamId 00000000-0000-0000-0000-000000000000 --channelId 19:00000000000000000000000000000000@thread.skype --role owner
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER==",
      "roles": [
        "owner"
      ],
      "displayName": "John Doe",
      "visibleHistoryStartDateTime": "0001-01-01T00:00:00Z",
      "userId": "78ccf530-bbf0-47e4-aae6-da5f8c6fb142",
      "email": "johndoe@contoso.onmicrosoft.com",
      "tenantId": "446355e4-e7e3-43d5-82f8-d7ad8272d55b"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  displayName: John Doe
  email      : johndoe@contoso.onmicrosoft.com
  id         : EXAMPLE_SECRET_VALUE_PLACEHOLDER==
  roles      : ["owner"]
  userId     : 78ccf530-bbf0-47e4-aae6-da5f8c6fb142
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,roles,displayName,userId,email
  EXAMPLE_SECRET_VALUE_PLACEHOLDER==,"[""owner""]",John Doe,78ccf530-bbf0-47e4-aae6-da5f8c6fb142,johndoe@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams channel member list --teamName "Team Name" --channelName "Channel Name"

  Date: 5/6/2023

  ## John Doe (EXAMPLE_SECRET_VALUE_PLACEHOLDER==)

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER==
  displayName | John Doe
  visibleHistoryStartDateTime | 0001-01-01T00:00:00Z
  userId | 78ccf530-bbf0-47e4-aae6-da5f8c6fb142
  email | johndoe@contoso.onmicrosoft.com
  tenantId | 446355e4-e7e3-43d5-82f8-d7ad8272d55b
  ```

  </TabItem>
</Tabs>
