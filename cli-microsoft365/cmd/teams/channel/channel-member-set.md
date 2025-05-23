-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams channel member set

Updates the role of the specified member in the specified Microsoft Teams private or shared team channel

## Usage

```sh
m365 teams channel member set [options]
```

## Options

```md definition-list
`--teamId [teamId]`
: The Id of the Microsoft Teams team. Specify either `teamId` or `teamName` but not both

`--teamName [teamName]`
: The display name of the Microsoft Teams team. Specify either `teamId` or `teamName` but not both

`--channelId [channelId]`
: The Id of the Microsoft Teams team channel. Specify either `channelId` or `channelName` but not both

`--channelName [channelName]`
: The display name of the Microsoft Teams team channel. Specify either `channelId` or `channelName` but not both

`--userName [userName]`
: User's UPN (user principal name, e.g. johndoe@example.com). Specify either userName, userId or id but not multiple.

`--userId [userId]`
: User's Microsoft Entra ID. Specify either userName, userId or id but not multiple.

`--id [id]`
: Channel member Id of a user. Specify either userName, userId or id but not multiple.

`-r, --role <role>`
: The role to be assigned to the user: owner, member.
```

<Global />

## Examples
  
Updates the role of the user to owner in the Microsoft Teams team with id 00000000-0000-0000-0000-000000000000 and channel id 19:00000000000000000000000000000000@thread.skype

```sh
m365 teams channel member set --teamId 00000000-0000-0000-0000-000000000000 --channelId 19:00000000000000000000000000000000@thread.skype --userName "johndoe@example.com" --role owner
```

Updates the role of the user with id 00000000-0000-0000-0000-000000000000 to member in the Microsoft Teams team with name _Team Name_ and channel with name _Channel Name_

```sh
m365 teams channel member set --teamName "Team Name" --channelName "Channel Name" --userId 00000000-0000-0000-0000-000000000000 --role member
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER==",
    "roles": [],
    "displayName": "John Doe",
    "visibleHistoryStartDateTime": "0001-01-01T00:00:00Z",
    "userId": "00000000-0000-0000-0000-000000000000",
    "email": "johndoe@contoso.onmicrosoft.com",
    "tenantId": "446355e4-e7e3-43d5-82f8-d7ad8272d55b"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  displayName                : John Doe
  email                      : johndoe@contoso.onmicrosoft.com
  id                         : EXAMPLE_SECRET_VALUE_PLACEHOLDER==
  roles                      : []
  tenantId                   : 446355e4-e7e3-43d5-82f8-d7ad8272d55b
  userId                     : 00000000-0000-0000-0000-000000000000
  visibleHistoryStartDateTime: 0001-01-01T00:00:00Z
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,roles,displayName,visibleHistoryStartDateTime,userId,email,tenantId
  EXAMPLE_SECRET_VALUE_PLACEHOLDER==,[],John Doe,0001-01-01T00:00:00Z,00000000-0000-0000-0000-000000000000,johndoe@contoso.onmicrosoft.com,446355e4-e7e3-43d5-82f8-d7ad8272d55b
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md

  # teams channel member set --teamName "Team Name" --channelName "Channel Name" --userName "johndoe@contoso.onmicrosoft.com" --role "owner"

  Date: 5/6/2023

  ## John Doe (EXAMPLE_SECRET_VALUE_PLACEHOLDER==)

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER==
  displayName | John Doe
  visibleHistoryStartDateTime | 0001-01-01T00:00:00Z
  userId | 00000000-0000-0000-0000-000000000000
  email | johndoe@contoso.onmicrosoft.com
  tenantId | 446355e4-e7e3-43d5-82f8-d7ad8272d55b
  ```

  </TabItem>
</Tabs>
