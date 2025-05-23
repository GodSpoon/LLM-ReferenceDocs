-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra enterpriseapp list

Lists the enterprise applications (or service principals) in Entra ID

## Usage

```sh
m365 entra enterpriseapp list [options]
```

## Alias

```sh
m365 entra sp list [options]
```

## Options

```md definition-list
`-n, --displayName [displayName]`
: Returns only enterprise applications with the specified name.

`--tag [tag]`
: Returns only enterprise applications with the specified tag.
```

<Global />

## Examples

Returns a list of all enterprise applications.

```sh
m365 entra enterpriseapp list
```

Returns a list of all enterprise applications that comply with the specified display name and the tag parameters.

```sh
m365 entra enterpriseapp list --displayName "My custom enterprise application" --tag "EXAMPLE_SECRET_VALUE_PLACEHOLDER"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "226859cc-86f0-40d3-b308-f43b3a729b6e",
      "deletedDateTime": null,
      "accountEnabled": true,
      "alternativeNames": [],
      "appDisplayName": "My custom enterprise application",
      "appDescription": null,
      "appId": "a62ef842-f9ef-49cf-9119-31b85ea58445",
      "applicationTemplateId": null,
      "appOwnerOrganizationId": "fd71909b-55e5-44d2-9f78-dc432421d527",
      "appRoleAssignmentRequired": false,
      "createdDateTime": "2022-11-28T20:32:11Z",
      "description": null,
      "disabledByMicrosoftStatus": null,
      "displayName": "My custom enterprise application",
      "homepage": null,
      "loginUrl": null,
      "logoutUrl": null,
      "notes": null,
      "notificationEmailAddresses": [],
      "preferredSingleSignOnMode": null,
      "preferredTokenSigningKeyThumbprint": null,
      "replyUrls": [
        "urn:ietf:wg:oauth:2.0:oob",
        "https://localhost",
        "http://localhost",
        "http://localhost:8400"
      ],
      "servicePrincipalNames": [
        "https://contoso.onmicrosoft.com/907a8cea-411a-461a-bb30-261e52febcca",
        "907a8cea-411a-461a-bb30-261e52febcca"
      ],
      "servicePrincipalType": "Application",
      "signInAudience": "AzureADMultipleOrgs",
      "tags": [
        "EXAMPLE_SECRET_VALUE_PLACEHOLDER"
      ],
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
      "oauth2PermissionScopes": [
        {
          "adminConsentDescription": "Allow the application to access My custom enterprise application on behalf of the signed-in user.",
          "adminConsentDisplayName": "Access My custom enterprise application",
          "id": "907a8cea-411a-461a-bb30-261e52febcca",
          "isEnabled": true,
          "type": "User",
          "userConsentDescription": "Allow the application to access My custom enterprise application on your behalf.",
          "userConsentDisplayName": "Access My custom enterprise application",
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
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                      displayName                   tag
  --------------------------------------  ----------------------------  ---------------------------------------
  a62ef842-f9ef-49cf-9119-31b85ea58445    My custom enterprise application   EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,accountEnabled,appDisplayName,appId,appOwnerOrganizationId,appRoleAssignmentRequired,createdDateTime,displayName,servicePrincipalType,signInAudience
  226859cc-86f0-40d3-b308-f43b3a729b6e,1,My custom enterprise application,a62ef842-f9ef-49cf-9119-31b85ea58445,fd71909b-55e5-44d2-9f78-dc432421d527,,2022-11-28T20:32:11Z,My custom enterprise application,AzureADMultipleOrgs
  ```
    
  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra enterpriseapp list

  Date: 27/4/2023

  ## My custom enterprise application (226859cc-86f0-40d3-b308-f43b3a729b6e)

  Property | Value
  ---------|-------
  id | 226859cc-86f0-40d3-b308-f43b3a729b6e
  accountEnabled | true
  appDisplayName | My custom enterprise application
  appId | a62ef842-f9ef-49cf-9119-31b85ea58445
  appOwnerOrganizationId | fd71909b-55e5-44d2-9f78-dc432421d527
  appRoleAssignmentRequired | false
  createdDateTime | 2022-11-28T20:32:11Z
  displayName | My custom enterprise application
  servicePrincipalType | Application
  signInAudience | AzureADMultipleOrg
  ```

  </TabItem>
</Tabs>
