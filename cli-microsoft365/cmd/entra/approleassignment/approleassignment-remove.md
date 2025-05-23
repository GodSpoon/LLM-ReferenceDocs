-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra approleassignment remove

Deletes an app role assignment for the specified Entra application registration

## Usage

```sh
m365 entra approleassignment remove [options]
```

## Options

```md definition-list
`--appId [appId]`
: Application appId also known as clientId of the App Registration for which the configured scopes (app roles) should be deleted.

`--appObjectId [appObjectId]`
: Application objectId of the App Registration for which the configured scopes (app roles) should be deleted.

`--appDisplayName [appDisplayName]`
: Application name of the App Registration for which the configured scopes (app roles) should be deleted.

`-r, --resource <resource>`
: Service principal name, appId or objectId that has the scopes (roles) e.g. `SharePoint`.

`-s, --scopes <scopes>`
: Permissions known also as scopes and roles to be deleted from the application. If multiple permissions have to be deleted, they have to be comma-separated e.g. `Sites.Read.All`,`Sites.ReadWrite.All`.

`-f, --force`
: Don't prompt for confirming removing the all role assignment.
```

<Global />

## Remarks

This command requires tenant administrator permissions.

Specify either the `appId`, `appObjectId` or `appDisplayName` but not multiple. If you specify more than one option value, the command will fail with an error.

Autocomplete values for the `resource` option do not mean allowed values. The autocomplete will just suggest some known names, but that doesn't restrict you to use name of your own custom application or other application within your tenant.

This command can also be used to assign permissions to system- or user-assigned managed identity.

## Examples

Deletes SharePoint _Sites.Read.All_ application permissions from Entra application with app id _57907bf8-73fa-43a6-89a5-1f603e29e451_

```sh
m365 entra approleassignment remove --appId "57907bf8-73fa-43a6-89a5-1f603e29e451" --resource "SharePoint" --scopes "Sites.Read.All"
```

Deletes multiple Microsoft Graph application permissions from an Entra application with name _MyAppName_

```sh
m365 entra approleassignment remove --appDisplayName "MyAppName" --resource "Microsoft Graph" --scopes "Mail.Read,Mail.Send"
```

Deletes Microsoft Graph _Mail.Read_ application permissions from a system-managed identity app with objectId _57907bf8-73fa-43a6-89a5-1f603e29e451_

```sh
m365 entra approleassignment remove --appObjectId "57907bf8-73fa-43a6-89a5-1f603e29e451" --resource "Microsoft Graph" --scopes "Mail.Read"
```

## Response

The command won't return a response on success.

## More information

- Microsoft Graph permissions reference: [https://learn.microsoft.com/graph/permissions-reference](https://learn.microsoft.com/graph/permissions-reference)
