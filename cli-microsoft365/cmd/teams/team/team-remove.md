-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# teams team remove

Removes the specified Microsoft Teams team

## Usage

```sh
m365 teams team remove [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the Microsoft Teams team to remove. Specify either `id` or `name` but not both.

`-n, --name [name]`
: The display name of the Microsoft Teams team to remove. Specify either `id` or `name` but not both.

`-f, --force`
: Don't prompt for confirming removing the specified team.
```

<Global />

## Remarks

When deleted, Microsoft 365 groups are moved to a temporary container and can be restored within 30 days. After that time, they are permanently deleted. This applies only to Microsoft 365 groups.

If the command finds multiple Microsoft Teams teams with the specified name, it will prompt you to disambiguate which team it should use, listing the discovered team IDs.

## Examples

Removes the specified Microsoft Teams team by id.

```sh
m365 teams team remove --id 00000000-0000-0000-0000-000000000000
```

Removes the specified Microsoft Teams team by name.

```sh
m365 teams team remove --name "Team Name"
```

Removes the specified team without confirmation.

```sh
m365 teams team remove --id 00000000-0000-0000-0000-000000000000 --force
```

## Response

The command won't return a response on success.

## More information

- directory resource type (deleted items): [https://learn.microsoft.com/graph/api/resources/directory?view=graph-rest-1.0](https://learn.microsoft.com/graph/api/resources/directory?view=graph-rest-1.0)
