-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo user remove

Removes user from specific web

## Usage

```sh
m365 spo user remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the web to remove user.

`--id [id]`
: ID of the user to remove from web. Use either `id` or `loginName` or `email`, `userName`, `entraGroupId`, or `entraGroupName`, but not all.

`--loginName [loginName]`
: Login name of the user to remove from web. Use either `id` or `loginName` or `email`, `userName`, `entraGroupId`, or `entraGroupName`, but not all.

`--userName [userName]`
: User name of the user to remove from web. Use either `id` or `loginName` or `email`, `userName`, `entraGroupId`, or `entraGroupName`, but not all.

`--email [email]`
: Email of the user to remove from web. Use either `id` or `loginName` or `email`, `userName`, `entraGroupId`, or `entraGroupName`, but not all.

`--entraGroupId [entraGroupId]`
: Object ID of the Entra group ID to remove. Use either `id` or `loginName` or `email`, `userName`, `entraGroupId`, or `entraGroupName`, but not all.

`--entraGroupName [entraGroupName]`
: Name of the Entra group to remove. Use either `id` or `loginName` or `email`, `userName`, `entraGroupId`, or `entraGroupName`, but not all.

`-f, --force`
: Do not prompt for confirmation before removing user from web
```

<Global />

## Examples

Removes user by id from a web without prompting for confirmation

```sh
m365 spo user remove --webUrl "https://contoso.sharepoint.com/sites/HR" --id 10 --force
```

Removes user by loginName from a web

```sh
m365 spo user remove --webUrl "https://contoso.sharepoint.com/sites/HR" --loginName "i:0#.f|membership|john.doe@mytenant.onmicrosoft.com"
```

Removes user by userName from a web

```sh
m365 spo user remove --webUrl "https://contoso.sharepoint.com/sites/HR" --userName "john.doe_hotmail.com#ext#@mytenant.onmicrosoft.com"
```

Removes user by email from a web

```sh
m365 spo user remove --webUrl "https://contoso.sharepoint.com/sites/HR" --email "john.doe@mytenant.onmicrosoft.com"
```

Removes user by entraGroupId from a web

```sh
m365 spo user remove --webUrl "https://contoso.sharepoint.com/sites/HR" --entraGroupId f832a493-de73-4fef-87ed-8c6fffd91be6
```

Removes user by entraGroupName from a web

```sh
m365 spo user remove --webUrl _https://contoso.sharepoint.com/sites/HR_ --entraGroupName "Test Members"
```
## Response

The command won't return a response on success.

## More information

- Remove-PnPUser - [https://learn.microsoft.com/powershell/module/sharepoint-pnp/remove-pnpuser?view=sharepoint-ps](https://learn.microsoft.com/powershell/module/sharepoint-pnp/remove-pnpuser?view=sharepoint-ps)
