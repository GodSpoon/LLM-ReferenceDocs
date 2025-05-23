-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# viva engage message remove

Removes a Viva Engage message

## Usage

```sh
m365 viva engage message remove [options]
```

## Options

```md definition-list
`--id <id>`
: The id of the Viva Engage message.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::

To remove a message, you must either:

- have posted the message yourself
- be an administrator of the group the message was posted to or
- be an admin of the network the message is in

## Examples

Removes the Viva Engage message with the id _1239871123_

```sh
m365 viva engage message remove --id 1239871123
```

Removes the Viva Engage message with the id _1239871123_ without prompting for confirmation.

```sh
m365 viva engage message remove --id 1239871123 --force
```

## Response

The command won't return a response on success.
