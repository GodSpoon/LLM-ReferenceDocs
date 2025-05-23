-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra app get

Gets an Entra app registration

## Usage

```sh
m365 entra app get [options]
```

## Alias

```sh
m365 entra appregistration get [options]
```

## Options

```md definition-list
`--appId [appId]`
: Application (client) ID of the Entra application registration to get. Specify either `appId`, `objectId` or `name`.

`--objectId [objectId]`
: Object ID of the Entra application registration to get. Specify either `appId`, `objectId` or `name`.

`--name [name]`
: Name of the Entra application registration to get. Specify either `appId`, `objectId` or `name`.

`--save`
: Use to store the information about the created app in a local file.

`-p, --properties [properties]`
: Comma-separated list of properties to retrieve.
```

<Global />

## Remarks

For best performance use the `objectId` option to reference the Entra application registration to get. If you use `appId` or `name`, this command will first need to find the corresponding object ID for that application.

If the command finds multiple Entra application registrations with the specified app name, it will prompt you to disambiguate which app it should use, listing the discovered object IDs.

If you want to store the information about the Entra app registration, use the `--save` option. This is useful when you build solutions connected to Microsoft 365 and want to easily manage app registrations used with your solution. When you use the `--save` option, after you get the app registration, the command will write its ID and name to the `.m365rc.json` file in the current directory. If the file already exists, it will add the information about the App registration to it if it's not already present, allowing you to track multiple apps. If the file doesn't exist, the command will create it.

Using the `--properties` option, you can specify a comma-separated list of app properties to retrieve from the Microsoft Graph. If you don't specify any properties, the command will output the default properties returned by Graph.

## Examples

Get the Entra application registration by its app (client) ID.

```sh
m365 entra app get --appId d75be2e1-0204-4f95-857d-51a37cf40be8
```

Get the Entra application registration by its object ID.

```sh
m365 entra app get --objectId d75be2e1-0204-4f95-857d-51a37cf40be8
```

Get the Entra application registration by its name with specified properties.

```sh
m365 entra app get --name "My app" --properties "appId,displayName"
```

Get the Entra application registration by its name. Store information about the retrieved app registration in the _.m365rc.json_ file in the current directory.

```sh
m365 entra app get --name "My app" --save
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "0d2eb848-da5f-4131-b739-941150b3a43d",
    "deletedDateTime": null,
    "appId": "9eb465b4-eed9-4fb2-aa7a-4dfe18a52a4d",
    "applicationTemplateId": null,
    "disabledByMicrosoftStatus": null,
    "createdDateTime": "2021-07-22T09:19:45Z",
    "displayName": "helloworld",
    "description": null,
    "groupMembershipClaims": null,
    "identifierUris": [
      "api://EXAMPLE_SECRET_VALUE_PLACEHOLDER/9eb465b4-eed9-4fb2-aa7a-4dfe18a52a4d"
    ],
    "isDeviceOnlyAuthSupported": null,
    "isFallbackPublicClient": null,
    "notes": null,
    "publisherDomain": "contoso.onmicrosoft.com",
    "serviceManagementReference": null,
    "signInAudience": "AzureADMyOrg",
    "tags": [],
    "tokenEncryptionKeyId": null,
    "samlMetadataUrl": null,
    "defaultRedirectUri": null,
    "certification": null,
    "servicePrincipalLockConfiguration": null,
    "requestSignatureVerification": null,
    "addIns": [],
    "api": {
      "acceptMappedClaims": null,
      "knownClientApplications": [],
      "requestedAccessTokenVersion": 2,
      "oauth2PermissionScopes": [
        {
          "adminConsentDescription": "Allows Teams to call the app’s web APIs as the current user.",
          "adminConsentDisplayName": "Teams can access app’s web APIs",
          "id": "90e24c9e-6bb5-4a59-82b3-7f744e3bcb4c",
          "isEnabled": true,
          "type": "User",
          "userConsentDescription": "Enable Teams to call this app’s web APIs with the same rights that you have",
          "userConsentDisplayName": "Teams can access app’s web APIs and make requests on your behalf",
          "value": "access_as_user"
        }
      ],
      "preAuthorizedApplications": [
        {
          "appId": "1fec8e78-bce4-4aaf-ab1b-5451cc387264",
          "delegatedPermissionIds": [
            "90e24c9e-6bb5-4a59-82b3-7f744e3bcb4c"
          ]
        },
        {
          "appId": "5e3ce6c0-2b1f-4285-8d4b-75ee78787346",
          "delegatedPermissionIds": [
            "90e24c9e-6bb5-4a59-82b3-7f744e3bcb4c"
          ]
        }
      ]
    },
    "appRoles": [],
    "info": {
      "logoUrl": null,
      "marketingUrl": null,
      "privacyStatementUrl": null,
      "supportUrl": null,
      "termsOfServiceUrl": null
    },
    "keyCredentials": [],
    "optionalClaims": {
      "accessToken": [
        {
          "additionalProperties": [],
          "essential": false,
          "name": "idtyp",
          "source": null
        }
      ],
      "idToken": [],
      "saml2Token": []
    },
    "parentalControlSettings": {
      "countriesBlockedForMinors": [],
      "legalAgeGroupRule": "Allow"
    },
    "passwordCredentials": [
      {
        "customKeyIdentifier": null,
        "displayName": null,
        "endDateTime": "2023-07-22T09:19:47.8601311Z",
        "hint": "QBU",
        "keyId": "24ae17c4-c593-4ddc-a15e-440071204813",
        "secretText": null,
        "startDateTime": "2021-07-22T09:19:47.8601311Z"
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
      "redirectUris": [
        "https://EXAMPLE_SECRET_VALUE_PLACEHOLDER/auth-end.html"
      ],
      "implicitGrantSettings": {
        "enableAccessTokenIssuance": false,
        "enableIdTokenIssuance": false
      },
      "redirectUriSettings": [
        {
          "uri": "https://EXAMPLE_SECRET_VALUE_PLACEHOLDER/auth-end.html",
          "index": null
        }
      ]
    },
    "spa": {
      "redirectUris": []
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  addIns                           : []
  api                              : {"acceptMappedClaims":null,"knownClientApplications":[],"requestedAccessTokenVersion":2,"oauth2PermissionScopes":[{"adminConsentDescription":"Allows Teams to call the app’s web APIs as the current user.","adminConsentDisplayName":"Teams can access app’s web APIs","id":"90e24c9e-6bb5-4a59-82b3-7f744e3bcb4c","isEnabled":true,"type":"User","userConsentDescription":"Enable Teams to call this app’s web APIs with the same rights that you have","userConsentDisplayName":"Teams can access app’s web APIs and make requests on your behalf","value":"access_as_user"}],"preAuthorizedApplications":[{"appId":"1fec8e78-bce4-4aaf-ab1b-5451cc387264","delegatedPermissionIds":["90e24c9e-6bb5-4a59-82b3-7f744e3bcb4c"]},{"appId":"5e3ce6c0-2b1f-4285-8d4b-75ee78787346","delegatedPermissionIds":["90e24c9e-6bb5-4a59-82b3-7f744e3bcb4c"]}]}
  appId                            : 9eb465b4-eed9-4fb2-aa7a-4dfe18a52a4d
  appRoles                         : []
  applicationTemplateId            : null
  certification                    : null
  createdDateTime                  : 2021-07-22T09:19:45Z
  defaultRedirectUri               : null
  deletedDateTime                  : null
  description                      : null
  disabledByMicrosoftStatus        : null
  displayName                      : helloworld
  groupMembershipClaims            : null
  id                               : 0d2eb848-da5f-4131-b739-941150b3a43d
  identifierUris                   : ["api://EXAMPLE_SECRET_VALUE_PLACEHOLDER/9eb465b4-eed9-4fb2-aa7a-4dfe18a52a4d"]
  info                             : {"logoUrl":null,"marketingUrl":null,"privacyStatementUrl":null,"supportUrl":null,"termsOfServiceUrl":null}
  isDeviceOnlyAuthSupported        : null
  isFallbackPublicClient           : null
  keyCredentials                   : []
  notes                            : null
  optionalClaims                   : {"accessToken":[{"additionalProperties":[],"essential":false,"name":"idtyp","source":null}],"idToken":[],"saml2Token":[]}
  parentalControlSettings          : {"countriesBlockedForMinors":[],"legalAgeGroupRule":"Allow"}
  passwordCredentials              : [{"customKeyIdentifier":null,"displayName":null,"endDateTime":"2023-07-22T09:19:47.8601311Z","hint":"QBU","keyId":"24ae17c4-c593-4ddc-a15e-440071204813","secretText":null,"startDateTime":"2021-07-22T09:19:47.8601311Z"}]
  publicClient                     : {"redirectUris":[]}
  publisherDomain                  : contoso.onmicrosoft.com
  requestSignatureVerification     : null
  requiredResourceAccess           : [{"resourceAppId":"00000003-0000-0000-c000-000000000000","resourceAccess":[{"id":"e1fe6dd8-ba31-4d61-89e7-88639da4683d","type":"Scope"}]}]
  samlMetadataUrl                  : null
  serviceManagementReference       : null
  servicePrincipalLockConfiguration: null
  signInAudience                   : AzureADMyOrg
  spa                              : {"redirectUris":[]}
  tags                             : []
  tokenEncryptionKeyId             : null
  verifiedPublisher                : {"displayName":null,"verifiedPublisherId":null,"addedDateTime":null}
  web                              : {"homePageUrl":null,"logoutUrl":null,"redirectUris":["https://EXAMPLE_SECRET_VALUE_PLACEHOLDER/auth-end.html"],"implicitGrantSettings":{"enableAccessTokenIssuance":false,"enableIdTokenIssuance":false},"redirectUriSettings":[{"uri":"https://EXAMPLE_SECRET_VALUE_PLACEHOLDER/auth-end.html","index":null}]}
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,appId,createdDateTime,displayName,publisherDomain,signInAudience
  0d2eb848-da5f-4131-b739-941150b3a43d,9eb465b4-eed9-4fb2-aa7a-4dfe18a52a4d,2021-07-22T09:19:45Z,helloworld,contoso.onmicrosoft.com,AzureADMyOrg
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra app get --appId "9eb465b4-eed9-4fb2-aa7a-4dfe18a52a4d"

  Date: 2023-06-01

  ## helloworld (0d2eb848-da5f-4131-b739-941150b3a43d)

  Property | Value
  ---------|-------
  id | 0d2eb848-da5f-4131-b739-941150b3a43d
  appId | 9eb465b4-eed9-4fb2-aa7a-4dfe18a52a4d
  createdDateTime | 2021-07-22T09:19:45Z
  displayName | helloworld
  publisherDomain | contoso.onmicrosoft.com
  signInAudience | AzureADMyOrg
  ```

  </TabItem>
</Tabs>
