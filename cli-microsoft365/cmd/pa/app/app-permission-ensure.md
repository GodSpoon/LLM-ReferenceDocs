-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# pa app permission ensure

Assigns/updates permissions to a Power Apps app

## Usage

```sh
m365 pa app permission ensure [options]
```

## Options

```md definition-list
`--appName <appName>`
: The name (GUID) of the Microsoft Power App.

`--roleName <roleName>`
: Permission level given to the app. Valid values: `CanEdit`, `CanView`. Sharing with the entire tenant is only supported with `CanView` role.

`--userId [userId]`
: The ID of the Microsoft Entra user. Specify either `userId`, `userName`, `groupId`, `groupName`, or `tenant`.

`--userName [userName]`
: The user principal name of the user. Specify either `userId`, `userName`, `groupId`, `groupName`, or `tenant`.

`--groupId [groupId]`
: The ID of the Microsoft Entra group. Specify either `userId`, `userName`, `groupId`, `groupName`, or `tenant`.

`--groupName [groupName]`
: The name of the Microsoft Entra group. Specify either `userId`, `userName`, `groupId`, `groupName`, or `tenant`.

`--tenant`
: Share the app with the entire tenant. When specifying this, only `CanView` role is supported. Specify either `userId`, `userName`, `groupId`, `groupName`, or `tenant`.

`--sendInvitationMail`
: When set, an invitation mail will be sent.

`--asAdmin`
: Run the command as admin for apps you don't own.

`-e, --environmentName [environmentName]`
: The name of the environment. Specify only a value when running the command as admin.
```

<Global />

## Remarks

:::note

When specifying a value for `groupId` or `groupName`, note that you can only grant permissions to security groups.

:::

## Examples

Share a Power App app with another user with run-only permissions

```sh
m365 pa app permission ensure --appName bc9f0a7e-53df-46af-b669-5888bb2f63d0 --userName john.doe@contoso.com --roleName CanView --sendInvitationMail
```

Add co-owner permissions for a security group to a Power Apps app

```sh
m365 pa app permission ensure --appName bc9f0a7e-53df-46af-b669-5888bb2f63d0 --groupName Developers --roleName CanEdit
```

Add permissions as admin to a Power App app that you do not own

```sh
m365 pa app permission ensure --environment EXAMPLE_SECRET_VALUE_PLACEHOLDER --appName bc9f0a7e-53df-46af-b669-5888bb2f63d0 --userId 42a28ec6-972f-4fdd-b483-50ee4b237f91 --roleName CanEdit --asAdmin
```

Share a Power Apps app with everyone in the tenant

```sh
m365 pa app permission ensure --appName bc9f0a7e-53df-46af-b669-5888bb2f63d0 --roleName CanView --tenant
```

## Response

The command won't return a response on success.
