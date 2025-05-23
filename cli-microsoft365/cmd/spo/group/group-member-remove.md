-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo group member remove

Removes the specified member from a SharePoint group

## Usage

```sh
m365 spo group member remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the SharePoint group is available.

`--groupId [groupId]`
: Id of the SharePoint group from which the user has to be removed. Specify either `groupName` or `groupId`, but not both.

`--groupName  [groupName]`
: Name of the SharePoint group from which user has to be removed. Specify either `groupName` or `groupId`, but not both.

`--userName [userName]`
: The UPN (user principal name, eg. megan.bowen@contoso.com) of the user that needs to be removed. Specify either `userName`, `email`, `userId`, `entraGroupId` or `entraGroupName`.

`--email [email]`
: The email of the user to remove as a member. Specify either `userName`, `email`, `userId`, `entraGroupId` or `entraGroupName`.

`--userId [userId]`
: The user Id (Id of the site user, eg. 14) of the user to remove as a member. Specify either `userName`, `email`, `userId`, `entraGroupId` or `entraGroupName`.

`--entraGroupId [entraGroupId]`
: The object Id of the Entra group to remove as a member. Specify either `userName`, `email`, `userId`, `entraGroupId`, or `entraGroupName`.

`--entraGroupName [entraGroupName]`
: The name of the Entra group to remove as a member. Specify either `userName`, `email`, `userId`, `entraGroupId`, or `entraGroupName`.
```

<Global />

## Examples

Remove a user from a SharePoint group based on the id on a given web.

```sh
m365 spo group member remove --webUrl https://contoso.sharepoint.com/sites/SiteA --groupId 5 --userName "Alex.Wilber@contoso.com"
```

Remove a user from a SharePoint group based on the username on a given web.

```sh
m365 spo group member remove --webUrl https://contoso.sharepoint.com/sites/SiteA --groupName "Site A Visitors" --email "Alex.Wilber@contoso.com"
```

Remove a user from a SharePoint group by email.

```sh
m365 spo group member remove --webUrl https://contoso.sharepoint.com/sites/SiteA --groupName "Site A Visitors" --userId 14
```

Remove an Entra group from a SharePoint group based on the Entra group name on a given web.

```sh
m365 spo group member remove --webUrl https://contoso.sharepoint.com/sites/SiteA --groupId 5 --entraGroupName "Microsoft Entra ID Security Group"
```

Remove an Entra group from a SharePoint group based on the Entra group ID on a given web.

```sh
m365 spo group member remove --webUrl https://contoso.sharepoint.com/sites/SiteA --groupName "Site A Visitors" --entraGroupId "5786b8e8-c495-4734-b345-756733960730"
```

## Response

The command won't return a response on success.
