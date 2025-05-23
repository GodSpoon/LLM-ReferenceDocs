-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra oauth2grant add

Grant the specified service principal OAuth2 permissions to the specified resource

## Usage

```sh
m365 entra oauth2grant add [options]
```

## Options

```md definition-list
`-i, --clientId <clientId>`
: `objectId` of the service principal for which permissions should be granted.

`-r, --resourceId <resourceId>`
: `objectId` of the Entra application to which permissions should be granted.

`-s, --scope <scope>`
: Permissions to grant.
```

<Global />

## Remarks

Before you can grant service principal OAuth2 permissions, you need its `objectId`. You can retrieve it using the [entra enterpriseapp get](../enterpriseapp/enterpriseapp-get.mdx) command.

The resource for which you want to grant permissions is designated using its `objectId`. You can retrieve it using the [entra enterpriseapp get](../enterpriseapp/enterpriseapp-get.mdx) command, the same way you would retrieve the `objectId` of the service principal.

When granting OAuth2 permissions, you have to specify which permission scopes you want to grant the service principal. You can get the list of available permission scopes either from the resource documentation or from the `appRoles` property when retrieving information about the service principal using the [entra enterpriseapp get](../enterpriseapp/enterpriseapp-get.mdx) command. Multiple permission scopes can be specified separated by a space.

When granting OAuth2 permissions, the values of the `clientId` and `resourceId` properties form a unique key. If a grant for the same `clientId`-`resourceId` pair already exists, running the `entra oauth2grant add` command will fail with an error. If you want to change permissions on an existing OAuth2 grant use the [entra oauth2grant set](./oauth2grant-set.mdx) command instead.

## Examples

Grant the service principal _d03a0062-1aa6-43e1-8f49-d73e969c5812_ the _Calendars.Read_ OAuth2 permissions to the _c2af2474-2c95-423a-b0e5-e4895f22f9e9_ resource.

```sh
m365 entra oauth2grant add --clientId d03a0062-1aa6-43e1-8f49-d73e969c5812 --resourceId c2af2474-2c95-423a-b0e5-e4895f22f9e9 --scope Calendars.Read
```

Grant the service principal _d03a0062-1aa6-43e1-8f49-d73e969c5812_ the _Calendars.Read_ and _Mail.Read_ OAuth2 permissions to the _c2af2474-2c95-423a-b0e5-e4895f22f9e9_ resource.

```sh
m365 entra oauth2grant add --clientId d03a0062-1aa6-43e1-8f49-d73e969c5812 --resourceId c2af2474-2c95-423a-b0e5-e4895f22f9e9 --scope "Calendars.Read Mail.Read"
```

## Response

The command won't return a response on success.

## More information

- Application and service principal objects in Microsoft Entra ID: [https://learn.microsoft.com/azure/active-directory/develop/active-directory-application-objects](https://learn.microsoft.com/azure/active-directory/develop/active-directory-application-objects)
