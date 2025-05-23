-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra administrativeunit member add

Add a member (user, group, or device) to an administrative unit

## Usage

```sh
m365 entra administrativeunit member add [options]
```

## Options

```md definition-list
`-i, --administrativeUnitId [administrativeUnitId]`
: The id of the administrative unit. Specify either `administrativeUnitId` or `administrativeUnitName` but not both.

`-n, --administrativeUnitName [administrativeUnitName]`
: The name of the administrative unit. Specify either `administrativeUnitId` or `administrativeUnitName` but not both.

`--userId [userId]`
: The id of the user to be added. Specify `userId`, `userName`, `groupId`, `groupName`, `deviceId` or `deviceName`.

`--userName [userName]`
: The user principal name (UPN) of the user to be added. Specify `userId`, `userName`, `groupId`, `groupName`, `deviceId` or `deviceName`.

`--groupId [groupId]`
: The id of the group to be added. Specify `userId`, `userName`, `groupId`, `groupName`, `deviceId` or `deviceName`.

`--groupName [groupName]`
: The name of the group to be added. Specify `userId`, `userName`, `groupId`, `groupName`, `deviceId` or `deviceName`.

`--deviceId [deviceId]`
: The id of the device to be added. Specify `userId`, `userName`, `groupId`, `groupName`, `deviceId` or `deviceName`.

`--deviceName [deviceName]`
: The name of the device to be added. Specify `userId`, `userName`, `groupId`, `groupName`, `deviceId` or `deviceName`.
```

<Global />

## Remarks

:::info

To use this command you must be either **Global Administrator** or **Privileged Role Administrator**.

:::

## Examples

Add a single user specified by id to an administrative unit specified by id

```sh
m365 entra administrativeunit member add --administrativeUnitId 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7 --userId 1caf7dcd-7e83-4c3a-94f7-932a1299c844
```

Add a single user specified by user principal name to an administrative unit specified by name

```sh
m365 entra administrativeunit member add --administrativeUnitName 'Marketing Division' --userName john.doe@contoso.com
```

Add a single group specified by id to an administrative unit specified by id

```sh
m365 entra administrativeunit member add --administrativeUnitId 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7 --groupId b2307a39-e878-458b-bc90-03bc578531d6
```

Add a single group specified by name to an administrative unit specified by name

```sh
m365 entra administrativeunit member add --administrativeUnitName 'Marketing Division' --groupName 'Marketing Group'
```

Add a single device specified by id to an administrative unit specified by id

```sh
m365 entra administrativeunit member add --administrativeUnitId 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7 --deviceId 810c84a8-4a9e-49e6-bf7d-12d183f40d01
```

Add a single device specified by name to an administrative unit specified by name

```sh
m365 entra administrativeunit member add --administrativeUnitName 'Marketing Division' --deviceName 'JohnDoe-PC'
```

## Response 

The command won't return a response on success.

## More information

- Administrative units: https://learn.microsoft.com/entra/identity/role-based-access-control/administrative-units
