-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra oauth2grant remove

Remove specified service principal OAuth2 permissions

## Usage

```sh
m365 entra oauth2grant remove [options]
```

## Options

```md definition-list
`-i, --grantId <grantId>`
: `objectId` of OAuth2 permission grant to remove.

`-f, --force`
: Do not prompt for confirmation before removing OAuth2 permission grant.
```

<Global />

## Remarks

Before you can remove service principal's OAuth2 permissions, you need to get the `objectId` of the permissions grant to remove. You can retrieve it using the [entra oauth2grant list](./oauth2grant-list.mdx) command.

If the `objectId` listed when using the [entra oauth2grant list](./oauth2grant-list.mdx) command has a minus sign ('-') prefix, you may receive an error indicating `--grantId` is missing.  To resolve this issue simply escape the leading '-'.  

```sh
m365 entra oauth2grant remove --grantId \-EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

## Examples

Remove the OAuth2 permission grant with the specified ID.

```sh
m365 entra oauth2grant remove --grantId EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

Remove the OAuth2 permission grant with the specified ID without being asked for confirmation

```sh
m365 entra oauth2grant remove --grantId EXAMPLE_SECRET_VALUE_PLACEHOLDER --force
```

## Response

The command won't return a response on success.

## More information

- Application and service principal objects in Microsoft Entra ID: [https://learn.microsoft.com/azure/active-directory/develop/active-directory-application-objects](https://learn.microsoft.com/azure/active-directory/develop/active-directory-application-objects)
- Delete a delegated permission grant (oAuth2PermissionGrant): [https://learn.microsoft.com/graph/api/oauth2permissiongrant-delete?view=graph-rest-1.0](https://learn.microsoft.com/graph/api/oauth2permissiongrant-delete?view=graph-rest-1.0)
