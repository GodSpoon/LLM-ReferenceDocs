-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra administrativeunit member remove

Removes a member (user, group, or device) from an administrative unit

## Usage

```sh
m365 entra administrativeunit member remove [options]
```

## options

```md definition-list
`-i, --id [id]`
: The id of the member to be removed. Specify either `id`, `userId`, `userName`, `groupId`, `groupName`, `deviceId` or `deviceName`.

`--userId [userId]`
: The id of the user to be removed. Specify either `id`, `userId`, `userName`, `groupId`, `groupName`, `deviceId` or `deviceName`.

`--userName [userName]`
: The user principal name (UPN) of the user to be removed. Specify either `id`, `userId`, `userName`, `groupId`, `groupName`, `deviceId` or `deviceName`.

`--groupId [groupId]`
: The id of the group to be removed. Specify either `id`, `userId`, `userName`, `groupId`, `groupName`, `deviceId` or `deviceName`.

`--groupName [groupName]`
: The name of the group to be removed. Specify either `id`, `userId`, `userName`, `groupId`, `groupName`, `deviceId` or `deviceName`.

`--deviceId [deviceId]`
: The id of the device to be removed. Specify either `id`, `userId`, `userName`, `groupId`, `groupName`, `deviceId` or `deviceName`.

`--deviceName [deviceName]`
: The name of the device to be removed. Specify either `id`, `userId`, `userName`, `groupId`, `groupName`, `deviceId` or `deviceName`.

`--administrativeUnitId [administrativeUnitId]`
: The id of the administrative unit. Specify either `administrativeUnitId` or `administrativeUnitName` but not both.

`--administrativeUnitName [administrativeUnitName]`
: The name of the administrative unit. Specify either `administrativeUnitId` or `administrativeUnitName` but not both.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::info

To use this command you must be either **Global Administrator** or **Privileged Role Administrator**.

:::

## Examples

Remove a member specified by id from an administrative unit specified by id

```sh
m365 entra administrativeunit member remove --id 64131a70-beb9-4ccb-b590-4401e58446ec --administrativeUnitId 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7
```

Remove a user specified by id from an administrative unit specified by id

```sh
m365 entra administrativeunit member remove --userId 64131a70-beb9-4ccb-b590-4401e58446ec --administrativeUnitId 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7
```

Remove a group specified by id from an administrative unit specified by id

```sh
m365 entra administrativeunit member remove --groupId b2307a39-e878-458b-bc90-03bc578531d6 --administrativeUnitId 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7
```

Remove a device specified by id from an administrative unit specified by id

```sh
m365 entra administrativeunit member remove --deviceId 810c84a8-4a9e-49e6-bf7d-12d183f40d01 --administrativeUnitId 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7
```

Remove a user specified by UPN from an administrative unit specified by name

```sh
m365 entra administrativeunit member remove --userName john.doe@contoso.com --administrativeUnitName 'Marketing Division'
```

Remove a group specified by name from an administrative unit specified by id

```sh
m365 entra administrativeunit member remove --groupName 'Marketing Group' --administrativeUnitId 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7
```

Remove a device specified by name from an administrative unit specified by name

```sh
m365 entra administrativeunit member remove --deviceName 'JohnDoe-PC' --administrativeUnitName 'Marketing Division'
```

## Response

The command won't return a response on success

## More information

- [Administrative units](https://learn.microsoft.com/entra/identity/role-based-access-control/administrative-units)
