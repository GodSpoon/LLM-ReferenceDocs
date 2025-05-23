-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# teams guestsettings set

Updates guest settings of a Microsoft Teams team

## Usage

```sh
m365 teams guestsettings set [options]
```

## Options

```md definition-list
`-i, --teamId <teamId>`
: The ID of the Teams team for which to update settings

`--allowCreateUpdateChannels [allowCreateUpdateChannels]`
: Set to `true` to allow guests to create and update channels and to `false` to disallow it

`--allowDeleteChannels [allowDeleteChannels]`
: Set to `true` to allow guests to create and update channels and to `false` to disallow it
```

<Global />

## Examples

Allow guests to create and edit channels

```sh
m365 teams guestsettings set --teamId '00000000-0000-0000-0000-000000000000' --allowCreateUpdateChannels true
```

Disallow guests to delete channels

```sh
m365 teams guestsettings set --teamId '00000000-0000-0000-0000-000000000000' --allowDeleteChannels false
```

## Response

The command won't return a response on success.
