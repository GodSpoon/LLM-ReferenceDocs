-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra pim role assignment list

Retrieves a list of Entra role assignments for a user or group.

## Usage

```sh
m365 entra pim role assignment list [options]
```

## Options

```md definition-list
`--userId [userId]`
: Id of the user to list role assignments for. Specify either `userId`, `userName`, `groupId` or `groupName`. If not specified, all assigned roles will be listed.

`--userName [userName]`
: UPN of the user to list role assignments for. Specify either `userId`, `userName`, `groupId` or `groupName`. If not specified, all assigned roles will be listed.

`--groupId [groupId]`
: Id of the group to list role assignments for. Specify either `userId`, `userName`, `groupId` or `groupName`. If not specified, all assigned roles will be listed.

`--groupName [groupName]`
: Display name of the group to list role assignments for. Specify either `userId`, `userName`, `groupId` or `groupName`. If not specified, all assigned roles will be listed.

`-s, --startDateTime [startDateTime]`
: An optional ISO 8601 formatted date filter to search from.

`--includePrincipalDetails`
: (deprecated. Use option `withPrincipalDetails` instead) An optional flag to include details of the principals that were assigned a role.

`--withPrincipalDetails`
: An optional flag to include details of the principals that were assigned a role.
```

<Global />

## Examples

Get a list of Entra role assignments.

```sh
m365 entra pim role assignment list
```

Get a list of Entra role assignments for the current user.

```sh
m365 entra pim role assignment list --userId '@meID'
```

Get a list of Entra role assignments since the first of January 2024.

```sh
m365 entra pim role assignment list --startDateTime 2024-01-01T00:00:00Z
```

Get a list of Entra role assignments with principal details.

```sh
m365 entra pim role assignment list --withPrincipalDetails
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "principalId": "61b0c52f-a902-4769-9a09-c6628335b00a",
      "roleDefinitionId": "fe930be7-5e62-47db-91af-98c3a49a38b1",
      "directoryScopeId": "/administrativeUnits/1a89e663-efcc-4911-8df7-e954714005de",
      "appScopeId": null,
      "startDateTime": "2023-11-15T12:24:32.773Z",
      "endDateTime": null,
      "assignmentType": "Assigned",
      "memberType": "Direct",
      "roleAssignmentOriginId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "roleAssignmentScheduleId": "36bd668f-3a40-455f-a40a-64074fde4a18",
      "roleDefinition": {
        "displayName": "User Administrator"
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                                                  principalId                           roleDefinitionId                      directoryScopeId                                           appScopeId  startDateTime             endDateTime  assignmentType  memberType  roleAssignmentOriginId                                              roleAssignmentScheduleId                                            roleDefinition
  ------------------------------------------------------------------  ------------------------------------  ------------------------------------  ---------------------------------------------------------  ----------  ------------------------  -----------  --------------  ----------  ------------------------------------------------------------------  ------------------------------------------------------------------  ---------------
  EXAMPLE_SECRET_VALUE_PLACEHOLDER  61b0c52f-a902-4769-9a09-c6628335b00a  fe930be7-5e62-47db-91af-98c3a49a38b1  /administrativeUnits/1a89e663-efcc-4911-8df7-e954714005de  null        2023-11-15T12:24:32.773Z  null         Assigned        Direct      EXAMPLE_SECRET_VALUE_PLACEHOLDER  36bd668f-3a40-455f-a40a-64074fde4a18                                [object Object]
  EXAMPLE_SECRET_VALUE_PLACEHOLDER                       d86c9ae0-6d7d-412f-82f4-cd24804210ac  fe930be7-5e62-47db-91af-98c3a49a38b1  /                                                          null        2024-02-12T08:47:02.91Z   null         Assigned        Direct      EXAMPLE_SECRET_VALUE_PLACEHOLDER                       5f2c16a0-4212-4fa2-afae-fc8bfdc527b6                                [object Object]
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,principalId,roleDefinitionId,directoryScopeId,appScopeId,startDateTime,endDateTime,assignmentType,memberType,roleAssignmentOriginId,roleAssignmentScheduleId
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,61b0c52f-a902-4769-9a09-c6628335b00a,fe930be7-5e62-47db-91af-98c3a49a38b1,/administrativeUnits/1a89e663-efcc-4911-8df7-e954714005de,,2023-11-15T12:24:32.773Z,,Assigned,Direct,EXAMPLE_SECRET_VALUE_PLACEHOLDER,36bd668f-3a40-455f-a40a-64074fde4a18
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,d86c9ae0-6d7d-412f-82f4-cd24804210ac,fe930be7-5e62-47db-91af-98c3a49a38b1,/,,2024-02-12T08:47:02.91Z,,Assigned,Direct,EXAMPLE_SECRET_VALUE_PLACEHOLDER,5f2c16a0-4212-4fa2-afae-fc8bfdc527b6
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra pim role assignment list

  Date: 2/23/2024

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  id | 5wuT\_mJe20eRr5jDpJo4sS\EXAMPLE_SECRET_VALUE_PLACEHOLDER
  principalId | 61b0c52f-a902-4769-9a09-c6628335b00a
  roleDefinitionId | fe930be7-5e62-47db-91af-98c3a49a38b1
  directoryScopeId | /administrativeUnits/1a89e663-efcc-4911-8df7-e954714005de
  startDateTime | 2023-11-15T12:24:32.773Z
  assignmentType | Assigned
  memberType | Direct
  roleAssignmentOriginId | 5wuT\_mJe20eRr5jDpJo4sS\EXAMPLE_SECRET_VALUE_PLACEHOLDER
  roleAssignmentScheduleId | 36bd668f-3a40-455f-a40a-64074fde4a18
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
      "principalId": "61b0c52f-a902-4769-9a09-c6628335b00a",
      "roleDefinitionId": "fe930be7-5e62-47db-91af-98c3a49a38b1",
      "directoryScopeId": "/administrativeUnits/1a89e663-efcc-4911-8df7-e954714005de",
      "appScopeId": null,
      "startDateTime": "2023-11-15T12:24:32.773Z",
      "endDateTime": null,
      "assignmentType": "Assigned",
      "memberType": "Direct",
      "roleAssignmentOriginId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "roleAssignmentScheduleId": "36bd668f-3a40-455f-a40a-64074fde4a18",
      "roleDefinition": {
        "displayName": "User Administrator"
      },
      "principal": {
        "id": "61b0c52f-a902-4769-9a09-c6628335b00a",
        "displayName": "Adele Vance",
        "userPrincipalName": "AdeleV@contoso.onmicrosoft.com",
        "mail": "AdeleV@contoso.onmicrosoft.com",
        "businessPhones": [
          "+1 425 555 0109"
        ],
        "givenName": "Adele",
        "jobTitle": "Retail Manager",
        "mobilePhone": null,
        "officeLocation": "18/2111",
        "preferredLanguage": "en-US",
        "surname": "Vance"
    }
  }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                                                  principalId                           roleDefinitionId                      directoryScopeId                                           appScopeId  startDateTime             endDateTime  assignmentType  memberType  roleAssignmentOriginId                                              roleAssignmentScheduleId                                            roleDefinition   principal
  ------------------------------------------------------------------  ------------------------------------  ------------------------------------  ---------------------------------------------------------  ----------  ------------------------  -----------  --------------  ----------  ------------------------------------------------------------------  ------------------------------------------------------------------  ---------------  ---------------
  EXAMPLE_SECRET_VALUE_PLACEHOLDER  61b0c52f-a902-4769-9a09-c6628335b00a  fe930be7-5e62-47db-91af-98c3a49a38b1  /administrativeUnits/1a89e663-efcc-4911-8df7-e954714005de  null        2023-11-15T12:24:32.773Z  null         Assigned        Direct      EXAMPLE_SECRET_VALUE_PLACEHOLDER  36bd668f-3a40-455f-a40a-64074fde4a18                                [object Object]  [object Object]
  EXAMPLE_SECRET_VALUE_PLACEHOLDER                       d86c9ae0-6d7d-412f-82f4-cd24804210ac  fe930be7-5e62-47db-91af-98c3a49a38b1  /                                                          null        2024-02-12T08:47:02.91Z   null         Assigned        Direct      EXAMPLE_SECRET_VALUE_PLACEHOLDER                       5f2c16a0-4212-4fa2-afae-fc8bfdc527b6                                [object Object]  [object Object]
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,principalId,roleDefinitionId,directoryScopeId,appScopeId,startDateTime,endDateTime,assignmentType,memberType,roleAssignmentOriginId,roleAssignmentScheduleId
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,61b0c52f-a902-4769-9a09-c6628335b00a,fe930be7-5e62-47db-91af-98c3a49a38b1,/administrativeUnits/1a89e663-efcc-4911-8df7-e954714005de,,2023-11-15T12:24:32.773Z,,Assigned,Direct,EXAMPLE_SECRET_VALUE_PLACEHOLDER,36bd668f-3a40-455f-a40a-64074fde4a18
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,d86c9ae0-6d7d-412f-82f4-cd24804210ac,fe930be7-5e62-47db-91af-98c3a49a38b1,/,,2024-02-12T08:47:02.91Z,,Assigned,Direct,EXAMPLE_SECRET_VALUE_PLACEHOLDER,5f2c16a0-4212-4fa2-afae-fc8bfdc527b6
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra pim role assignment list --withPrincipalDetails "true"

  Date: 3/31/2024

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  id | 5wuT\_mJe20eRr5jDpJo4sS\EXAMPLE_SECRET_VALUE_PLACEHOLDER
  principalId | 61b0c52f-a902-4769-9a09-c6628335b00a
  roleDefinitionId | fe930be7-5e62-47db-91af-98c3a49a38b1
  directoryScopeId | /administrativeUnits/1a89e663-efcc-4911-8df7-e954714005de
  startDateTime | 2023-11-15T12:24:32.773Z
  assignmentType | Assigned
  memberType | Direct
  roleAssignmentOriginId | 5wuT\_mJe20eRr5jDpJo4sS\EXAMPLE_SECRET_VALUE_PLACEHOLDER
  roleAssignmentScheduleId | 36bd668f-3a40-455f-a40a-64074fde4a18
  ```

  </TabItem>
</Tabs>
