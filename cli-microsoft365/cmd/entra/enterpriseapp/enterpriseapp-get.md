-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra enterpriseapp get

Gets information about an enterprise application (or service principal)

## Usage

```sh
m365 entra enterpriseapp get [options]
```

## Alias

```sh
m365 entra sp get [options]
```

## Options

```md definition-list
`-i, --id [id]`
: ID of the application for which the enterprise application should be retrieved.

`-n, --displayName [displayName]`
: Display name of the application for which the enterprise application should be retrieved.

`--objectId [objectId]`
: ObjectId of the application for which the enterprise application should be retrieved.
```

<Global />

## Remarks

Specify either the `id`, `objectId` or `displayName`. If you specify more than one option value, the command will fail with an error.

## Examples

Return details about the enterprise application with the specified id.

```sh
m365 entra enterpriseapp get --id b2307a39-e878-458b-bc90-03bc578531d6
```

Return details about the enterprise application with the specified displayName.

```sh
m365 entra enterpriseapp get --displayName "Microsoft Graph"
```

Return details about the enterprise application with the specified ObjectId.

```sh
m365 entra enterpriseapp get --objectId b2307a39-e878-458b-bc90-03bc578531dd
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "b62fe6f3-5746-49be-af60-eaa24d66754a",
    "deletedDateTime": null,
    "accountEnabled": true,
    "alternativeNames": [],
    "appDisplayName": "LinkedIn",
    "appDescription": null,
    "appId": "ac7c9b4b-83b0-4a5e-ace2-a3530162c8f8",
    "applicationTemplateId": null,
    "appOwnerOrganizationId": "c2b2a0f7-fa44-4929-a994-757b7b998f01",
    "appRoleAssignmentRequired": true,
    "createdDateTime": "2022-12-12T15:41:42Z",
    "description": null,
    "disabledByMicrosoftStatus": null,
    "displayName": "LinkedIn",
    "homepage": "https://EXAMPLE_SECRET_VALUE_PLACEHOLDER:444/applications/default.aspx?metadata=linkedin|ISV9.3|primary|z",
    "loginUrl": null,
    "logoutUrl": null,
    "notes": null,
    "notificationEmailAddresses": [],
    "preferredSingleSignOnMode": null,
    "preferredTokenSigningKeyThumbprint": null,
    "replyUrls": [],
    "servicePrincipalNames": [
      "ac7c9b4b-83b0-4a5e-ace2-a3530162c8f8",
      "http://LinkedIn/41859ae8-d0c4-45ac-9394-00000464c196"
    ],
    "servicePrincipalType": "Application",
    "signInAudience": "AzureADMyOrg",
    "tags": [
      "4d57f64e-9941-4df2-bb70-8d9a2a38ab91",
      "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "EXAMPLE_SECRET_VALUE_PLACEHOLDER"
    ],
    "tokenEncryptionKeyId": null,
    "samlSingleSignOnSettings": null,
    "addIns": [],
    "appRoles": [
      {
        "allowedMemberTypes": [
          "User"
        ],
        "description": "msiam_access",
        "displayName": "msiam_access",
        "id": "01c2bb8e-0895-42c8-b950-3ec8abc7a012",
        "isEnabled": true,
        "origin": "Application",
        "value": null
      }
    ],
    "info": {
      "logoUrl": null,
      "marketingUrl": null,
      "privacyStatementUrl": null,
      "supportUrl": null,
      "termsOfServiceUrl": null
    },
    "keyCredentials": [],
    "oauth2PermissionScopes": [
      {
        "adminConsentDescription": "Allow the application to access LinkedIn on behalf of the signed-in user.",
        "adminConsentDisplayName": "Access LinkedIn",
        "id": "823b3b27-be2a-4699-a0ae-da054e6465cf",
        "isEnabled": true,
        "type": "User",
        "userConsentDescription": "Allow the application to access LinkedIn on your behalf.",
        "userConsentDisplayName": "Access LinkedIn",
        "value": "user_impersonation"
      }
    ],
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
  appDisplayName                        : LinkedIn
  appId                                 : ac7c9b4b-83b0-4a5e-ace2-a3530162c8f8
  appOwnerOrganizationId                : c2b2a0f7-fa44-4929-a994-757b7b998f01
  appRoleAssignmentRequired             : true
  appRoles                              : [{"allowedMemberTypes":["User"],"description":"msiam_access","displayName":"msiam_access","id":"01c2bb8e-0895-42c8-b950-3ec8abc7a012","isEnabled":true,"origin":"Application","value":null}]
  applicationTemplateId                 : null
  createdDateTime                       : 2022-12-12T15:41:42Z
  deletedDateTime                       : null
  description                           : null
  disabledByMicrosoftStatus             : null
  displayName                           : LinkedIn
  homepage                              : https://EXAMPLE_SECRET_VALUE_PLACEHOLDER:444/applications/default.aspx?metadata=linkedin|ISV9.3|primary|z
  id                                    : b62fe6f3-5746-49be-af60-eaa24d66754a
  info                                  : {"logoUrl":null,"marketingUrl":null,"privacyStatementUrl":null,"supportUrl":null,"termsOfServiceUrl":null}
  keyCredentials                        : []
  loginUrl                              : null
  logoutUrl                             : null
  notes                                 : null
  notificationEmailAddresses            : []
  oauth2PermissionScopes                : [{"adminConsentDescription":"Allow the application to access LinkedIn on behalf of the signed-in user.","adminConsentDisplayName":"Access LinkedIn","id":"823b3b27-be2a-4699-a0ae-da054e6465cf","isEnabled":true,"type":"User","userConsentDescription":"Allow the application to access LinkedIn on your behalf.","userConsentDisplayName":"Access LinkedIn","value":"user_impersonation"}]
  passwordCredentials                   : []
  preferredSingleSignOnMode             : null
  preferredTokenSigningKeyThumbprint    : null
  replyUrls                             : []
  resourceSpecificApplicationPermissions: []
  samlSingleSignOnSettings              : null
  servicePrincipalNames                 : ["ac7c9b4b-83b0-4a5e-ace2-a3530162c8f8","http://LinkedIn/41859ae8-d0c4-45ac-9394-00000464c196"]
  servicePrincipalType                  : Application
  signInAudience                        : AzureADMyOrg
  tags                                  : ["4d57f64e-9941-4df2-bb70-8d9a2a38ab91","EXAMPLE_SECRET_VALUE_PLACEHOLDER","EXAMPLE_SECRET_VALUE_PLACEHOLDER"]
  tokenEncryptionKeyId                  : null
  verifiedPublisher                     : {"displayName":null,"verifiedPublisherId":null,"addedDateTime":null}
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,accountEnabled,appDisplayName,appId,appOwnerOrganizationId,appRoleAssignmentRequired,createdDateTime,displayName,homepage,servicePrincipalType,signInAudience
  b62fe6f3-5746-49be-af60-eaa24d66754a,1,LinkedIn,ac7c9b4b-83b0-4a5e-ace2-a3530162c8f8,c2b2a0f7-fa44-4929-a994-757b7b998f01,1,2022-12-12T15:41:42Z,LinkedIn,https://EXAMPLE_SECRET_VALUE_PLACEHOLDER:444/applications/default.aspx?metadata=linkedin|ISV9.3|primary|z,Application,AzureADMyOrg
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra enterpriseapp get --id "ac7c9b4b-83b0-4a5e-ace2-a3530162c8f8"

  Date: 2023-06-02

  ## LinkedIn (b62fe6f3-5746-49be-af60-eaa24d66754a)

  Property | Value
  ---------|-------
  id | b62fe6f3-5746-49be-af60-eaa24d66754a
  accountEnabled | true
  appDisplayName | LinkedIn
  appId | ac7c9b4b-83b0-4a5e-ace2-a3530162c8f8
  appOwnerOrganizationId | c2b2a0f7-fa44-4929-a994-757b7b998f01
  appRoleAssignmentRequired | true
  createdDateTime | 2022-12-12T15:41:42Z
  displayName | LinkedIn
  homepage | https://EXAMPLE_SECRET_VALUE_PLACEHOLDER:444/applications/default.aspx?metadata=linkedin\|ISV9.3\|primary\|z
  servicePrincipalType | Application
  signInAudience | AzureADMyOrg
  ```

  </TabItem>
</Tabs>

## More information

- Application and service principal objects in Microsoft Entra ID: [https://learn.microsoft.com/azure/active-directory/develop/active-directory-application-objects](https://learn.microsoft.com/azure/active-directory/develop/active-directory-application-objects)
- Get servicePrincipal: [https://learn.microsoft.com/graph/api/serviceprincipal-get?view=graph-rest-1.0](https://learn.microsoft.com/graph/api/serviceprincipal-get?view=graph-rest-1.0)
