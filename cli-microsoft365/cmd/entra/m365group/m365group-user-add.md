-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra m365group user add

Adds user to specified Microsoft 365 Group or Microsoft Teams team

## Usage

```sh
m365 entra m365group user add [options]
```

## Alias

```sh
m365 teams user add [options]
```

## Options

```md definition-list
`-i, --groupId [groupId]`
: The ID of the Microsoft 365 group. Specify only one of the following: `groupId`, `groupName`, `teamId`, or `teamName`.

`--groupName [groupName]`
: The display name of the Microsoft 365 group. Specify only one of the following: `groupId`, `groupName`, `teamId`, or `teamName`.

`--teamId [teamId]`
: The ID of the Teams team. Specify only one of the following: `groupId`, `groupName`, `teamId`, or `teamName`.

`--teamName [teamName]`
: The display name of the Microsoft Teams team. Specify only one of the following: `groupId`, `groupName`, `teamId`, or `teamName`.

`--ids [ids]`
: Microsoft Entra IDs of users. You can also pass a comma-separated list of IDs. Specify either `ids` or `userNames` but not both.

`--userNames [userNames]`
: The user principal names of users. You can also pass a comma-separated list of UPNs. Specify either `ids` or `userNames` but not both.

`-r, --role [role]`
: The role to be assigned to the new user. Allowed values: `Owner`, `Member`. Default `Member`.
```

<Global />

## Examples

Add a new member with the userNames parameter to the specified Microsoft 365 Group.

```sh
m365 entra m365group user add --groupId '00000000-0000-0000-0000-000000000000' --userNames 'anne.matthews@contoso.onmicrosoft.com'
```

Add multiple new owners with the userNames parameter to the specified Microsoft 365 Group.

```sh
m365 entra m365group user add --groupName 'Contoso' --userNames 'anne.matthews@contoso.onmicrosoft.com, john.doe@contoso.onmicrosoft.com' --role Owner
```

Add a new member with the userNames parameter to the specified Microsoft Teams team.

```sh
m365 entra m365group member add --teamId '00000000-0000-0000-0000-000000000000' --userNames 'anne.matthews@contoso.onmicrosoft.com' --role Member
```

Add multiple new members with the ids parameter to the specified Microsoft Teams team.

```sh
m365 entra m365group user add --teamName 'Engineering' --ids '74a3b772-3122-447b-b9da-10895e238219,dd3d21e4-a142-46b9-8482-bca8fe9596b3' --role Member
```

## Response

The command won't return a response on success.
