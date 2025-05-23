-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# teams channel remove

Removes the specified channel in the Microsoft Teams team

## Usage

```sh
m365 teams channel remove [options]
```

## Options

```md definition-list
`--teamId [teamId]`
: The ID of the team to which the channel to remove belongs. Specify either `teamId` or `teamName` but not both.

`--teamName [teamName]`
: The display name of the team to which the channel to remove belongs. Specify either `teamId` or `teamName` but not both.

`-i, --id [id]`
: The ID of the channel to remove. Specify `id` or `name` but not both.

`-n, --name [name]`
: The name of the channel to remove. Specify `id` or `name` but not both.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

When deleted, Microsoft Teams channels are moved to a recycle bin and can be restored within 30 days. After that time, they are permanently deleted.

## Examples

Remove the specified Microsoft Teams channel by Id

```sh
m365 teams channel remove --id 19:f3dcbb1674574677abcae89cb626f1e6@thread.skype --teamId d66b8110-fcad-49e8-8159-0d488ddb7656
```

Remove the specified Microsoft Teams channel by Id without confirmation

```sh
m365 teams channel remove --id 19:f3dcbb1674574677abcae89cb626f1e6@thread.skype --teamId d66b8110-fcad-49e8-8159-0d488ddb7656 --force
```

Remove the specified Microsoft Teams channel by Name

```sh
m365 teams channel remove --name 'name' --teamName "Team Name"
```

Remove the specified Microsoft Teams channel by Name without confirmation

```sh
m365 teams channel remove --name 'name' --teamName "Team Name" --force 
```

## Response

The command won't return a response on success.

## More information

- directory resource type (deleted items): [https://learn.microsoft.com/graph/api/resources/directory?view=graph-rest-1.0](https://learn.microsoft.com/graph/api/resources/directory?view=graph-rest-1.0)
