-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra m365group user remove

Removes the specified user from specified Microsoft 365 Group or Microsoft Teams team

## Usage

```sh
m365 entra m365group user remove [options]
```

## Options

```md definition-list
`-i, --groupId [groupId]`
: The ID of the Microsoft 365 group. Specify only one of the following: `groupId`, `groupName`, `teamId`, or `teamName`.

`--groupName [groupName]`
: The display name of the Microsoft 365 group. Specify only one of the following: `groupId`, `groupName`, `teamId`, or `teamName`.

`--teamId [teamId]`
: The ID of the Microsoft Teams team. Specify only one of the following: `groupId`, `groupName`, `teamId`, or `teamName`.

`--teamName [teamName]`
: The display name of the Microsoft Teams team. Specify only one of the following: `groupId`, `groupName`, `teamId`, or `teamName`.

`--ids [ids]`
: Microsoft Entra IDs of users. You can also pass a comma-separated list of IDs. Specify either `ids` or `userNames` but not both.

`--userNames [userNames]`
: The user principal names of users. You can also pass a comma-separated list of UPNs. Specify either `ids` or `userNames` but not both.

`-f, --force`
: Don't prompt for confirming removing the user from the specified Microsoft 365 Group or Microsoft Teams team.
```

<Global />

## Remarks

You can remove users from a Microsoft 365 Group or Microsoft Teams team if you are owner of that group or team.

## Examples

Removes user from the specified Microsoft 365 Group.

```sh
m365 entra m365group user remove --groupId '5b8e4cb1-ea40-484b-a94e-02a4313fefb4' --userNames 'anne.matthews@contoso.onmicrosoft.com'
```

Removes user from the specified Microsoft 365 Team specified by id without confirmation.

```sh
m365 entra m365group user remove --teamId '5b8e4cb1-ea40-484b-a94e-02a4313fefb4' --userNames 'anne.matthews@contoso.onmicrosoft.com' --force
```

Removes users specified by a comma separated list of user principal names from the specified Microsoft Teams team specified by name

```sh
m365 entra m365group user remove --teamName 'Project Team' --userNames 'anne.matthews@contoso.onmicrosoft.com,john@contoso.com'
```

Removes users specified by a comma separated list of user ids from the specified Microsoft 365 group specified by name.

```sh
m365 entra m365group user remove --groupName 'Project Team' --ids '5b8e4cb1-ea40-484b-a94e-02a4313fefb4,be7a56d8-b045-4938-af35-917ab6e5309f'
```

## Response

The command won't return a response on success.
