-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra pim role assignment add

Request activation of an Entra role assignment for a user or group.

## Usage

```sh
m365 entra pim role assignment add [options]
```

## Options

```md definition-list
`-n, --roleDefinitionName [roleDefinitionName]`	
: Name of the role definition that should be assigned. Specify either `roleDefinitionName` or `roleDefinitionId` but not both.

`-i, --roleDefinitionId [roleDefinitionId]`	
: Id of the role definition that is being assigned. Specify either `roleDefinitionName` or `roleDefinitionId` but not both.

`--userId [userId]`	
: Id of the user that will be granted the assignment. Specify either `userId`, `userName`, `groupId` or `groupName`. If not specified, the current user will be used.

`--userName [userName]`	
: UPN of the user that will be granted the assignment. Specify either `userId`, `userName`, `groupId` or `groupName`. If not specified, the current user will be used.

`--groupId [groupId]`
: Id of the group that will be granted the assignment. Specify either `userId`, `userName`, `groupId` or `groupName`. If not specified, the current user will be used.

`--groupName [groupName]`
: Display name of the group that will be granted the assignment. Specify either `userId`, `userName`, `groupId` or `groupName`. If not specified, the current user will be used.

`--administrativeUnitId [administrativeUnitId]`
: Id of the administrative unit representing the scope of the assignment. Specify either `administrativeUnitId` or `applicationId`. If not specified, default scope will be tenant-wide.

`--applicationId [applicationId]`
: Object Id of the application representing the scope of the assignment. Specify either `administrativeUnitId` or `applicationId`. If not specified, default scope will be tenant-wide.

`-j, --justification [justification]`
: An optional justification message.

`-s, --startDateTime [startDateTime]`
: When the assignment should start. If left out, the assignment will start from the current time.

`-e, --endDateTime [endDateTime]`
: When the assignment should end. Specify either `duration`, `endDateTime` or `noExpiration`.

`-d, --duration [duration]`
: How long the assignment should last. Write in ISO 8601 format for durations: PT3H for 3 hours. Specify either `duration`, `endDateTime` or `noExpiration`.

`--noExpiration [noExpiration]`
: If specified, the role assignment will never expire. Specify either `duration`, `endDateTime` or `noExpiration`.

`--ticketNumber [ticketNumber]`
: Optional ticket number value to communicate with the request.

`--ticketSystem [ticketSystem]`
: Optional ticket system to communicate with the request.
```

<Global />

## Remarks

:::info

When activating a role for other users, you must be **Privileged Role Administrator**.

:::

## Examples

Request activation of the SharePoint Administrator Entra role assignment for the current user.

```sh
m365 entra pim role assignment add --roleDefinitionName 'SharePoint Administrator'
```

Request activation of an Entra role assignment for the current user.

```sh
m365 entra pim role assignment add --roleDefinitionId 'f1417aa3-bf0b-4cc5-a845-a0b2cf11f690'
```

Request activation of an Entra role assignment for the current user with a justification and max duration of 4 hours.

```sh
m365 entra pim role assignment add --roleDefinitionId 'f1417aa3-bf0b-4cc5-a845-a0b2cf11f690' --justification 'Need Global Admin to release application xyz to production' --duration 'PT4H'
```

Request activation of an Entra role assignment for a specified user with tenant scope.

```sh
m365 entra pim role assignment add --roleDefinitionId 'f1417aa3-bf0b-4cc5-a845-a0b2cf11f690' --userId '3488d6b8-6b2e-41c3-9583-1991205323c2'
```

Request activation of the User Administrator Entra role assignment for a specified group with administrative unit scope.

```sh
m365 entra pim role assignment add --roleDefinitionName 'User Administrator' --groupId '3488d6b8-6b2e-41c3-9583-1991205323c2' --administrativeUnitId '03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7'
```

Request activation of the Application Administrator Entra role assignment for a specified group with scope to a specific application.

```sh
m365 entra pim role assignment add --roleDefinitionName 'Application Administrator' --groupName 'Applications admins' --applicationId '03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7'
```

Request activation of an Entra role assignment for a specific period of two days.

```sh
m365 entra pim role assignment add --roleDefinitionName 'Global Administrator' --userName 'admin-john@contoso.com' --startDateTime '2024-01-10T09:00:00Z' --endDateTime '2024-01-11T17:00:00Z'
```

Request activation of an Entra role assignment with no expiration.

```sh
m365 entra pim role assignment add --roleDefinitionName 'Global Administrator' --userName 'admin-john@contoso.com' --noExpiration
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "3f7d1bd6-a9a5-45bc-b831-00cfa3e3c649",
    "status": "Provisioned",
    "createdDateTime": "2024-02-12T13:54:21.3110096Z",
    "completedDateTime": "2024-02-12T13:54:21.9847061Z",
    "approvalId": null,
    "customData": null,
    "action": "adminAssign",
    "principalId": "61b0c52f-a902-4769-9a09-c6628335b00a",
    "roleDefinitionId": "f28a1f50-f6e7-4571-818b-6a12f2af6b6c",
    "directoryScopeId": "/",
    "appScopeId": null,
    "isValidationOnly": false,
    "targetScheduleId": "3f7d1bd6-a9a5-45bc-b831-00cfa3e3c649",
    "justification": "Need SharePoint Administrator role",
    "createdBy": {
      "application": null,
      "device": null,
      "user": {
        "displayName": null,
        "id": "893f9116-e024-4bc6-8e98-54c245129485"
      }
    },
    "scheduleInfo": {
      "startDateTime": "2024-02-12T13:54:21.9847061Z",
      "recurrence": null,
      "expiration": {
        "type": "noExpiration",
        "endDateTime": null,
        "duration": null
      }
    },
    "ticketInfo": {
      "ticketNumber": null,
      "ticketSystem": null
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  action           : adminAssign
  appScopeId       : null
  approvalId       : null
  completedDateTime: 2024-02-12T14:02:09.8938321Z
  createdBy        : {"application":null,"device":null,"user":{"displayName":null,"id":"893f9116-e024-4bc6-8e98-54c245129485"}}
  createdDateTime  : 2024-02-12T14:02:09.4658344Z
  customData       : null
  directoryScopeId : /
  id               : c221e106-0711-470a-83cf-f8d7cbc51ecd
  isValidationOnly : false
  justification    : Need SharePoint Administrator role
  principalId      : 61b0c52f-a902-4769-9a09-c6628335b00a
  roleDefinitionId : f28a1f50-f6e7-4571-818b-6a12f2af6b6c
  scheduleInfo     : {"startDateTime":"2024-02-12T14:02:09.8938321Z","recurrence":null,"expiration":{"type":"noExpiration","endDateTime":null,"duration":null}}
  status           : Provisioned
  targetScheduleId : c221e106-0711-470a-83cf-f8d7cbc51ecd
  ticketInfo       : {"ticketNumber":null,"ticketSystem":null}
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,status,createdDateTime,completedDateTime,approvalId,customData,action,principalId,roleDefinitionId,directoryScopeId,appScopeId,isValidationOnly,targetScheduleId,justification
  7d727f44-c2dd-459e-8665-99ce003d12a9,Provisioned,2024-02-12T14:08:54.881749Z,2024-02-12T14:08:55.2507639Z,,,adminAssign,61b0c52f-a902-4769-9a09-c6628335b00a,f28a1f50-f6e7-4571-818b-6a12f2af6b6c,/,,,7d727f44-c2dd-459e-8665-99ce003d12a9,Need SharePoint Administrator role
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra pim roleassignment add --roleDefinitionId "f28a1f50-f6e7-4571-818b-6a12f2af6b6c" --userId "61b0c52f-a902-4769-9a09-c6628335b00a" --justification "Need SharePoint Administrator role"

  Date: 2/13/2024

  ## 7622802f-648b-4dd9-820f-dccaf8bbbab5

  Property | Value
  ---------|-------
  id | 7622802f-648b-4dd9-820f-dccaf8bbbab5
  status | Provisioned
  createdDateTime | 2024-02-13T18:34:13.5365923Z
  completedDateTime | 2024-02-13T18:34:14.269623Z
  action | adminAssign
  principalId | 61b0c52f-a902-4769-9a09-c6628335b00a
  roleDefinitionId | f28a1f50-f6e7-4571-818b-6a12f2af6b6c
  directoryScopeId | /
  isValidationOnly | false
  targetScheduleId | 7622802f-648b-4dd9-820f-dccaf8bbbab5
  justification | Need SharePoint Administrator role
  ```

  </TabItem>
</Tabs>

## More information

- Role assignment request: https://learn.microsoft.com/graph/api/EXAMPLE_SECRET_VALUE_PLACEHOLDER
