-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# teams team archive

Archives specified Microsoft Teams team

## Usage

```sh
m365 teams team archive [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the Microsoft Teams team to archive. Specify either `id` or `name` but not both.

`-n, --name [name]`
: The display name of the Microsoft Teams team to archive. Specify either `id` or `name` but not both.

`--shouldSetSpoSiteReadOnlyForMembers`
: Sets the permissions for team members to read-only on the SharePoint Online site associated with the team.
```

<Global />

## Remarks

Using this command, global admins and Microsoft Teams service admins can access teams that they are not a member of.

If the command finds multiple Microsoft Teams teams with the specified name, it will prompt you to disambiguate which team it should use, listing the discovered team IDs.

When a team is archived, users can no longer send or like messages on any channel in the team, edit the team's name, description, or other settings, or in general make most changes to the team. Membership changes to the team continue to be allowed.


## Examples

Archive the specified Microsoft Teams team by id.

```sh
m365 teams team archive --id 6f6fd3f7-9ba5-4488-bbe6-a789004d0d55
```

Archive the specified Microsoft Teams team by name.

```sh
m365 teams team archive --name "Team Name"
```

Archive the specified Microsoft Teams team and set permissions for team members to read-only on the SharePoint Online site associated with the team

```sh
m365 teams team archive --id 6f6fd3f7-9ba5-4488-bbe6-a789004d0d55 --shouldSetSpoSiteReadOnlyForMembers
```

## Response

The command won't return a response on success.
