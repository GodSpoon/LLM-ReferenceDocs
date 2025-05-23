-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra group member set

Updates role of members in a Microsoft Entra ID group

## Usage

```sh
m365 entra group member set [options]
```

## Options

```md definition-list
`-i, --groupId [groupId]`
: The ID of the Entra ID group. Specify `groupId`, `groupDisplayName` or `groupName` but not multiple.

`-n, --groupDisplayName [groupDisplayName]`
: (deprecated. Use option `groupName` instead) The display name of the Entra ID group. Specify `groupId`, `groupDisplayName` or `groupName` but not multiple.

`--groupName [groupName]`
: The display name of the Microsoft Entra group. Specify `groupId`, `groupDisplayName` or `groupName` but not multiple.

`--ids [ids]`
: Comma-separated list of user IDs. Specify either `ids` or `userNames` but not both.

`--userNames [userNames]`
: The user principal names of users. You can also pass a comma-separated list of UPNs. Specify either `ids` or `userNames` but not both.

`-r, --role <role>`
: The new role to be assigned to the members. Valid values: `Owner`, `Member`.
```

<Global />

## Examples

Update a single member specified by ID to a member of a group specified by display name

```sh
m365 entra group member set --groupDisplayName Developers --ids 098b9f52-f48c-4401-819f-29c33794c3f5 --role Member
```

Update a single member specified by ID to a member of a group specified by group name

```sh
m365 entra group member set --groupName Developers --ids 098b9f52-f48c-4401-819f-29c33794c3f5 --role Member
```

Update multiple members specified by ID to members of a group specified by ID

```sh
m365 entra group member set --groupId a03c0c35-ef9a-419b-8cab-f89e0a8d2d2a --ids "098b9f52-f48c-4401-819f-29c33794c3f5,f1e06e31-3abf-4746-83c2-1513d71f38b8" --role Member
```

Update a single member specified by UPN to an owner of a group specified by display name

```sh
m365 entra group member set --groupDisplayName Developers --userNames john.doe@contoso.com --role Owner
```

Update a single member specified by UPN to an owner of a group specified by group name

```sh
m365 entra group member set --groupName Developers --userNames john.doe@contoso.com --role Owner
```

Update multiple members specified by UPN to owners of a group specified by ID

```sh
m365 entra group member set --groupId a03c0c35-ef9a-419b-8cab-f89e0a8d2d2a --userNames "john.doe@contoso.com,adele.vance@contoso.com" --role Owner
```

## Response

The command won't return a response on success.
