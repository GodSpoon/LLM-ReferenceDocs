-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra app list

Retrieves a list of Entra app registrations

## Usage

```sh
m365 entra app list [options]
```

## Alias

```sh
m365 entra appregistration list [options]
```

## Options

```md definition-list
`-p, --properties [properties]`
: Comma-separated list of properties to retrieve.
```

<Global />

## Remarks

Using the `--properties` option, you can specify a comma-separated list of app properties to retrieve from the Microsoft Graph. If you don't specify any properties, the command will output the default properties returned by Graph.

## Examples

Retrieve a list of Entra app registrations.

```sh
m365 entra app list
```

Retrieve a list of Entra app registrations with specified properties.

```sh
m365 entra app list --properties "appId,displayName"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "ff2798f7-1c7a-4607-8a7b-3d5e0c18c756",
      "deletedDateTime": null,
      "appId": "61ed4fab-a861-4307-bb87-a6a53dbe39f5",
      "applicationTemplateId": null,
      "disabledByMicrosoftStatus": null,
      "createdDateTime": "2021-03-16T14:51:28Z",
      "displayName": "TestAppPermissions",
      "description": null,
      "groupMembershipClaims": null,
      "identifierUris": [],
      "isDeviceOnlyAuthSupported": null,
      "isFallbackPublicClient": null,
      "notes": null,
      "publisherDomain": "Contoso.onmicrosoft.com",
      "serviceManagementReference": null,
      "signInAudience": "AzureADMyOrg",
      "tags": [],
      "tokenEncryptionKeyId": null,
      "samlMetadataUrl": null,
      "defaultRedirectUri": null,
      "certification": null,
      "optionalClaims": null,
      "addIns": [],
      "api": {
        "acceptMappedClaims": null,
        "knownClientApplications": [],
        "requestedAccessTokenVersion": null,
        "oauth2PermissionScopes": [],
        "preAuthorizedApplications": []
      },
      "appRoles": [],
      "info": {
        "logoUrl": null,
        "marketingUrl": null,
        "privacyStatementUrl": null,
        "supportUrl": null,
        "termsOfServiceUrl": null
      },
      "keyCredentials": [
        {
          "customKeyIdentifier": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
          "displayName": "CN=TestCertificate",
          "endDateTime": "2022-01-01T00:00:00Z",
          "key": null,
          "keyId": "8928a06f-fa2d-4d92-98c3-b0f544804f64",
          "startDateTime": "2020-01-01T00:00:00Z",
          "type": "AsymmetricX509Cert",
          "usage": "Verify"
        }
      ],
      "parentalControlSettings": {
        "countriesBlockedForMinors": [],
        "legalAgeGroupRule": "Allow"
      },
      "passwordCredentials": [
        {
          "customKeyIdentifier": null,
          "displayName": "TestSecret",
          "endDateTime": "2022-03-16T14:58:45.602Z",
          "hint": "~03",
          "keyId": "714c9628-4bb8-4f08-84b4-7fd8d7a7b8c5",
          "secretText": null,
          "startDateTime": "2021-03-16T14:59:07.642Z"
        }
      ],
      "publicClient": {
        "redirectUris": []
      },
      "requiredResourceAccess": [
        {
          "resourceAppId": "00000003-0000-0000-c000-000000000000",
          "resourceAccess": [
            {
              "id": "e1fe6dd8-ba31-4d61-89e7-88639da4683d",
              "type": "Scope"
            },
            {
              "id": "18228521-a591-40f1-b215-5fad4488c117",
              "type": "Role"
            },
            {
              "id": "09850681-111b-4a89-9bed-3f2cae46d706",
              "type": "Role"
            }
          ]
        }
      ],
      "verifiedPublisher": {
        "displayName": null,
        "verifiedPublisherId": null,
        "addedDateTime": null
      },
      "web": {
        "homePageUrl": null,
        "logoutUrl": null,
        "redirectUris": [],
        "implicitGrantSettings": {
          "enableAccessTokenIssuance": false,
          "enableIdTokenIssuance": false
        },
        "redirectUriSettings": []
      },
      "spa": {
        "redirectUris": []
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  appId                                 id                                    displayName                                                              signInAudience
  ------------------------------------  ------------------------------------  -----------------------------------------------------------------------  ----------------------------------
  61ed4fab-a861-4307-bb87-a6a53dbe39f5  ff2798f7-1c7a-4607-8a7b-3d5e0c18c756  TestAppPermissions                                                       AzureADMyOrg
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  appId,id,displayName,signInAudience
  61ed4fab-a861-4307-bb87-a6a53dbe39f5,ff2798f7-1c7a-4607-8a7b-3d5e0c18c756,TestAppPermissions,AzureADMyOrg
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra app list

  Date: 2023-06-01

  ## TestAppPermissions (ff2798f7-1c7a-4607-8a7b-3d5e0c18c756)

  Property | Value
  ---------|-------
  id | ff2798f7-1c7a-4607-8a7b-3d5e0c18c756
  appId | 61ed4fab-a861-4307-bb87-a6a53dbe39f5
  createdDateTime | 2021-03-16T14:51:28Z
  displayName | TestAppPermissions
  isFallbackPublicClient | true
  publisherDomain | contoso.onmicrosoft.com
  signInAudience | AzureADMyOrg
  ```

  </TabItem>
</Tabs>
