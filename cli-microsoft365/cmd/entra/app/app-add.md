-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra app add

Creates new Entra app registration

## Usage

```sh
m365 entra app add [options]
```

## Alias

```sh
m365 entra appregistration add [options]
```

## Options

```md definition-list
`-n, --name [name]`
: Name of the app. Specify either `name` or `manifest` but not both.

`--multitenant`
: Specify, to make the app available to other tenants.

`-r, --redirectUris [redirectUris]`
: Comma-separated list of redirect URIs. Requires `platform` to be specified.

`-p, --platform [platform]`
: Platform for which the `redirectUris` should be configured. Allowed values `spa`, `web`, `publicClient`. Requires `redirectUris` to be specified.

`--implicitFlow`
: Specify, to indicate that the authorization endpoint should return ID and access tokens.

`-s, --withSecret`
: When specified, will create a secret named `Default` and set it to expire 1 year in the future.

`--apisDelegated [apisDelegated]`
: Comma-separated list of delegated permissions to register with the app.

`--apisApplication [apisApplication]`
: Comma-separated list of application permissions to register with the app.

`-u, --uri [uri]`
: Application ID URI.

`--scopeName [scopeName]`
: Name of the scope to add. Requires `uri` to be specified.

`--scopeConsentBy [scopeConsentBy]`
: Specifies if the scope can be consented only by admins or by admins and users. Allowed values `admins`, `adminsAndUsers`. Default `admins`.

`--scopeAdminConsentDisplayName [scopeAdminConsentDisplayName]`
: Scope admin consent display name.

`--scopeAdminConsentDescription [scopeAdminConsentDescription]`
: Scope admin consent description.

`--certificateFile [certificateFile]`
: Path to the file with certificate public key. Specify either `certificateFile` or `certificateBase64Encoded`.

`--certificateBase64Encoded [certificateBase64Encoded]`
: Base64-encoded string with certificate public key. Specify either `certificateFile` or `certificateBase64Encoded`.

`--certificateDisplayName [certificateDisplayName]`
: Display name for the certificate. If not given, the displayName will be set to the certificate subject. When specified, also specify either `certificateFile` or `certificateBase64Encoded`.

`--grantAdminConsent`
: When specified, grants application & delegated permissions through admin consent.

`--manifest [manifest]`
: App manifest as retrieved from Entra ID to create the app registration from. Specify either `name` or `manifest` but not both.

`--save`
: Use to store the information about the created app in a local file.

`--allowPublicClientFlows`
: Enable the allow public client flows feature on the app registration.
```

<Global />

## Remarks

You can use this command to create a new Entra app registration either by specifying the different configuration settings through the corresponding options or by using the manifest.

If you don't use the manifest, you must specify the name of the Entra app registration using the `name` option. If you use the manifest, you can skip the `name` option assuming the manifest contains the `displayName` property.

You can also use the manifest to provision some of the configuration settings of your Entra app. All properties specified in the manifest are optional and will set if specified.

If you specify the manifest along with some options, values specified in the options will override settings from the manifest. One exception is the name specified in the `name` option which will be overridden by the `displayName` property from the manifest if specified.

The following properties specified in the manifest retrieved from Entra ID are not supported by this command:

- accessTokenAcceptedVersion
- disabledByMicrosoftStatus
- errorUrl
- oauth2RequirePostResponse
- oauth2AllowUrlPathMatching
- orgRestrictions
- samlMetadataUrl

When specifying the value for the `uri`, you can use the `_appId_` token, to include the ID of the newly generated Entra app registration in the Application ID URI, eg. URI `api://caf406b91cd4.ngrok.io/_appId_` will become `api://caf406b91cd4.ngrok.io/EXAMPLE-GUID-PLACEHOLDER` where the last portion is the app ID of the created Entra app registration.

When using the `withSecret` option, this command will automatically generate a secret named `Default` and set it to expire 1 year in the future.

After creating the Entra app registration, this command returns the app ID and object ID of the created app registration. If you used the `withSecret` option, it will also return the generated secret.

If you want to store the information about the created Entra app registration, use the `--save` option. This is useful when you build solutions connected to Microsoft 365 and want to easily manage app registrations used with your solution. When you use the `--save` option, after you create the app registration, the command will write its ID and name to the `.m365rc.json` file in the current directory. If the file already exists, it will add the information about the to it, allowing you to track multiple apps. If the file doesn't exist, the command will create it.

When specifying `--grantAdminConsent` option, an enterprise application will be created for the app registration.

## Examples

Create new Entra app registration with the specified name

```sh
m365 entra app add --name 'My Entra app'
```

Create new Entra app registration from the manifest retrieved from the Azure Portal stored in a local file named _manifest.json_

```sh
m365 entra app add --manifest @manifest.json
```

Create new multitenant Entra app registration

```sh
m365 entra app add --name 'My Entra app' --multitenant
```

Create new Entra app registration for a web app with the specified redirect URIs

```sh
m365 entra app add --name 'My Entra app' --redirectUris 'https://myapp.azurewebsites.net,http://localhost:4000' --platform web
```

Create new Entra app registration for a desktop app

```sh
m365 entra app add --name 'My Entra app' --redirectUris 'https://login.microsoftonline.com/common/oauth2/nativeclient' --platform publicClient
```

Create new Entra app registration with an auto-generated secret (secret returned in the command output)

```sh
m365 entra app add --name 'My Entra app' --withSecret
```

Create new Entra app registration for a daemon app with specified Microsoft Graph application permissions

```sh
m365 entra app add --name 'My Entra app' --withSecret --apisApplication 'https://graph.microsoft.com/Group.ReadWrite.All,https://graph.microsoft.com/Directory.Read.All'
```

Create new Entra app registration for a single-page app with specified Microsoft Graph delegated permissions

```sh
m365 entra app add --name 'My Entra app' --platform spa --redirectUris 'https://myspa.azurewebsites.net,http://localhost:8080' --apisDelegated 'https://graph.microsoft.com/Calendars.Read,https://graph.microsoft.com/Directory.Read.All' --implicitFlow
```

Create new Entra app registration with Application ID URI set to a fixed value

```sh
m365 entra app add --name 'My Entra app' --uri https://contoso.onmicrosoft.com/myapp
```

Create new Entra app registration with Application ID URI set to a value that contains the ID of the app registration, designated with the `_appId_` token and a custom API scope that can be consented by both admins and users

```sh
m365 entra app add --name 'My Entra app' --uri api://caf406b91cd4.ngrok.io/_appId_ --scopeName access_as_user --scopeAdminConsentDescription 'Access as a user' --scopeAdminConsentDisplayName 'Access as a user' --scopeConsentBy adminsAndUsers
```

Create new Entra app registration for a daemon app with specified Microsoft Graph application permissions, including admin consent

```sh
 m365 entra app add --name 'My Entra app' --apisApplication 'https://graph.microsoft.com/Group.ReadWrite.All' --grantAdminConsent
```

Create new Entra app registration with the specified name. Store information about the created app registration in the _.m365rc.json_ file in the current directory.

```sh
m365 entra app add --name 'My Entra app' --save
```

Create new Entra app registration with a certificate

```sh
m365 entra app add --name 'My Entra app' --certificateDisplayName "Some certificate name" --certificateFile "c:	emp\some-certificate.cer"
```

Create a new Entra app registration with the allow public client flows feature enabled.

```sh
m365 entra app add --name 'My Entra app' --allowPublicClientFlows
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "appId": "EXAMPLE-GUID-PLACEHOLDER",
    "objectId": "EXAMPLE-GUID-PLACEHOLDER",
    "tenantId": "EXAMPLE-GUID-PLACEHOLDER"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  appId   : EXAMPLE-GUID-PLACEHOLDER
  objectId: EXAMPLE-GUID-PLACEHOLDER
  tenantId: EXAMPLE-GUID-PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  appId,objectId,tenantId
  EXAMPLE-GUID-PLACEHOLDER,EXAMPLE-GUID-PLACEHOLDER,EXAMPLE-GUID-PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra app add --name "My Entra app"

  Date: 2023-06-01

  ## EXAMPLE-GUID-PLACEHOLDER

  Property | Value
  ---------|-------
  appId | EXAMPLE-GUID-PLACEHOLDER
  objectId | EXAMPLE-GUID-PLACEHOLDER
  tenantId | EXAMPLE-GUID-PLACEHOLDER
  ```

  </TabItem>
</Tabs>

### `withSecret` response

When we make use of the option `withSecret` the response will differ. 

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "appId": "EXAMPLE-GUID-PLACEHOLDER",
    "objectId": "EXAMPLE-GUID-PLACEHOLDER",
    "tenantId": "EXAMPLE-GUID-PLACEHOLDER",
    "secrets": [
      {
        "displayName": "Default",
        "value": "EXAMPLE_SECRET_VALUE_PLACEHOLDER"
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  appId   : EXAMPLE-GUID-PLACEHOLDER
  objectId: EXAMPLE-GUID-PLACEHOLDER
  secrets : [{"displayName":"Default","value":"EXAMPLE_SECRET_VALUE_PLACEHOLDER"}]
  tenantId: EXAMPLE-GUID-PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  appId,objectId,tenantId
  EXAMPLE-GUID-PLACEHOLDER,EXAMPLE-GUID-PLACEHOLDER,EXAMPLE-GUID-PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra app add --name "My Entra app" --withSecret "true"

  Date: 2023-06-01

  ## EXAMPLE-GUID-PLACEHOLDER

  Property | Value
  ---------|-------
  appId | EXAMPLE-GUID-PLACEHOLDER
  objectId | EXAMPLE-GUID-PLACEHOLDER
  tenantId | EXAMPLE-GUID-PLACEHOLDER
  ```

  </TabItem>
</Tabs>
