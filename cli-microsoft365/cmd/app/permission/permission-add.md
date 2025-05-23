-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# app permission add

Adds the specified application and/or delegated permissions to the current Microsoft Entra app API permissions

## Usage

```sh
m365 app permission add [options]
```

## Options

```md definition-list
`--appId [appId]`
: Client ID of the Microsoft Entra app registered in the .m365rc.json file to retrieve API permissions for.

`--applicationPermissions [applicationPermissions]`
: Space-separated list of application permissions to add.

`--delegatedPermissions [delegatedPermissions]`
: Space-separated list of delegated permissions to add.

`--grantAdminConsent`
: If specified, admin consent to the newly added permissions will be granted.
```

<Global />

## Remarks

If you have multiple apps registered in your .m365rc.json file, you can specify the app for which you'd like to retrieve permissions using the `--appId` option. If you don't specify the app using the `--appId` option, you'll be prompted to select one of the applications from your .m365rc.json file.

## Examples

Adds the specified application permissions to the default app registered in the _.m365rc.json_ file while granting admin consent.

```sh
m365 app permission add --applicationPermissions 'https://graph.microsoft.com/User.ReadWrite.All https://graph.microsoft.com/User.Read.All' --grantAdminConsent
```

Adds the specified delegated permissions to the default app registered in the _.m365rc.json_ file without granting admin consent.

```sh
m365 app permission add --delegatedPermissions 'https://graph.microsoft.com/offline_access'
```

Adds the specified application and delegated permissions to a specific app registered in the _.m365rc.json_ file while granting admin consent.

```sh
m365 app permission add --appId '1663767b-4172-4519-bfd1-28e6ff19055b' --applicationPermissions 'https://graph.microsoft.com/User.ReadWrite.All https://graph.microsoft.com/User.Read.All' --delegatedPermissions 'https://graph.microsoft.com/offline_access' --grantAdminConsent
```

## Response

The command won't return a response on success.
