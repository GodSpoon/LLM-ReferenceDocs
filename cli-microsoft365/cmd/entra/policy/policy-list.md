-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra policy list

Returns policies from Entra ID

## Usage

```sh
m365 entra policy list [options]
```

## Options

```md definition-list
`-t, --type [type]`
: The type of policies to return. Allowed values `activityBasedTimeout`, `adminConsentRequest`, `appManagement`, `authenticationFlows`, `authenticationMethods`, `authenticationStrength`, `authorization`, `claimsMapping`, `conditionalAccess`, `crossTenantAccess`, `defaultAppManagement`, `deviceRegistration`, `featureRolloutPolicy`, `homeRealmDiscovery`, `identitySecurityDefaultsEnforcement`, `permissionGrant`, `roleManagement`, `tokenIssuance`, `tokenLifetime`. If omitted, all policies are returned.
```

<Global />

## Examples

Returns all policies from Entra ID.

```sh
m365 entra policy list
```

Returns claim-mapping policies from Entra ID.

```sh
m365 entra policy list --type "claimsMapping"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "authorizationPolicy",
      "allowInvitesFrom": "everyone",
      "allowedToSignUpEmailBasedSubscriptions": true,
      "allowedToUseSSPR": true,
      "EXAMPLE_SECRET_VALUE_PLACEHOLDER": true,
      "allowUserConsentForRiskyApps": null,
      "blockMsolPowerShell": false,
      "displayName": "Authorization Policy",
      "description": "Used to manage authorization related settings across the company.",
      "guestUserRoleId": "10dae51f-b6af-4016-8d66-8c2a99b929b3",
      "defaultUserRolePermissions": {
        "allowedToCreateApps": true,
        "allowedToCreateSecurityGroups": true,
        "allowedToCreateTenants": true,
        "EXAMPLE_SECRET_VALUE_PLACEHOLDER": true,
        "allowedToReadOtherUsers": true,
        "permissionGrantPoliciesAssigned": [
          "EXAMPLE_SECRET_VALUE_PLACEHOLDER"
        ]
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    displayName
  ------------------------------------  --------------------
  authorizationPolicy                   Authorization Policy
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,allowInvitesFrom,allowedToSignUpEmailBasedSubscriptions,allowedToUseSSPR,EXAMPLE_SECRET_VALUE_PLACEHOLDER,blockMsolPowerShell,displayName,description,guestUserRoleId
  authorizationPolicy,everyone,1,1,1,,Authorization Policy,Used to manage authorization related settings across the company.,10dae51f-b6af-4016-8d66-8c2a99b929b3
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra policy list

  Date: 2023-06-02

  ## Authorization Policy (authorizationPolicy)

  Property | Value
  ---------|-------
  id | authorizationPolicy
  allowInvitesFrom | everyone
  allowedToSignUpEmailBasedSubscriptions | true
  allowedToUseSSPR | true
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | true
  blockMsolPowerShell | false
  displayName | Authorization Policy
  description | Used to manage authorization related settings across the company.
  guestUserRoleId | 10dae51f-b6af-4016-8d66-8c2a99b929b3
  ```

  </TabItem>
</Tabs>

## More information

- Microsoft Graph Entra ID policy overview: [https://learn.microsoft.com/graph/api/resources/policy-overview?view=graph-rest-1.0](https://learn.microsoft.com/graph/api/resources/policy-overview?view=graph-rest-1.0)
