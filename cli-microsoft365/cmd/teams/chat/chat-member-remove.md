-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# teams chat member remove

Removes a member from a Microsoft Teams chat conversation

## Usage

```sh
m365 teams chat member remove [options]
```

## Options

```md definition-list
`-i, --chatId <chatId>`
: The ID of the chat conversation.

`--id [id]`
: The ID of the chat member. Specify either `id`, `userId`, or `userName` but not multiple.

`--userId [userId]`
: The ID of the Microsoft Entra user. Specify either `id`, `userId`, or `userName` but not multiple.

`--userName [userName]`
: User's UPN (user principal name, e.g. johndoe@example.com). Specify either `id`, `userId`, or `userName` but not multiple.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Remove a member from a Teams chat by its member ID without prompting for confirmation.

```sh
m365 teams chat member remove --chatId 19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@unq.gbl.spaces --id EXAMPLE_SECRET_VALUE_PLACEHOLDER== --force
```

Remove a member from a Teams chat by its Microsoft Entra ID.

```sh
m365 teams chat member remove --chatId 19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@unq.gbl.spaces --userId bd94e214-7852-48b0-a326-5a34b2a02183
```

Remove a member from a Teams chat by its Microsoft Entra UPN.

```sh
m365 teams chat member remove --chatId 19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@unq.gbl.spaces --userName john.doe@contoso.com
```

## Response

The command won't return a response on success.
