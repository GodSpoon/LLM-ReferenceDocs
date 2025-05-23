-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# login

Log in to Microsoft 365

## Usage

```sh
m365 login [options]
```

## Options

```md definition-list
`--appId [appId]`
: App ID of the Microsoft Entra application to use for authentication. This option is crucial and should be specified if it isn't defined elsewhere.

`--tenant [tenant]`
: ID of the tenant from which accounts should authenticate. Use `common` or `organization` for multitenant apps. Defaults to `common` if not specified and if the config value `tenantId` and the environment variable `CLIMICROSOFT365_TENANT` are also not set.

`-t, --authType [authType]`
: The type of authentication to use. Allowed values `certificate`, `deviceCode`, `password`, `identity`, `federatedIdentity`, `browser`, `secret`. Default `deviceCode`

`-u, --userName [userName]`
: Name of the user to authenticate. Required when `authType` is set to `password`

`-p, --password [password]`
: Password for the user or the certificate. Required when `authType` is set to `password`, or when `authType` is set to `certificate` and the provided certificate requires a password to open

`-c, --certificateFile [certificateFile]`
: Path to the file with certificate private key. When `authType` is set to `certificate`, specify either `certificateFile` or `certificateBase64Encoded`

`--certificateBase64Encoded [certificateBase64Encoded]`
: Base64-encoded string with certificate private key. When `authType` is set to `certificate`, specify either `certificateFile` or `certificateBase64Encoded`

`--thumbprint [thumbprint]`
: Certificate thumbprint. If not specified, and `authType` is set to `certificate`, it will be automatically calculated based on the specified certificate

`-s, --secret [secret]`
: Client Secret of the Microsoft Entra application to use for authentication. Required when `authType` is set to `secret`.

`--cloud [cloud]`
: Cloud to connect to. Allowed values `Public`, `USGov`, `USGovHigh`, `USGovDoD` and `China`. Default `Public`

`--connectionName [connectionName]`
: Specify an optional name to make switching between connections easier.

`--ensure`
: Ensures that the user is signed in. if the user isn't signed in, it initiates the login flow
```

<Global />

## Remarks

:::tip

The CLI determines the `appId` and `tenant` values in the following order of precedence:

1. The `appId` or `tenant` option specified during login.
2. The `clientId` or `tenantId` value set in the configuration.
3. The `CLIMICROSOFT365_ENTRAAPPID` or `CLIMICROSOFT365_TENANT` environment variable.

For `appId`, it is **required** that at least one of the options is specified during login.

For `tenant`, if none are specified, the CLI will default to `common`.

:::

Using the `login` command you can log in to Microsoft 365.

By default, the `login` command uses device code OAuth flow to log in to Microsoft 365. Alternatively, you can authenticate using a user name and password or certificate, which are convenient for CI/CD scenarios, but which come with their own [limitations](../user-guide/connecting-microsoft-365.mdx). The default `authType` can be configured using `m365 cli config set`. This means you'll be able to run `m365 login` without specifying the `--authType` option.

When logging in to Microsoft 365 using the user name and password, next to the access and refresh token, the CLI for Microsoft 365 will store the user credentials so that it can automatically re-authenticate if necessary. Similarly to the tokens, the credentials are removed by re-authenticating using the device code or by calling the [logout](logout.mdx) command.

When logging in to Microsoft 365 using a certificate, the CLI for Microsoft 365 will store the contents of the certificate so that it can automatically re-authenticate if necessary. The contents of the certificate are removed by re-authenticating using the device code or by calling the [logout](logout.mdx) command.  

Federated Identity is currently supported in GitHub Actions. To use this you need to set `authType` to `federatedIdentity` and specify `appId` and `tenant` to the values of the app registration you've configured a federated credential on. 

To log in to Microsoft 365 using a certificate or secret, you will typically [create a custom Microsoft Entra application](../user-guide/using-own-identity.mdx). To use this application with the CLI for Microsoft 365, you will set the `CLIMICROSOFT365_ENTRAAPPID` environment variable to the application's ID and the `CLIMICROSOFT365_TENANT` environment variable to the ID of the Microsoft Entra tenant, where you created the Microsoft Entra application. Also, please make sure to read about [the caveats when using the certificate login option](../user-guide/cli-certificate-caveats.mdx).

Managed identity in Azure Cloud Shell is the identity of the user. It is neither system- nor user-assigned and it can't be configured. To log in to Microsoft 365 using managed identity in Azure Cloud Shell, set `authType` to `identity` and don't specify the `userName` option.

When connecting to clouds other than `Public`, you'll need to use a Microsoft Entra application registered in a directory provisioned in that cloud. If you try to login using the default Microsoft Entra application, login will fail.

:::tip

When signing in with multiple identities, every signin will be saved as a connection. You can list available connections using [m365 connection list](./connection/connection-list.mdx) and switch between connections using [m365 connection use](./connection/connection-use.mdx) 

:::

## Examples

Log in to Microsoft 365 using the device code.

```sh
m365 login --appId 31359c7f-bd7e-475c-86db-fdb8c937548e
```

Log in to Microsoft 365 using the device code and set the connection name.

```sh
m365 login --connectionName 'myworkaccount' --appId 31359c7f-bd7e-475c-86db-fdb8c937548e
```

Log in to Microsoft 365 using your own Microsoft Entra application that's restricted only to allow accounts from the specific tenant.

```sh
m365 login --appId 31359c7f-bd7e-475c-86db-fdb8c937548c --tenant 31359c7f-bd7e-475c-86db-fdb8c937548a
```

Log in to Microsoft 365 using your own Microsoft Entra application and a personal information exchange (.pfx) file.

```sh
m365 login --authType certificate --appId 31359c7f-bd7e-475c-86db-fdb8c937548c --tenant 31359c7f-bd7e-475c-86db-fdb8c937548a --certificateFile /Users/user/dev/localhost.pfx --password 'pass@word1'
```

Log in to Microsoft 365 using a user name and password with `clientId` set in the configuration.

```sh
m365 login --authType password --userName user@contoso.com --password pass@word1
```

Log in to Microsoft 365 using a PEM certificate with `clientId` set in the configuration.

```sh
m365 login --authType certificate --certificateFile /Users/user/dev/localhost.pem
```

Log in to Microsoft 365 using a PEM certificate with `clientId` set in the configuration. Use the specified thumbprint.

```sh
m365 login --authType certificate --certificateFile /Users/user/dev/localhost.pem  --thumbprint EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

Log in to Microsoft 365 using a personal information exchange (.pfx) file with `CLIMICROSOFT365_ENTRAAPPID` environment variable set.

```sh
m365 login --authType certificate --certificateFile /Users/user/dev/localhost.pfx --password 'pass@word1'
```

Log in to Microsoft 365 using a personal information exchange (.pfx) file protected with an empty password and `CLIMICROSOFT365_ENTRAAPPID` environment variable set.

```sh
m365 login --authType certificate --certificateFile /Users/user/dev/localhost.pfx --password
```

Log in to Microsoft 365 using a personal information exchange (.pfx) file not protected with a password and `CLIMICROSOFT365_ENTRAAPPID` environment variable set.

```sh
m365 login --authType certificate --certificateFile /Users/user/dev/localhost.pfx
```

Log in to Microsoft 365 using a personal information exchange (.pfx) file. Use the specified thumbprint and `CLIMICROSOFT365_ENTRAAPPID` environment variable set.

```sh
m365 login --authType certificate --certificateFile /Users/user/dev/localhost.pfx --thumbprint EXAMPLE_SECRET_VALUE_PLACEHOLDER --password 'pass@word1'
```

Log in to Microsoft 365 using a certificate from a base64-encoded string with `CLIMICROSOFT365_ENTRAAPPID` environment variable set.

```sh
m365 login --authType certificate --certificateBase64Encoded EXAMPLE_SECRET_VALUE_PLACEHOLDER== --thumbprint EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

Log in to Microsoft 365 using a system assigned managed identity with `clientId` set in the configuration. Applies to Azure resources with managed identity enabled, such as Azure Virtual Machines, Azure App Service or Azure Functions.

```sh
m365 login --authType identity
```

Log in to Microsoft 365 using managed identity in Azure Cloud Shell with `clientId` set in the configuration. Uses the identity of the current user.

```sh
m365 login --authType identity
```

Log in to Microsoft 365 using a user-assigned managed identity with `clientId` set in the configuration. Client id or principal id also known as object id value can be specified in the `userName` option. Applies to Azure resources with managed identity enabled, such as Azure Virtual Machines, Azure App Service or Azure Functions.

```sh
m365 login --authType identity --userName ac9fbed5-804c-4362-a369-21a4ec51109e
```

Log in to Microsoft 365 using a federated identity. Can currently only be used in GitHub Actions.

```sh
m365 login --authType federatedIdentity --appId eb96cfd0-abfa-4477-8d1d-c6dfde3efb19 --tenant 9a1a1bbd-e158-4cf5-967d-a53b8e85c628
```

Log in to Microsoft 365 using the interactive browser authentication with `clientId` set in the configuration. Uses the identity of the current user.

```sh
m365 login --authType browser
```

Log in to Microsoft 365 using a client secret with `clientId` set in the configuration.

```sh
m365 login --authType secret --secret topSeCr3t@007
```

Ensures that the user is signed in, initiates the login flow if the user isn't signed in

```sh
m365 login --ensure
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  To sign in, use a web browser to open the page https://microsoft.com/devicelogin and enter the code CQBMTLEFC to authenticate.
  ```
  Upon successful login:
  ```json
  {
    "connectionName": "dd8b99a7-77c6-4238-a609-396d27844921",
    "connectedAs": "john.doe@contoso.onmicrosoft.com",
    "authType": "DeviceCode",
    "appId": "31359c7f-bd7e-475c-86db-fdb8c937548e",
    "appTenant": "common",
    "cloudType": "Public"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  To sign in, use a web browser to open the page https://microsoft.com/devicelogin and enter the code CQBMTLEFC to authenticate.
  ```
  Upon successful login:
  ```text
  appId         : 31359c7f-bd7e-475c-86db-fdb8c937548e
  appTenant     : common
  authType      : DeviceCode
  cloudType     : Public
  connectedAs   : john.doe@contoso.onmicrosoft.com
  connectionName: dd8b99a7-77c6-4238-a609-396d27844921
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  To sign in, use a web browser to open the page https://microsoft.com/devicelogin and enter the code CQBMTLEFC to authenticate.
  ```
  Upon successful login:
  ```csv
  connectionName,connectedAs,authType,appId,appTenant,cloudType
  dd8b99a7-77c6-4238-a609-396d27844921,john.doe@contoso.onmicrosoft.com,DeviceCode,31359c7f-bd7e-475c-86db-fdb8c937548e,common,Public
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  To sign in, use a web browser to open the page https://microsoft.com/devicelogin and enter the code CQBMTLEFC to authenticate.
  ```
  Upon successful login:
  ```md
  # login

  Date: 7/2/2023

  Property | Value
  ---------|-------
  connectionName | dd8b99a7-77c6-4238-a609-396d27844921
  connectedAs | john.doe@contoso.onmicrosoft.com
  authType | DeviceCode
  appId | 31359c7f-bd7e-475c-86db-fdb8c937548e
  appTenant | common
  cloudType | Public
  ```

  </TabItem>
</Tabs>
