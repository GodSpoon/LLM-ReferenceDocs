-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage community user add

Adds a user to a specific Microsoft 365 Viva Engage community

## Usage

```sh
m365 viva engage community user add [options]
```

## Options

```md definition-list
`-i, --communityId [communityId]`
: The ID of the Viva Engage community. Specify `communityId`, `communityDisplayName` or `entraGroupId`.

`-n, --communityDisplayName [communityDisplayName]`
: The display name of the Viva Engage community. Specify `communityId`, `communityDisplayName` or `entraGroupId`.

`--entraGroupId [entraGroupId]`
: The ID of the Microsoft 365 group. Specify `communityId`, `communityDisplayName` or `entraGroupId`.

`--ids [ids]`
: Microsoft Entra IDs of users. You can pass a comma-separated list of multiple IDs. Specify either `ids` or `userNames` but not both.

`--userNames [userNames]`
: The user principal names of users. You can pass a comma-separated list of multiple UPNs. Specify either `ids` or `userNames` but not both.

`-r, --role <role>`
: The role to be assigned to the new users. Valid values: `Admin`, `Member`.
```

<Global />

## Examples

Add a single user specified by ID as a member to a community specified by display name.

```sh
m365 viva engage community user add --communityDisplayName "All company" --ids 098b9f52-f48c-4401-819f-29c33794c3f5 --role Member
```

Add multiple users specified by ID as members to a community specified by ID.

```sh
m365 viva engage community user add --communityId EXAMPLE_SECRET_VALUE_PLACEHOLDER --ids "098b9f52-f48c-4401-819f-29c33794c3f5,f1e06e31-3abf-4746-83c2-1513d71f38b8" --role Member
```

Add a single user specified by UPN as an admin to a community specified by display name.

```sh
m365 viva engage community user add --communityDisplayName "All company" --userNames john.doe@contoso.com --role Admin
```

Adds multiple users specified by UPN as admins to a community specified by its group ID.

```sh
m365 viva engage community user add --entraGroupId a03c0c35-ef9a-419b-8cab-f89e0a8d2d2a --userNames "john.doe@contoso.com,adele.vance@contoso.com" --role Admin
```

## Response

The command won't return a response on success.
