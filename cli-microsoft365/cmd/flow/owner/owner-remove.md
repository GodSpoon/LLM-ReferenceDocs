-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# flow owner remove

Removes owner permissions to a Power Automate flow

## Usage

```sh
m365 flow owner remove [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment.

`--flowName <flowName>`
: The name of the Power Automate flow.

`--userId [userId]`
: The ID of the user. Specify either `userId`, `userName`, `groupId` or `groupName`.

`--userName [userName]`
: User principal name of the user. Specify either `userId`, `userName`, `groupId` or `groupName`.

`--groupId [groupId]`
: The ID of the group. Specify either `userId`, `userName`, `groupId` or `groupName`.

`--groupName [groupName]`
: The name of the group. Specify either `userId`, `userName`, `groupId` or `groupName`.

`--asAdmin`
: Run the command as admin.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Remove owner permissions from a specific Power Automate flow for a user by ID without prompting for confirmation

```sh
m365 flow owner remove --userId 5c241023-2ba5-4ea8-a516-a2481a3e6c51 --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 72f2be4a-78c1-4220-a048-dbf557296a72 --force
```

Remove owner permissions from a specific Power Automate flow for a user by UPN as admin

```sh
m365 flow owner remove --userName john.doe@contoso.com --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 72f2be4a-78c1-4220-a048-dbf557296a72 --asAdmin
```

Remove owner permissions from a specific Power Automate flow for a group by ID

```sh
m365 flow owner remove --groupId 5c241023-2ba5-4ea8-a516-a2481a3e6c51 --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 72f2be4a-78c1-4220-a048-dbf557296a72
```

Remove owner permissions from a specific Power Automate flow for a group by name as admin

```sh
m365 flow owner remove --groupName "Test group" --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 72f2be4a-78c1-4220-a048-dbf557296a72 --asAdmin
```

## Response

The command won't return a response on success.
