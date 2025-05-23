-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra enterpriseapp add

Creates an enterprise application (or service principal) for a registered Entra app

## Usage

```sh
m365 entra enterpriseapp add [options]
```

## Alias

```sh
m365 entra sp add [options]
```

## Options

```md definition-list
`-i, --id [id]`
: ID of the app for which the enterprise application should be created.

`-n, --displayName [displayName]`
: Display name of the app for which the enterprise application should be created.

`--objectId [objectId]`
: ObjectId of the app for which the enterprise application should be created.
```

<Global />

## Remarks

Specify either the `id`, `displayName` or `objectId`. If you specify more than one option value, the command will fail with an error.

If you register an application in the portal, an application object as well as an enterprise application object are automatically created in your home tenant. If you register an application using CLI for Microsoft 365 or the Microsoft Graph, you'll need to create the enterprise application separately. To register/create an application using the CLI for Microsoft 365, use the [m365 entra app add](../app/app-add.mdx) command.

## Examples

Creates an enterprise application for a registered Entra app with the specified id.

```sh
m365 entra enterpriseapp add --id b2307a39-e878-458b-bc90-03bc578531d6
```

Creates an enterprise application for a registered Entra app with the specified displayName.

```sh
m365 entra enterpriseapp add --displayName "Microsoft Graph"
```

Creates an enterprise application for a registered Entra app with the specified objectId.

```sh
m365 entra enterpriseapp add --objectId b2307a39-e878-458b-bc90-03bc578531d6
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "caeefa7c-1b4e-4257-8f1e-5dffd4e409e4",
    "deletedDateTime": null,
    "accountEnabled": true,
    "alternativeNames": [],
    "appDisplayName": "My Entra app",
    "appDescription": null,
    "appId": "a1023942-9f35-42a6-baf6-390f3a5f89c4",
    "applicationTemplateId": null,
    "appOwnerOrganizationId": "c2b2a0f7-fa44-4929-a994-757b7b998f01",
    "appRoleAssignmentRequired": false,
    "createdDateTime": null,
    "description": null,
    "disabledByMicrosoftStatus": null,
    "displayName": "My Entra app",
    "homepage": null,
    "loginUrl": null,
    "logoutUrl": null,
    "notes": null,
    "notificationEmailAddresses": [],
    "preferredSingleSignOnMode": null,
    "preferredTokenSigningKeyThumbprint": null,
    "replyUrls": [],
    "servicePrincipalNames": [
      "a1023942-9f35-42a6-baf6-390f3a5f89c4"
    ],
    "servicePrincipalType": "Application",
    "signInAudience": "AzureADMyOrg",
    "tags": [],
    "tokenEncryptionKeyId": null,
    "samlSingleSignOnSettings": null,
    "addIns": [],
    "appRoles": [],
    "info": {
      "logoUrl": null,
      "marketingUrl": null,
      "privacyStatementUrl": null,
      "supportUrl": null,
      "termsOfServiceUrl": null
    },
    "keyCredentials": [],
    "oauth2PermissionScopes": [],
    "passwordCredentials": [],
    "resourceSpecificApplicationPermissions": [],
    "verifiedPublisher": {
      "displayName": null,
      "verifiedPublisherId": null,
      "addedDateTime": null
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  accountEnabled                        : true
  addIns                                : []
  alternativeNames                      : []
  appDescription                        : null
  appDisplayName                        : My Entra app
  appId                                 : f0790438-1fde-4340-8e64-3c770757dc4d
  appOwnerOrganizationId                : c2b2a0f7-fa44-4929-a994-757b7b998f01
  appRoleAssignmentRequired             : false
  appRoles                              : []
  applicationTemplateId                 : null
  createdDateTime                       : null
  deletedDateTime                       : null
  description                           : null
  disabledByMicrosoftStatus             : null
  displayName                           : My Entra app
  homepage                              : null
  id                                    : 6897ea56-b26f-4257-9101-2df7f1bcf2a2
  info                                  : {"logoUrl":null,"marketingUrl":null,"privacyStatementUrl":null,"supportUrl":null,"termsOfServiceUrl":null}
  keyCredentials                        : []
  loginUrl                              : null
  logoutUrl                             : null
  notes                                 : null
  notificationEmailAddresses            : []
  oauth2PermissionScopes                : []
  passwordCredentials                   : []
  preferredSingleSignOnMode             : null
  preferredTokenSigningKeyThumbprint    : null
  replyUrls                             : []
  resourceSpecificApplicationPermissions: []
  samlSingleSignOnSettings              : null
  servicePrincipalNames                 : ["f0790438-1fde-4340-8e64-3c770757dc4d"]
  servicePrincipalType                  : Application
  signInAudience                        : AzureADMyOrg
  tags                                  : []
  tokenEncryptionKeyId                  : null
  verifiedPublisher                     : {"displayName":null,"verifiedPublisherId":null,"addedDateTime":null}
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,accountEnabled,appDisplayName,appId,appOwnerOrganizationId,appRoleAssignmentRequired,displayName,servicePrincipalType,signInAudience
  29e00a15-cdb7-4d36-a745-30d920173dd8,1,My Entra app,ea8340e9-e464-4597-93f1-e115f9f8c7be,c2b2a0f7-fa44-4929-a994-757b7b998f01,,My Entra app,Application,AzureADMyOrg
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra enterpriseapp add --id "8da75b6a-4272-4b17-8ee1-20ba66e2b06f"

  Date: 2023-06-02

  ## My Entra app (28adf0e2-596c-4012-b24b-b0ec033a8f89)

  Property | Value
  ---------|-------
  id | 28adf0e2-596c-4012-b24b-b0ec033a8f89
  accountEnabled | true
  appDisplayName | My Entra app
  appId | 8da75b6a-4272-4b17-8ee1-20ba66e2b06f
  appOwnerOrganizationId | c2b2a0f7-fa44-4929-a994-757b7b998f01
  appRoleAssignmentRequired | false
  displayName | My Entra app
  servicePrincipalType | Application
  signInAudience | AzureADMyOrg
  ```

  </TabItem>
</Tabs>

## More information

- Application and service principal objects in Microsoft Entra ID: [https://learn.microsoft.com/azure/active-directory/develop/active-directory-application-objects](https://learn.microsoft.com/azure/active-directory/develop/active-directory-application-objects)
- Create servicePrincipal: [https://learn.microsoft.com/graph/api/serviceprincipal-post-serviceprincipals?view=graph-rest-1.0](https://learn.microsoft.com/graph/api/serviceprincipal-post-serviceprincipals?view=graph-rest-1.0)
