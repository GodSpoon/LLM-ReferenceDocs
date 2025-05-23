-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage community user remove

Removes a specified user from a Microsoft 365 Viva Engage community

## Usage

```sh
m365 viva engage community user remove [options]
```

## Options

```md definition-list
`-i, --communityId [communityId]`
: The ID of the Viva Engage community. Specify `communityId`, `communityDisplayName` or `entraGroupId`.

`-n, --communityDisplayName [communityDisplayName]`
: The display name of the Viva Engage community. Specify `communityId`, `communityDisplayName` or `entraGroupId`.

`--entraGroupId [entraGroupId]`
: The ID of the Microsoft 365 group. Specify `communityId`, `communityDisplayName` or `entraGroupId`.

`--id [id]`
: Microsoft Entra ID of the user. Specify either `id` or `userName` but not both.

`--userName [userName]`
: The user principal name of the user. Specify either `id` or `userName` but not both.

`-f, --force`
: Don't prompt for confirming removing the user from the specified Viva Engage community.
```

<Global />

## Examples

Remove a user specified by ID as a member from a community specified by display name.

```sh
m365 viva engage community user remove --communityDisplayName "All company" --id 098b9f52-f48c-4401-819f-29c33794c3f5
```

Remove a user specified by UPN from a community specified by its group ID without confirmation.

```sh
m365 viva engage community user remove --entraGroupId a03c0c35-ef9a-419b-8cab-f89e0a8d2d2a --userName john.doe@contoso.com --force
```

## Response

The command won't return a response on success.
