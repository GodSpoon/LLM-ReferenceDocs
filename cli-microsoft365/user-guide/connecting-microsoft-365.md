-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
title: Log in to Microsoft 365 
sidebar_position: 3
---

import AsciinemaPlayer from '../../src/components/AsciinemaPlayer';
import 'asciinema-player/dist/bundle/asciinema-player.css';

# Log in to Microsoft 365

Before you can use CLI for Microsoft 365 commands to manage your tenant, you have to log in to Microsoft 365. Following section explains how you can log in and check the Microsoft 365 login status.

## Microsoft 365 services

Using the CLI for Microsoft 365 you can manage different areas of an Microsoft 365 tenant. Currently, commands for working with SharePoint Online, Microsoft Entra ID, Microsoft Graph and the Azure Management Service are available, but more commands for other services will be added in the future.

Commands in the CLI for Microsoft 365 are organized into services. For example, all commands that manage SharePoint Online begin with `spo` (`spo app list`, `spo cdn get`, etc.) and commands for working with the Microsoft Entra ID begin with `entra`. After logging in to Microsoft 365, you can communicate with any Microsoft 365 service supported by the CLI for Microsoft 365 and it will automatically retrieve the necessary access token.

### Log in to Microsoft 365

CLI for Microsoft 365 offers you a number of ways to log in to Microsoft 365.

#### Log in using the default device code flow

The default way to log in to Microsoft 365 using the CLI for Microsoft 365 is through the device code flow. To log in to Microsoft 365, use the `login` command.

When logging in, you need to specify the `appId` and `tenant` of your Microsoft Entra application registration. This is required to authenticate your own application registration to access your tenant on your behalf.

:::info

If you don't have an application registration yet, you can create one using the [m365 setup](../cmd/setup.mdx) command. This command will guide you through the process of creating a new application registration and granting it the necessary permissions in your tenant. It will also set the `appId` and `tenant` environment variables for you, allowing you to log in to Microsoft 365 without specifying these values when using the `login` command.

Alternatively, you can manually set the `CLIMICROSOFT365_ENTRAAPPID` and `CLIMICROSOFT365_TENANT` environment variables to avoid specifying the `appId` and `tenant` values during login.

For more details on creating an application registration or setting the environment variables, refer to the article: [Use your own Microsoft Entra identity](./using-own-identity.mdx).

:::

After executing the `login` command, you will be prompted to navigate to _https://aka.ms/devicelogin_ in your web browser and enter the login code presented to you by the CLI for Microsoft 365 in the command line. After entering the code, you will see the prompt that you are about to authenticate your own application registration to access your tenant on your behalf. After accepting the prompt, you can go back to the CLI for Microsoft 365 and you will be logged.

The default method to log in to Microsoft 365 using the CLI for Microsoft 365 is through the device code flow, which you can initiate by executing the `login` command. However, if possible, opt for browser authentication as it is more convenient and provides the same security benefits. If you are logging in from a different system (e.g., inside a Docker container, Azure Cloud Shell, etc.) where the CLI cannot open a browser, use the device code flow instead. The device code flow is interactive and requires user interaction, which might be limiting if you want to use the CLI for Microsoft 365 in a fully automated continuous deployment setup that doesn't involve user interaction.

#### Log in using user name and password

An alternative way to log in to Microsoft 365 in the CLI for Microsoft 365 is by using a user name and password. To use this way of authenticating, set the `authType` option to `password` and specify your credentials using the `userName` and `password` options.

To log in to Microsoft 365 using your user name and password, execute:

```sh
m365 login --authType password --userName user@contoso.com --password pass@word1
```

Using credentials to log in to Microsoft 365 is convenient in automation scenarios where you cannot authenticate interactively. The downside of this way of authenticating is, that it doesn't allow you to use any of the advanced security features that Microsoft Entra ID offers. If your account for example uses multi-factor authentication, logging in to Microsoft 365 using credentials will fail.

:::warning

When logging in to Microsoft 365 using credentials, CLI for Microsoft 365 will persist not only the retrieved access and refresh token, but also the credentials you specified when logging in. This is necessary for the CLI to be able to retrieve a new refresh token, in case the previously retrieved refresh token expired or has been invalidated.

:::

Generally, you should use the default device code flow. If you need to use a non-interactive authentication flow, you can authenticate using a certificate or credentials of an account that has sufficient privileges in your tenant and doesn't have multi-factor authentication or other advanced security features enabled.

#### Log in using a certificate

Another way to log in to Microsoft 365 in the CLI for Microsoft 365 is by using a certificate. To use this authentication method, set the `CLIMICROSOFT365_ENTRAAPPID` environment variable to the ID of the Microsoft Entra application that you want to use to authenticate the CLI for Microsoft 365 and the `CLIMICROSOFT365_TENANT` environment variable to the ID of your Microsoft Entra ID directory. When calling the login command, set the `authType` option to `certificate` and specify the path to the certificate private key using the `certificateFile` option. Optionally, you can specify the certificate's thumbprint using the `thumbprint` option. If not specified, CLI will automatically calculate it from the specified certificate.

To log in to Microsoft 365 using a Personal Information Exchange (.pfx) file, execute:

```sh
m365 login --authType certificate --certificateFile /Users/user/dev/localhost.pfx --password 'pass@word1'
```

To log in to Microsoft 365 using a Privacy Enhanced Mail (PEM) certificate, execute:

```sh
m365 login --authType certificate --certificateFile /Users/user/dev/localhost.pem
```

Logging in to Microsoft 365 using a certificate is convenient for automation scenarios where you cannot authenticate interactively but also don't want to use credentials.

Because there is no user context when logging in using a certificate, you will typically create a new Microsoft Entra application, specific to your organization and grant it the required permissions.

:::warning

You should keep in mind, that because the CLI for Microsoft 365 will be accessing these APIs with app-only context, you need to grant the correct application permissions rather than delegated permissions that would be used in other authentication methods.

:::

Logging in using a certificate gives the CLI for Microsoft 365 app-only access to Microsoft 365 services. Not all operations support app-only access so it is possible, that some CLI commands will fail when executed while logged in to Microsoft 365 using a certificate.

:::warning

When logging in to Microsoft 365 using a certificate, CLI for Microsoft 365 will persist not only the retrieved access token but also the contents of the certificate's private key and its thumbprint. This is necessary for the CLI to be able to retrieve a new access token in case of the previously retrieved access token expired or has been invalidated.

:::

Generally, you should use the default device code flow. If you need to use a non-interactive authentication flow, to for example integrate the CLI for Microsoft 365 in your build pipeline, you can login using a certificate or user credentials.

:::warning

PFX files exported from a Windows key store will not work as they are protected with either a password or Active Directory account. The private key must either be exported from the protected .pfx or newly created using 3rd party tools like OpenSSL (https://www.openssl.org/).

:::

Create a new self signed certificate:

```sh
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout privateKey.key -out certificate.cer
```

Create a new Personal Information Exchange (.pfx) file

```sh
openssl pkcs12 -export -out protected.pfx -inkey privateKey.key -in certificate.cer -password pass:"pass@word1"
```

At this point the `protected.pfx` file can be used to log in the CLI for Microsoft 365 following the instructions above for logging in using a .pfx file.

If login with the .pfx file does not work then extract the private key from a protected .pfx and unprotect it:

```sh
openssl pkcs12 -in protected.pfx -out privateKeyWithPassphrase.pem -nodes
```

At this point the `privateKeyWithPassphrase.pem` file can be used to log in the CLI for Microsoft 365 following the instructions above for logging in using a PEM certificate.

#### Log in using a secret

CLI for Microsoft 365 also supports login using a secret. To use this authentication method, set the `CLIMICROSOFT365_ENTRAAPPID` environment variable to the ID of the Microsoft Entra application that you want to use to authenticate the CLI for Microsoft 365 and the `CLIMICROSOFT365_TENANT` environment variable to the ID of your Microsoft Entra ID directory. When calling the login command, set the `authType` option to `secret` and specify the client secret value. 

To log in to Microsoft 365 using a secret, execute:

```sh
m365 login --authType secret --secret topSeCr3t@007
```

Logging in to Microsoft 365 using a secret is convenient for automation scenarios where you cannot authenticate interactively but also don't want to use credentials.

Because there is no user context when logging in using a secret, you will typically create a new Microsoft Entra application, specific to your organization and grant it the required permissions.

:::warning

You should keep in mind, that because the CLI for Microsoft 365 will be accessing these APIs with app-only context, you need to grant the correct application permissions rather than delegated permissions that would be used in other authentication methods.

:::

Logging in using a secret gives the CLI for Microsoft 365 app-only access to Microsoft 365 services. Not all operations support app-only access so it is possible, that some CLI commands will fail when executed while logged in to Microsoft 365 using a secret.

:::warning

Currently, SharePoint does not support authentication using Microsoft Entra app ID and Secret. CLI for Microsoft 365 commands that call the SharePoint APIs will fail while logged in to Microsoft 365 using a Secret.

:::

:::warning

When logging in to Microsoft 365 using a secret, CLI for Microsoft 365 will persist not only the retrieved access token but also the secret. This is necessary for the CLI to be able to retrieve a new access token in case of the previously retrieved access token expired or has been invalidated.

:::

#### Login without setting the environment variables

In all the examples above, we make use of the `CLIMICROSOFT365_ENTRAAPPID` and `CLIMICROSOFT365_TENANT` environment variables. If you don't want to set these environment variables, you can specify the options `appId` and `tenant` when logging in to Microsoft 365.

Below would be the command to log in to Microsoft 365 using a Personal Information Exchange (.pfx) file, execute:

```sh
m365 login --appId 31359c7f-bd7e-475c-86db-fdb8c937548c --tenant 31359c7f-bd7e-475c-86db-fdb8c937548a -authType certificate --certificateFile /Users/user/dev/localhost.pfx --password 'pass@word1'
```

#### Log in using a browser authentication

Yet another way to log in to Microsoft 365 in the CLI for Microsoft 365 is by using a an interactive browser authentication. To use this authentication method, call the login command with the `authType` option set to `browser`:

```sh
m365 login --authType browser
```

This option is especially useful if you have conditional access policies configured in your tenant but you can also use it instead of the default device code flow.

### Check login status

To see if you're logged in to Microsoft 365 and if so, with which account, use the `status` command.

If you're logged in to Microsoft 365 using a certificate, the `status` command will show the name of the Microsoft Entra application used to log in.

### Log out from Microsoft 365

To log out from Microsoft 365, use the `logout` command. Executing the `logout` command removes all connection information such as user name, refresh or access tokens stored on your computer.

<AsciinemaPlayer src="https://asciinema.org/a/445658.cast" rows={15} idleTimeLimit={3} preload={true} loop autoplay/>

### Working with SharePoint Online

CLI for Microsoft 365 automatically detects the URL of your SharePoint Online tenant when executing SharePoint commands. All you need to do is to log in to Microsoft 365 with your account. Commands, that operate on specific site collections or sites, allow you to specify the URL of the site on which you want to perform the operation and you can execute them without having to specifically connect or login to the given site. CLI for Microsoft 365 will automatically retrieve the necessary access token to execute the given command.

:::info

Some SharePoint commands in the CLI for Microsoft 365 require access to tenant-level resources. To execute these commands, you have to have permissions to access the tenant admin site.

:::

## Authorize with Microsoft 365

To authorize for communicating with Microsoft 365 API, the CLI for Microsoft 365 uses the OAuth 2.0 protocol. When using the default device code flow, you authenticate with Microsoft Entra ID in the web browser. After authenticating, CLI for Microsoft 365 will attempt to retrieve a valid access token for the specified Microsoft 365 service. If you have insufficient permissions to access the particular service, authorization will fail with an adequate error.

If you authenticate using credentials, the authentication and authorization are a part of the same request that CLI for Microsoft 365 issues towards Microsoft Entra ID. If either authentication or authorization fails, you will see a corresponding error message explaining what went wrong.

## Logging in to Microsoft 365 via a proxy

All communication between the CLI for Microsoft 365 and Microsoft 365 APIs happens via web requests. If you're behind a proxy, you should set up an environment variable to allow CLI for Microsoft 365 to log in to Microsoft 365. More information about the necessary configuration steps is available at [https://github.com/request/request#EXAMPLE_SECRET_VALUE_PLACEHOLDER](https://github.com/request/request#EXAMPLE_SECRET_VALUE_PLACEHOLDER).

## Persisted connections

After logging in to Microsoft 365, the CLI for Microsoft 365 will persist that connection information until you explicitly log out from Microsoft 365. This is necessary to support building scripts using the CLI for Microsoft 365, where each command is executed independently of other commands. Persisted connection contains information about the user name used to establish the connection as well as the retrieved refresh- and access tokens. To secure this information from unprivileged access, it's stored securely in the password store specific to the platform on which you're using the CLI. For more information, see the separate article dedicated to [persisting connection information](../concepts/persisting-connection.mdx) in the CLI for Microsoft 365.
