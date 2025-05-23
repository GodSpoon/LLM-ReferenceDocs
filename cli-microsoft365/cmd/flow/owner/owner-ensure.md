-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# flow owner ensure

Assigns/updates permissions to a Power Automate flow

## Usage

```sh
m365 flow owner ensure [options]
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

`--roleName <roleName>`
: Access level for the user on the flow. Valid options are `CanView` or `CanEdit`.

`--asAdmin`
: Run the command as admin.
```

<Global />

## Examples

Assign owner permissions to a specific Power Automate flow for a user with ID

```sh
m365 flow owner ensure --userId 5c241023-2ba5-4ea8-a516-a2481a3e6c51 --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 72f2be4a-78c1-4220-a048-dbf557296a72 --roleName CanEdit
```

Assign owner permissions to a specific Power Automate flow for a user with UPN

```sh
m365 flow owner ensure --userName "john.doe@contoso.com" --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 72f2be4a-78c1-4220-a048-dbf557296a72 --roleName CanEdit
```

Assign owner permissions to a specific Power Automate flow for a group

```sh
m365 flow owner ensure --groupId 8d4d9f32-1ab0-4f81-9054-efbb1759e8e6 --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 72f2be4a-78c1-4220-a048-dbf557296a72 --roleName CanEdit
```

## Response

The command won't return a response on success.
