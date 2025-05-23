-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra group set

Updates a Microsoft Entra group

## Usage

```sh
m365 entra group set [options]
```

## Options

```md definition-list
`-i, --id [id]`	
: The ID of the Microsoft Entra group to update. Specify either `id` or `displayName` but not both.

`-n, --displayName [displayName]`	
: The display name of the Microsoft Entra group to update. Specify either `id` or `displayName` but not both.

`--newDisplayName [newDisplayName]`	
: The new display name of the Microsoft Entra group. The maximum length is 256 characters.

`--description [description]`
: The new description for the group.

`--mailNickname [mailNickname]`
: The new mail alias for the group (part before the @). Use only for mail-enabled groups. Maximum length is 64 characters.

`--ownerIds [ownerIds]`
: Comma-separated list of IDs of Microsoft Entra users that will be the group owners. Specify either `ownerIds` or `ownerUserNames`, but not both.

`--ownerUserNames [ownerUserNames]`
: Comma-separated list of UPNs of Microsoft Entra users that will be the group owners. Specify either `ownerIds` or `ownerUserNames`, but not both.

`--memberIds [memberIds]`
: Comma-separated list of IDs of Microsoft Entra users that will be the group members. Specify either `memberIds` or `memberUserNames`, but not both.

`--memberUserNames [memberUserNames]`
: Comma-separated list of UPNs of Microsoft Entra users that will be the group members. Specify either `memberIds` or `memberUserNames`, but not both.

`--visibility [visibility]`
: Specifies the group join policy and group content visibility for Microsoft 365 groups. Possible values are: `Private` or `Public`. Specify only when targeting a Microsoft 365 group.
```

<Global />

## Remarks

The `visibility` option affects the behavior of the group.

With the `Public` visibility:
- Anyone can join the group without needing owner approval. 
- Anyone can view the attributes of the group. 
- Anyone can see the members of the group.

With the `Private` visibilty:
- Owner approval is needed to join the group.
- Anyone can view the attributes of the group.
- Anyone can see the members of the group.

If the specified option is not found, you will receive a `Resource 'xyz' does not exist or one of its queried reference-property objects are not present.` error.

Specifying `memberIds` or `memberUserNames` will make only those users members, removing all others. Similarly, specifying `ownerIds` or `ownerUserNames` will make only those users owners, removing all others.

## Examples

Update the display name of a group specified by the display name

```sh
m365 entra group set --displayName Devs --newDisplayName Developers
```

Set the owners of a group to the specified people

```sh
m365 entra group set --id 57fd6b33-54eb-42b0-9ea0-8a9ac04eab7d --ownerUserNames "john.doe@contoso.com,adele.vance@contoso.com"
```

Update the description and mail nickname of a group

```sh
m365 entra group set --id 57fd6b33-54eb-42b0-9ea0-8a9ac04eab7d --description "All developers of the company" --mailNickname developers
```

## Response

The command won't return a response on success.
