-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra m365group user set

Updates role of the specified users in the specified Microsoft 365 Group or Microsoft Teams team

## Usage

```sh
m365 entra m365group user set [options]
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
: Microsoft Entra IDs of users. You can also pass a comma-separated list of IDs. Specify only one of the following `ids` or `userNames`.

`--userNames [userNames]`
: The user principal names of users. You can also pass a comma-separated list of UPNs. Specify only one of the following `ids` or `userNames`.

`-r, --role <role>`
: Role to set for the given user in the specified Microsoft 365 Group or Microsoft Teams team. Allowed values: `Owner`, `Member`.
```

<Global />

## Remarks

The command will return an error if the user already has the specified role in the given Microsoft 365 Group or Microsoft Teams team.

## Examples

Promote a single user to Owner of the given Microsoft 365 Group

```sh
m365 entra m365group user set --groupId '00000000-0000-0000-0000-000000000000' --userNames 'anne.matthews@contoso.onmicrosoft.com' --role Owner
```

Promote multiple users specified by the userNames parameter to Owner of the given Microsoft 365 Group

```sh
m365 entra m365group user set --groupName 'Contoso' --userNames 'anne.matthews@contoso.onmicrosoft.com,john.doe@contoso.onmicrosoft.com' --role Owner
```

Promote multiple users specified by the ids parameter to Owner of the given Microsoft 365 Group

```sh
m365 entra m365group user set --groupId '00000000-0000-0000-0000-000000000000' --ids '74a3b772-3122-447b-b9da-10895e238219,dd3d21e4-a142-46b9-8482-bca8fe9596b3' --role Owner
```

Demote a single user from Owner to Member in the given Microsoft 365 Group

```sh
m365 entra m365group user set --groupId '00000000-0000-0000-0000-000000000000' --userNames 'anne.matthews@contoso.onmicrosoft.com' --role Member
```

Demote multiple users specified by the userNames parameter from Owner to Member of the given Microsoft Teams team

```sh
m365 teams user set --teamId '00000000-0000-0000-0000-000000000000' --userNames 'anne.matthews@contoso.onmicrosoft.com,john.doe@contoso.onmicrosoft.com' --role Member
```

Demote multiple users specified by the ids parameter from Owner to Member in the given Microsoft Teams team

```sh
m365 teams user set --teamName 'Engineering' --ids '74a3b772-3122-447b-b9da-10895e238219,dd3d21e4-a142-46b9-8482-bca8fe9596b3' --role Member
```

## Response

The command won't return a response on success.
