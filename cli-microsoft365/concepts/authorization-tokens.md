-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
sidebar_position: 2
---

# Authorization and access tokens

Commands provided with the CLI for Microsoft 365 manipulate different settings of Microsoft 365. Before you can execute any of the commands in the CLI, you have to log in to Microsoft 365. CLI for Microsoft 365 will then automatically retrieve the access token necessary to execute the particular command.

## Authorization in the CLI for Microsoft 365

There are a number of ways in which you can authenticate and authorize with Microsoft 365. The CLI for Microsoft 365 uses the OAuth protocol to authorize with Microsoft 365 and its services. OAuth flows in Microsoft 365 are facilitated by Microsoft Entra ID.

### Microsoft Entra application used by the CLI for Microsoft 365

CLI for Microsoft 365 gets access to Microsoft 365 through your own Microsoft Entra application registration. 

:::info

When you create your own Microsoft Entra application, you need to choose the application to be a **public client**. Despite the setting's description, the application will not be publicly accessible. This setting enables the use of the device flow for your own application and is only required for interactive use of the CLI. If you use the CLI with non-interactive scripts and log in using client credentials or Managed Service Identity, you don't need to activate this setting. The option is currently only available in the preview blade for managing Microsoft Entra applications.

<br/>

[![The 'public client' enabled for a Microsoft Entra application](../images/activate-public-client-aad-app.png)](../images/activate-public-client-aad-app.png)

:::

When specifying a application registration to be used by the CLI for Microsoft 365, set the `CLIMICROSOFT365_ENTRAAPPID` environment variable to the ID of your application registration.

For a streamlined setup, you can use the [m365 setup](../cmd/setup.mdx) command to create a new application registration with all the necessary permissions to fully use the CLI for Microsoft 365.

:::warning

After changing the ID of the application registration used by the CLI for Microsoft 365 refresh the existing connection to Microsoft 365 using the `login` command. If you try to use the existing connection, CLI for Microsoft 365 will fail when trying to refresh the existing access token.

:::

For instructions on how to create your own Microsoft Entra application registration see [Using your own Microsoft Entra identity](../user-guide/using-own-identity.mdx).

### Access and refresh tokens in the CLI for Microsoft 365

After completing the OAuth flow, the CLI receives from Microsoft Entra ID a refresh- and an access token. Each web request to Microsoft 365 APIs contains the access token which authorizes the CLI for Microsoft 365 to execute the particular operation. When the access token expires, the CLI uses the refresh token to obtain a new access token. When the refresh token expires, the user has to reauthenticate to Microsoft 365 to obtain a new refresh token.

## Services and commands

Each command in the CLI for Microsoft 365 belongs to a service, for example the [spo site add](../cmd/spo/site/site-add.mdx) command, which creates a new modern site, belongs to the SharePoint Online service, while the [entra enterpriseapp get](../cmd/entra/enterpriseapp/enterpriseapp-get.mdx) command, which lists Microsoft Entra ID service principals, belongs to the Azure Active Directory Graph service. Each service in Microsoft 365 is a different Microsoft Entra ID authorization resource and requires a separate access token. When working with the CLI, you can be simultaneously connected to multiple services. Each command in the CLI knows which Microsoft 365 service it communicates with and for which resource it should have a valid access token.

## Communicating with Microsoft 365

Before a command can log in to Microsoft 365, it requires a valid access token. CLI for Microsoft 365 automatically obtains the access token for the particular web request without you having to worry about it.

## Viva Engage commands are executed in the context of the current logged in user

Viva Engage commands require the delegated 'user_impersonation' permission to be granted for the Microsoft Entra application. Viva Engage commands are executed in the context of the currently logged in user. Certificate-based authentication with app_only permissions is currently not supported by Microsoft Entra ID.
