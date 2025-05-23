-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra app permission remove

Removes the specified application and/or delegated permissions from a specified Entra app.

## Usage

```sh
m365 entra app permission remove [options]
```

## Options

```md definition-list
`-i, --appId [appId]`
: Client ID of the Microsoft Entra app to remove the API permissions from. Specify either `appId`, `appName` or `appObjectId`.

`--appObjectId [appObjectId]`
: Object ID of the Microsoft Entra app to remove the API permissions from. Specify either `appId`, `appName` or `appObjectId`.

`-n, --appName [appName]`
: Display name of the Entra app to remove the API permissions from. Specify either `appId`, `appName` or `appObjectId`.

`-a, --applicationPermissions [applicationPermissions]`
: Space-separated list of application permissions to remove. Specify at least `applicationPermissions` or `delegatedPermissions`.

`-d, --delegatedPermissions [delegatedPermissions]`
: Space-separated list of delegated permissions to remove. Specify at least `applicationPermissions` or `delegatedPermissions`.

`--revokeAdminConsent`
: When specified, revokes the admin consent for the specified permissions as well.

`-f, --force`
: Don't prompt for confirmation to remove the permissions.
```

<Global />

## Remarks

Removing permissions on App Registrations does not immediately remove consent given by an administrator. Explicitly instruct the CLI to revoke consent by using the `--revokeAdminConsent` flag.

## Examples

Remove multiple delegated API permissions from an Entra app registration

```sh
m365 entra app permission remove --appId 'f1417aa3-bf0b-4cc5-a845-a0b2cf11f690' --delegatedPermissions 'https://management.azure.com/user_impersonation https://service.flow.microsoft.com/Flows.Read.All https://graph.microsoft.com/Agreement.Read.All'
```

Remove multiple app-only permissions from an Entra app registration and revoke admin consent

```sh
m365 entra app permission remove --appId 'f1417aa3-bf0b-4cc5-a845-a0b2cf11f690' --applicationPermissions 'https://graph.microsoft.com/Sites.FullControl.All https://microsoft.sharepoint-df.com/Sites.FullControl.All' --revokeAdminConsent
```

## Response

The command won't return a response on success.
