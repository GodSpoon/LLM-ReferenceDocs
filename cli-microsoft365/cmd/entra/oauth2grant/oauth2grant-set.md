-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra oauth2grant set

Update OAuth2 permissions for the service principal

## Usage

```sh
m365 entra oauth2grant set [options]
```

## Options

```md definition-list
`-i, --grantId <grantId>`
: `objectId` of OAuth2 permission grant to update.

`-s, --scope <scope>`
: Permissions to grant.
```

<Global />

## Remarks

Before you can update service principal's OAuth2 permissions, you need to get the `objectId` of the permissions grant to update. You can retrieve it using the [entra oauth2grant list](./oauth2grant-list.mdx) command.

If the `objectId` listed when using the [entra oauth2grant list](./oauth2grant-list.mdx) command has a minus sign ('-') prefix, you may receive an error indicating `--grantId` is missing. To resolve this issue simply escape the leading '-'.  

```sh
m365 entra oauth2grant set --grantId \-EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

## Examples

Update the existing OAuth2 permission grant with ID EXAMPLE_SECRET_VALUE_PLACEHOLDER to the _Calendars.Read Mail.Read_ permissions.

```sh
m365 entra oauth2grant set --grantId EXAMPLE_SECRET_VALUE_PLACEHOLDER --scope "Calendars.Read Mail.Read"
```

## Response

The command won't return a response on success.

## More information

- Application and service principal objects in Microsoft Entra ID: [https://learn.microsoft.com/azure/active-directory/develop/active-directory-application-objects](https://learn.microsoft.com/azure/active-directory/develop/active-directory-application-objects)
- Update a delegated permission grant (oAuth2PermissionGrant): [https://learn.microsoft.com/graph/api/oauth2permissiongrant-update?view=graph-rest-1.0](https://learn.microsoft.com/graph/api/oauth2permissiongrant-update?view=graph-rest-1.0)
