-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra pim role assignment eligibility list

Retrieves a list of eligible roles a user or group can be assigned to

## Usage

```sh
m365 entra pim role assignment eligibility list [options]
```

## Options

```md definition-list
`--userId [userId]`
: Id of the user for which to list eligible roles. Specify either `userId`, `userName`, `groupId` or `groupName`. If not specified, all eligible roles will be listed.

`--userName [userName]`
: UPN of the user for which to list eligible roles. Specify either `userId`, `userName`, `groupId` or `groupName`. If not specified, all eligible roles will be listed.

`--groupId [groupId]`
: Id of the group for which to list eligible roles. Specify either `userId`, `userName`, `groupId` or `groupName`. If not specified, all eligible roles will be listed.

`--groupName [groupName]`
: Display name of the group for which to list eligible roles. Specify either `userId`, `userName`, `groupId` or `groupName`. If not specified, all eligible roles will be listed.

`--includePrincipalDetails`
: (deprecated. Use option `withPrincipalDetails` instead) An optional flag to include details of the principals that were eligible for a role.

`--withPrincipalDetails`
: An optional flag to include details of the principals that were eligible for a role.
```

<Global />

## Examples

Get a list of eligible roles for any user.

```sh
m365 entra pim role assignment eligibility list
```

Get a list of eligible roles for the current user.

```sh
m365 entra pim role assignment eligibility list --userId '@meID'
```

Get a list of eligible roles for any user with principal details.

```sh
m365 entra pim role assignment eligibility list --withPrincipalDetails
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "principalId": "52f26d18-d151-434f-ae14-a4a83122b2b2",
      "roleDefinitionId": "0964bb5e-9bdb-4d7b-ac29-58e794862a40",
      "directoryScopeId": "/",
      "appScopeId": null,
      "startDateTime": "2024-04-08T10:14:01.153Z",
      "endDateTime": null,
      "memberType": "Direct",
      "roleEligibilityScheduleId": "7a135e3d-5be5-403c-bdad-47ccbac434e3",
      "roleDefinitionName": "displayName": "Search Administrator"
    }  
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  roleDefinitionId                      roleDefinitionName    principalId
  ------------------------------------  --------------------  ------------------------------------
  0964bb5e-9bdb-4d7b-ac29-58e794862a40  Search Administrator  52f26d18-d151-434f-ae14-a4a83122b2b2
  744ec460-397e-42ad-a462-8b3f9747a02c  Knowledge Manager     61b0c52f-a902-4769-9a09-c6628335b00a
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,principalId,roleDefinitionId,directoryScopeId,appScopeId,startDateTime,endDateTime,memberType,roleEligibilityScheduleId,roleDefinitionName
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,52f26d18-d151-434f-ae14-a4a83122b2b2,0964bb5e-9bdb-4d7b-ac29-58e794862a40,/,,2024-04-08T10:14:01.153Z,,Direct,7a135e3d-5be5-403c-bdad-47ccbac434e3,Search Administrator
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,61b0c52f-a902-4769-9a09-c6628335b00a,744ec460-397e-42ad-a462-8b3f9747a02c,/,,2024-04-08T10:13:04.913Z,2025-04-08T10:12:36.9Z,Direct,0606b8a1-ba92-42b7-804c-8e32dfdec2b8,Knowledge Manager
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra pim role assignment eligibility list

  Date: 4/8/2024

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  principalId | 52f26d18-d151-434f-ae14-a4a83122b2b2
  roleDefinitionId | 0964bb5e-9bdb-4d7b-ac29-58e794862a40
  directoryScopeId | /
  startDateTime | 2024-04-08T10:14:01.153Z
  memberType | Direct
  roleEligibilityScheduleId | 7a135e3d-5be5-403c-bdad-47ccbac434e3
  roleDefinitionName | Search Administrator
  ```

  </TabItem>
</Tabs>

### `withPrincipalDetails` response

When we make use of the option `withPrincipalDetails` the response will differ. 

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "principalId": "52f26d18-d151-434f-ae14-a4a83122b2b2",
      "roleDefinitionId": "0964bb5e-9bdb-4d7b-ac29-58e794862a40",
      "directoryScopeId": "/",
      "appScopeId": null,
      "startDateTime": "2024-04-08T10:14:01.153Z",
      "endDateTime": null,
      "memberType": "Direct",
      "roleEligibilityScheduleId": "7a135e3d-5be5-403c-bdad-47ccbac434e3",
      "roleDefinitionName": "Search Administrator",
      "principal": {
        "id": "52f26d18-d151-434f-ae14-a4a83122b2b2",
        "displayName": "Alex Wilber",
        "userPrincipalName": "AlexW@contoso.onmicrosoft.com",
        "mail": "AlexW@contoso.onmicrosoft.com",
        "businessPhones": [
          "+1 858 555 0110"
        ],
        "givenName": "Alex",
        "jobTitle": "Marketing Assistant",
        "mobilePhone": null,
        "officeLocation": "131/1104",
        "preferredLanguage": "en-US",
        "surname": "Wilber"
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  roleDefinitionId                      roleDefinitionName    principalId
  ------------------------------------  --------------------  ------------------------------------
  0964bb5e-9bdb-4d7b-ac29-58e794862a40  Search Administrator  52f26d18-d151-434f-ae14-a4a83122b2b2
  744ec460-397e-42ad-a462-8b3f9747a02c  Knowledge Manager     61b0c52f-a902-4769-9a09-c6628335b00a
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,principalId,roleDefinitionId,directoryScopeId,appScopeId,startDateTime,endDateTime,memberType,roleEligibilityScheduleId,roleDefinitionName
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,52f26d18-d151-434f-ae14-a4a83122b2b2,0964bb5e-9bdb-4d7b-ac29-58e794862a40,/,,2024-04-08T10:14:01.153Z,,Direct,7a135e3d-5be5-403c-bdad-47ccbac434e3,Search Administrator
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,61b0c52f-a902-4769-9a09-c6628335b00a,744ec460-397e-42ad-a462-8b3f9747a02c,/,,2024-04-08T10:13:04.913Z,2025-04-08T10:12:36.9Z,Direct,0606b8a1-ba92-42b7-804c-8e32dfdec2b8,Knowledge Manager
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra pim role assignment eligibility list --withPrincipalDetails "true"

  Date: 4/8/2024

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  principalId | 52f26d18-d151-434f-ae14-a4a83122b2b2
  roleDefinitionId | 0964bb5e-9bdb-4d7b-ac29-58e794862a40
  directoryScopeId | /
  startDateTime | 2024-04-08T10:14:01.153Z
  memberType | Direct
  roleEligibilityScheduleId | 7a135e3d-5be5-403c-bdad-47ccbac434e3
  roleDefinitionName | Search Administrator
  ```

  </TabItem>
</Tabs>
