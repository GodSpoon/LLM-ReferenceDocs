-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# teams channel member remove

Remove the specified member from the specified Microsoft Teams private or shared team channel

## Usage

```sh
m365 teams channel member remove [options]
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

`-f, --force`
: Don't prompt for confirmation
```

<Global />

## Examples
  
Remove the user _johndoe@example.com_ from the Microsoft Teams team with id 00000000-0000-0000-0000-000000000000 and channel id 19:00000000000000000000000000000000@thread.skype

```sh
m365 teams channel member remove --teamId 00000000-0000-0000-0000-000000000000 --channelId 19:00000000000000000000000000000000@thread.skype --userName "johndoe@example.com"
```

Remove the user with id 00000000-0000-0000-0000-000000000000 from the Microsoft Teams team with name _Team Name_ and channel with name _Channel Name_

```sh
m365 teams channel member remove --teamName "Team Name" --channelName "Channel Name" --userId 00000000-0000-0000-0000-000000000000
```

## Response

The command won't return a response on success.
