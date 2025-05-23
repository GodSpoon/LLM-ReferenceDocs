-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# teams team set

Updates settings of a Microsoft Teams team

## Usage

```sh
m365 teams team set [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the Microsoft Teams team for which to update settings.

`-n, --name [name]`
: The display name for the Microsoft Teams team for which to update settings.

`--description [description]`
: The description for the Microsoft Teams team.

`--mailNickName [mailNickName]`
: The mail alias for the Microsoft Teams team.

`--classification [classification]`
: The classification for the Microsoft Teams team.

`--visibility [visibility]`
: The visibility of the Microsoft Teams team. Valid values `Private`, `Public`.
```

<Global />

## Examples

Set Microsoft Teams team visibility.

```sh
m365 teams team set --id "00000000-0000-0000-0000-000000000000" --visibility Private
```

Set Microsoft Teams team classification.

```sh
m365 teams team set --id "00000000-0000-0000-0000-000000000000" --classification MBI
```

## Response

The command won't return a response on success.
