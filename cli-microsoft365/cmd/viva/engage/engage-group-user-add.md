-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# viva engage group user add

Adds a user to a Viva Engage Group

## Usage

```sh
m365 viva engage group user add [options]
```

## Options

```md definition-list
`--groupId <groupId>`
: The ID of the group to add the user to

`--id [id]`
: ID of the user to add to the group. If not specified, adds the current user

`--email [email]`
: E-mail of the user to add to the group
```

<Global />

## Remarks

:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::

If the specified user is not a member of the network, the command will return an HTTP 400 error message.

## Examples

Adds the current user to the group with the ID `5611239081`

```sh
m365 viva engage group user add --groupId 5611239081
```

Adds the user with ID `66622349` to the group with the ID `5611239081`

```sh
m365 viva engage group user add --groupId 5611239081 --id 66622349
```

Adds the user with e-mail to the group with ID `5611239081`

```sh
m365 viva engage group user add --groupId 5611239081 --email suzy@contoso.com
```

## Response

The command won't return a response on success.
