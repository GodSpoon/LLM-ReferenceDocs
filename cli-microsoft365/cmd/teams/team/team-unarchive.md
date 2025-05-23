-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# teams team unarchive

Restores an archived Microsoft Teams team

## Usage

```sh
m365 teams team unarchive [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the Microsoft Teams team to restore. Specify either `id` or `name` but not both.

`-n, --name [name]`
: The display name of the Microsoft Teams team to restore. Specify either `id` or `name` but not both.
```

<Global />

## Remarks

This command supports admin permissions. Global admins and Microsoft Teams service admins can restore teams that they are not a member of.

If the command finds multiple Microsoft Teams teams with the specified name, it will prompt you to disambiguate which team it should use, listing the discovered team IDs.

This command restores users' ability to send messages and edit the team, abiding by tenant and team settings.

## Examples

Restore an archived Microsoft Teams team by id.

```sh
m365 teams team unarchive --id 6f6fd3f7-9ba5-4488-bbe6-a789004d0d55
```

Restore an archived Microsoft Teams team by name.

```sh
m365 teams team unarchive --name "Team Name"
```

## Response

The command won't return a response on success.
