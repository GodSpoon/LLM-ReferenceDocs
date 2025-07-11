-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra organization list

Retrieves a list of organizations

## Usage

```sh
m365 entra organization list [options]
```

## Options

```md definition-list
`-p, --properties [properties]`
: The comma separated list of properties to be returned.
```

<Global />

## Remarks

:::info

Applications granted the `User.Read` permission are able to read only the id, displayName, and verifiedDomains properties of the organization. 
All other properties return with null values. To read all properties, use at least `Organization.Read.All`.

:::

## Examples

Retrieve organizations

```sh
m365 entra organization list
```

Retrieve specific info

```sh
m365 entra organization list --properties 'id,displayName,tenantType'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "e65b162c-6f87-4eb1-a24e-1b37d3504663",
      "deletedDateTime": null,
      "businessPhones": [
        "4258828080"
      ],
      "city": null,
      "country": null,
      "countryLetterCode": "IE",
      "createdDateTime": "2023-02-21T19:56:38Z",
      "defaultUsageLocation": null,
      "displayName": "Contoso",
      "EXAMPLE_SECRET_VALUE_PLACEHOLDER": null,
      "marketingNotificationEmails": [],
      "onPremisesLastSyncDateTime": null,
      "onPremisesSyncEnabled": null,
      "partnerTenantType": null,
      "postalCode": null,
      "preferredLanguage": "en",
      "securityComplianceNotificationMails": [],
      "securityComplianceNotificationPhones": [],
      "state": null,
      "street": null,
      "technicalNotificationMails": [
        "john.doe@contoso.com"
      ],
      "tenantType": "AAD",
      "directorySizeQuota": {
        "used": 1400,
        "total": 300000
      },
      "assignedPlans": [],
      "onPremisesSyncStatus": [],
      "privacyProfile": {
        "contactEmail": "john.doe@contoso.com",
        "statementUrl": ""
      },
      "provisionedPlans": [],
      "verifiedDomains": [
        {
          "capabilities": "Email, OfficeCommunicationsOnline",
          "isDefault": true,
          "isInitial": true,
          "name": "contoso.onmicrosoft.com",
          "type": "Managed"
        },
        {
          "capabilities": "Email, OfficeCommunicationsOnline, MoeraDomain",
          "isDefault": false,
          "isInitial": false,
          "name": "contoso2.onmicrosoft.com",
          "type": "Managed"
        }
      ]
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  displayName: Contoso
  id         : e65b162c-6f87-4eb1-a24e-1b37d3504663
  tenantType : AAD
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,deletedDateTime,city,country,countryLetterCode,createdDateTime,defaultUsageLocation,displayName,EXAMPLE_SECRET_VALUE_PLACEHOLDER,onPremisesLastSyncDateTime,onPremisesSyncEnabled,partnerTenantType,postalCode,preferredLanguage,state,street,tenantType
  e65b162c-6f87-4eb1-a24e-1b37d3504663,,,,IE,2023-02-21T19:56:38Z,,Contoso,,,,,,en,,,AAD
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra organization list --debug "false" --verbose "false"

  Date: 4/18/2025

  ## Contoso (e65b162c-6f87-4eb1-a24e-1b37d3504663)

  Property | Value
  ---------|-------
  id | e65b162c-6f87-4eb1-a24e-1b37d3504663
  countryLetterCode | IE
  createdDateTime | 2023-02-21T19:56:38Z
  displayName | Contoso
  preferredLanguage | en
  tenantType | AAD
  ```

  </TabItem>
</Tabs>

## More information

- Organization: https://learn.microsoft.com/graph/api/organization-list
