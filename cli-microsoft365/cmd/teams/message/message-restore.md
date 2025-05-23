-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams message restore

Restores a deleted message from a channel in a Microsoft Teams team

## Usage

```sh
m365 teams message restore [options]
```

## Options

```md definition-list
`--teamId [teamId]`
: ID of the Microsoft Teams team. Specify either `teamId` or `teamName` but not both.

`--teamName [teamName]`
:	Name of the Microsoft Teams team. Specify either `teamId` or `teamName` but not both.

`--channelId [channelId]`
:	Channel ID of the Microsoft Teams team. Specify either `channelId` or `channelName` but not both.

`--channelName [channelName]`
:	Channel name of the Microsoft Teams team. Specify either `channelId` or `channelName` but not both.

`-i, --id <id>`
:	The ID of the Teams message.
```

<Global />

## Remarks

:::info

This command does only support delegated permissions.

:::

You can only restore Microsoft Teams messages that you created yourself.

## Examples

Restore a deleted message by using IDs

```sh
m365 teams message restore --teamId 5f5d7b71-1161-44d8-bcc1-3da710eb4171 --channelId 19:4a95f7d8db4c4e7fae857bcebe0623e6@thread.tacv2 --id 1540747442203
```

Restore a deleted message by using display names

```sh
m365 teams message restore --teamName Marketing --channelName Branding --id 1540747442203
```

## Response

The command won't return a response on success.
