-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# teams tab remove

Removes a tab from the specified channel

## Usage

```sh
m365 teams tab remove [options]
```

## Options

```md definition-list
`-t, --teamId <teamId>`
: The ID of the team where the tab exists

`-c, --channelId <channelId>`
: The ID of the channel to remove the tab from

`-i, --id <id>`
: The ID of the tab to remove

`-f, --force`
: Don't prompt for confirmation
```

<Global />

## Examples

Removes a tab from the specified channel. Will prompt for confirmation

```sh
m365 teams tab remove --teamId 00000000-0000-0000-0000-000000000000 --channelId 19:00000000000000000000000000000000@thread.skype --id 06805b9e-77e3-4b93-ac81-525eb87513b8
```

Removes a tab from the specified channel without prompting for confirmation

```sh
m365 teams tab remove --teamId 00000000-0000-0000-0000-000000000000 --channelId 19:00000000000000000000000000000000@thread.skype --id 06805b9e-77e3-4b93-ac81-525eb87513b8 --force
```

## Response

The command won't return a response on success.

## More information

- Delete tab from channel: [https://learn.microsoft.com/graph/api/channel-delete-tabs](https://learn.microsoft.com/graph/api/channel-delete-tabs)
