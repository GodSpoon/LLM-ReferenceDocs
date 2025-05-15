-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# outlook message remove

Permanently removes a specific message from a mailbox

## Usage

```sh
m365 outlook message remove [options]
```

## Options

```md definition-list
`-i, --id <id>`
: ID of the message.

`--userId [userId]`
: ID of the user that owns the mailbox. Specify either `userId` or `userName`, but not both. This option is required when using application permissions.

`--userName [userName]`
: User principal name of the user that owns the mailbox. Specify either `userId` or `userName`, but not both. This option is required when using application permissions.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::warning

This command will permanently delete the Outlook message. To move a message to the trash bin, use [outlook message move](./message-move.mdx) instead.

:::

## Examples

Remove a specific message for the currently signed-in user

```
m365 outlook message remove --id EXAMPLE_SECRET_VALUE_PLACEHOLDER=
```

Remove a specific message in a shared mailbox

```
m365 outlook message remove --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userName sharedmailbox@contoso.com
```

Remove a specific message from a specific mailbox specified by user ID using application permissions

```
m365 outlook message remove --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userId 6799fd1a-723b-4eb7-8e52-41ae530274ca
```

Remove a specific message from a specific mailbox specified by user UPN using application permissions

```
m365 outlook message remove --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userName john.doe@contoso.com
```

## Response

The command won't return a response on success.
