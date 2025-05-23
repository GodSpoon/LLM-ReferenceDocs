-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# pa app permission remove

Removes permissions to a Power Apps app

## Usage

```sh
m365 pa app permission remove [options]
```

## Options

```md definition-list
`--appName <appName>`
: The name (GUID) of the Microsoft Power App.

`--userId [userId]`
: The ID of the Microsoft Entra user. Specify either `userId`, `userName`, `groupId`, `groupName`, or `tenant`.

`--userName [userName]`
: The user principal name of the user. Specify either `userId`, `userName`, `groupId`, `groupName`, or `tenant`.

`--groupId [groupId]`
: The ID of the Microsoft Entra group. Specify either `userId`, `userName`, `groupId`, `groupName`, or `tenant`.

`--groupName [groupName]`
: The name of the Microsoft Entra group. Specify either `userId`, `userName`, `groupId`, `groupName`, or `tenant`.

`--tenant`
: When specifying this, tenant permissions (everyone in the tenant) will be removed. Specify either `userId`, `userName`, `groupId`, `groupName`, or `tenant`.

`--asAdmin`
: Run the command as admin for apps you don't own.

`-e, --environmentName [environmentName]`
: The name of the environment. Specify only a value when running the command as admin.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Remove permissions of a specific user for a specific app

```sh
m365 pa app permission remove --appName bc9f0a7e-53df-46af-b669-5888bb2f63d0 --userName john.doe@contoso.com 
```

Remove permissions of a specific security group for a specific app

```sh
m365 pa app permission remove --appName bc9f0a7e-53df-46af-b669-5888bb2f63d0 --groupName Developers
```

Removes permissions as administrator for an app which you do not own

```sh
m365 pa app permission remove --environment EXAMPLE_SECRET_VALUE_PLACEHOLDER --appName bc9f0a7e-53df-46af-b669-5888bb2f63d0 --userId 42a28ec6-972f-4fdd-b483-50ee4b237f91 --asAdmin
```

Unshare a Power Apps app with the entire tenant

```sh
m365 pa app permission remove --appName bc9f0a7e-53df-46af-b669-5888bb2f63d0 --tenant
```

## Response

The command won't return a response on success.
