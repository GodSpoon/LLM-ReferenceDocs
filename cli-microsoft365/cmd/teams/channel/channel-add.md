-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams channel add

Adds a channel to the specified Microsoft Teams team

## Usage

```sh
m365 teams channel add [options]
```

## Options

```md definition-list
`-i, --teamId [teamId]`
: The ID of the team to add the channel to. Specify either `teamId` or `teamName` but not both

`--teamName [teamName]`
: The display name of the team to add the channel to. Specify either `teamId` or `teamName` but not both

`-n, --name <name>`
: The name of the channel to add

`-d, --description [description]`
: The description of the channel to add

`--type [type]`
: Type of channel to create: `standard`, `private`, `shared`. Default `standard`.

`--owner [owner]`
: User with this ID or UPN will be added as owner of the channel. This option is required when type is `private` or `shared`.
```

<Global />

## Remarks

You can only add a channel to the Microsoft Teams team you are a member of.

## Examples

Add channel to the specified Microsoft Teams team with id 6703ac8a-c49b-4fd4-8223-28f0ac3a6402

```sh
m365 teams channel add --teamId 6703ac8a-c49b-4fd4-8223-28f0ac3a6402 --name climicrosoft365 --description development
```

Add channel to the specified Microsoft Teams team with name _Team Name_

```sh
m365 teams channel add --teamName "Team Name" --name climicrosoft365 --description development
```

Add private channel to the specified Microsoft Teams team with owner UPN

```sh
m365 teams channel add --teamName "Team Name" --name climicrosoft365 --type private --owner john.doe@contoso.com
```

Add shared channel to the specified Microsoft Teams team with owner ID

```sh
m365 teams channel add --teamId 6703ac8a-c49b-4fd4-8223-28f0ac3a6402 --name climicrosoft365 --type shared --owner cc693a7d-4833-4911-a89a-f0fe6e49bf69
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "19:591922f67c4341eeb15e49c791822bfe@thread.tacv2",
    "createdDateTime": "2022-11-05T10:02:44.3930065Z",
    "displayName": "climicrosoft365",
    "description": null,
    "isFavoriteByDefault": false,
    "email": "",
    "webUrl": "https://teams.microsoft.com/l/channel/19%3a591922f67c4341eeb15e49c791822bfe%40thread.tacv2/climicrosoft365?groupId=6703ac8a-c49b-4fd4-8223-28f0ac3a6402&tenantId=446355e4-e7e3-43d5-82f8-d7ad8272d55b",
    "membershipType": "standard"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  createdDateTime    : 2022-11-05T10:05:31.3998293Z
  description        : null
  displayName        : climicrosoft365
  email              :
  id                 : 19:591922f67c4341eeb15e49c791822bfe@thread.tacv2
  isFavoriteByDefault: false
  membershipType     : standard
  webUrl             : https://teams.microsoft.com/l/channel/19%3a591922f67c4341eeb15e49c791822bfe%40thread.tacv2/climicrosoft365?groupId=6703ac8a-c49b-4fd4-8223-28f0ac3a6402&tenantId=446355e4-e7e3-43d5-82f8-d7ad8272d55b
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,createdDateTime,displayName,description,isFavoriteByDefault,email,webUrl,membershipType
  19:591922f67c4341eeb15e49c791822bfe@thread.tacv2,2022-11-05T12:34:59.6583728Z,climicrosoft365,,,,https://teams.microsoft.com/l/channel/19%3a591922f67c4341eeb15e49c791822bfe%40thread.tacv2/climicrosoft365?groupId=6703ac8a-c49b-4fd4-8223-28f0ac3a6402&tenantId=446355e4-e7e3-43d5-82f8-d7ad8272d55b,standard
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams channel add --teamName "Team Name" --name "climicrosoft365" --description "development"

  Date: 5/12/2023

  ## climicrosoft365 (19:591922f67c4341eeb15e49c791822bfe@thread.tacv2)

  Property | Value
  ---------|-------
  id | 19:591922f67c4341eeb15e49c791822bfe@thread.tacv2
  createdDateTime | 2022-11-05T10:02:44.3930065Z
  displayName | climicrosoft365
  isFavoriteByDefault | false
  email |
  webUrl | https://teams.microsoft.com/l/channel/19%3a591922f67c4341eeb15e49c791822bfe%40thread.tacv2/climicrosoft365?groupId=6703ac8a-c49b-4fd4-8223-28f0ac3a6402&tenantId=446355e4-e7e3-43d5-82f8-d7ad8272d55b
  membershipType | standard
  ```

  </TabItem>
</Tabs>
