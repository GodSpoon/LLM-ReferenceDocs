-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# viva engage group user remove

Removes a user from a Viva Engage group

## Usage

```sh
m365 viva engage group user remove [options]
```

## Options

```md definition-list
`--groupId <groupId>`
: The ID of the Viva Engage group.

`--id [id]`
: ID of the user to remove from the group. If not specified, removes the current user.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::

## Examples

Remove the current user from the group with the ID `5611239081`

```sh
m365 viva engage group user remove --groupId 5611239081
```

Remove the user with the ID `66622349` from the group with the ID `5611239081`

```sh
m365 viva engage group user remove --groupId 5611239081 --id 66622349
```

Remove the user with the ID `66622349` from the group with the ID `5611239081` without asking for confirmation

```sh
m365 viva engage group user remove --groupId 5611239081 --id 66622349 --force
```

## Response

The command won't return a response on success.
