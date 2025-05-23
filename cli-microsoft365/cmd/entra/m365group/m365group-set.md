-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra m365group set

Updates Microsoft 365 Group properties

## Usage

```sh
m365 entra m365group set [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the Microsoft 365 Group to update.

`-n, --displayName [displayName]`
: Display name of the Microsoft 365 Group to update.

`--newDisplayName [newDisplayName]`
: New display name for the Microsoft 365 Group.

`-d, --description [description]`
: Description for the Microsoft 365 Group.

`--ownerIds [ownerIds]`
: Comma-separated list of IDs of Microsoft Entra ID users that will be group owners. Specify either `ownerIds` or `ownerUserNames`, but not both.

`--ownerUserNames [ownerUserNames]`
: Comma-separated list of UPNs of Microsoft Entra ID users that will be group owners. Specify either `ownerIds` or `ownerUserNames`, but not both.

`--memberIds [memberIds]`
: Comma-separated list of IDs of Microsoft Entra ID users that will be group members. Specify either `memberIds` or `memberUserNames`, but not both.

`--memberUserNames [memberUserNames]`
: Comma-separated list of UPNs of Microsoft Entra ID users that will be group members. Specify either `memberIds` or `memberUserNames`, but not both.

`--isPrivate [isPrivate]`
: Set to `true` if the Microsoft 365 Group should be private and `false` if it should be public.

`-l, --logoPath [logoPath]`
: Local path to the image file to use as group logo.

`--allowExternalSenders [allowExternalSenders]`
: Indicates if people external to the organization can send messages to the group. Valid values: `true`, `false`.

`--autoSubscribeNewMembers [autoSubscribeNewMembers]`
: Indicates if new members added to the group will be auto-subscribed to receive email notifications. Valid values: `true`, `false`.

`--hideFromAddressLists [hideFromAddressLists]`
: Indicates if the group is not displayed in certain parts of the Outlook UI: the Address Book, address lists for selecting message recipients, and the Browse Groups dialog for searching groups. Valid values: `true`, `false`.

`--hideFromOutlookClients [hideFromOutlookClients]`
: Indicates if the group is not displayed in Outlook clients, such as Outlook for Windows and Outlook on the web. Valid values: `true`, `false`.
```

<Global />

## Remarks

When updating group's owners and members, the command will remove existing owners/members from the group, and the specified users will be added.

When specifying the path to the logo image you can use both relative and absolute paths. Note, that ~ in the path, will not be resolved and will most likely result in an error.

:::note

Options `allowExternalSenders` and `autoSubscribeNewMembers` can only be set using delegated permissions.  

:::

## Examples

Update Microsoft 365 Group display name.

```sh
m365 entra m365group set --id 28beab62-7540-4db1-a23f-29a6018a3848 --newDisplayName Finance
```

Change Microsoft 365 Group visibility to public.

```sh
m365 entra m365group set --id 28beab62-7540-4db1-a23f-29a6018a3848 --isPrivate `false`
```

Updates the list of Microsoft 365 Group owners with a list of users by UPN.

```sh
m365 entra m365group set --id 28beab62-7540-4db1-a23f-29a6018a3848 --ownerUserNames "DebraB@contoso.onmicrosoft.com,DiegoS@contoso.onmicrosoft.com"
```

Updates the list of Microsoft 365 Group owners with a list of users by ID.

```sh
m365 entra m365group set --id 28beab62-7540-4db1-a23f-29a6018a3848 --ownerIds "3527dada-9368-4cdd-a958-5460f5658e0e,e94b2cb8-7c9a-4651-b1af-207d81a010b6"
```

Updates the list of Microsoft 365 Group members with a list of users by UPN.

```sh
m365 entra m365group set --id 28beab62-7540-4db1-a23f-29a6018a3848 --memberUserNames "DebraB@contoso.onmicrosoft.com,DiegoS@contoso.onmicrosoft.com"
```

Updates the list of Microsoft 365 Group members with a list of users by ID.

```sh
m365 entra m365group set --id 28beab62-7540-4db1-a23f-29a6018a3848 --memberIds "3527dada-9368-4cdd-a958-5460f5658e0e,e94b2cb8-7c9a-4651-b1af-207d81a010b6"
```

Update Microsoft 365 Group logo.

```sh
m365 entra m365group set --id 28beab62-7540-4db1-a23f-29a6018a3848 --logoPath images/logo.png
```

Hide the Microsoft 365 group from the address lists and the Outlook clients.

```sh
m365 entra m365group set --id 28beab62-7540-4db1-a23f-29a6018a3848 --hideFromOutlookClients true --hideFromAddressLists true
```

Auto-subscribe new members to receive email notifications and do not allow external senders to send messages to the group.

```sh
m365 entra m365group set --id 28beab62-7540-4db1-a23f-29a6018a3848 --autoSubscribeNewMembers true --allowExternalSenders false
```

## Response

The command won't return a response on success.
