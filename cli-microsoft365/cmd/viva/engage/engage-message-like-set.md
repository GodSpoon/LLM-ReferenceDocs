-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# viva engage message like set

Likes or unlikes a Viva Engage message

## Usage

```sh
m365 viva engage message like set [options]
```

## Options

```md definition-list
`--messageId <messageId>`
: The id of the Viva Engage message.

`--enable [enable]`
: Set to `true` to like a message. Set to `false` to unlike it. Default `true`.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::

## Examples

Likes the message with the ID `5611239081`

```sh
m365 viva engage message like set --messageId 5611239081
```

Unlike the message with the ID `5611239081`

```sh
m365 viva engage message like set --messageId 5611239081 --enable false
```

Unlike the message with the ID `5611239081` without asking for confirmation

```sh
m365 viva engage message like set --messageId 5611239081 --enable false --force
```

## Response

The command won't return a response on success.
