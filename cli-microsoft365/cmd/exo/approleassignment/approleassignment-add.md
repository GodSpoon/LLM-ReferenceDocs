-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# exo approleassignment add

Grants permissions to an application that's accessing data in Exchange Online and specify which mailboxes an app can access.

## Usage

```sh
m365 exo approleassignment add [options]
```

## Options

```md definition-list
`--roleDefinitionId [roleDefinitionId]`
: Id of a role to be assigned. Specify either `roleDefinitionId` or `roleDefinitionName`, but not both.

`--roleDefinitionName [roleDefinitionName]`
: Name of a role to be assigned. Specify either `roleDefinitionId` or `roleDefinitionName`, but not both.

`--principalId [principalId]`
: Id of a service principal to which the assignment is granted. Specify either `principalId` or `principalName`, but not both.

`--principalName [principalName]`
: Name of a service principal to which the assignment is granted. Specify either `principalId` or `principalName`, but not both.

`-s, --scope <scope>`	
: Scope of the roleassignment. Allowed values are: `tenant`, `administrativeUnit`, `group`, `user`, `custom`.

`--userId [userId]`	
: Id of a user to which the assignment is scoped. Specify either `userId` or `userName` when scope is set to `user`.

`--userName [userName]`
: UPN of a user to which the assignment is scoped. Specify either `userId` or `userName` when scope is set to `user`.

`--groupId [groupId]`
: Id of a group to which the assignment is scoped. Specify either `groupId` or `groupName` when scope is set to `group`.

`--groupName [groupName]`
: Name of a group to which the assignment is scoped. Specify either `groupId` or `groupName` when scope is set to `group`.

`--administrativeUnitId [administrativeUnitId]`
: Id of an administrative unit to which the assignment is scoped. Specify either `administrativeUnitId` or `administrativeUnitName` when scope is set to `administrativeUnit`.

`--administrativeUnitName [administrativeUnitName]`
: Name of an administrative unit to which the assignment is scoped. Specify either `administrativeUnitId` or `administrativeUnitName` when scope is set to `administrativeUnit`.

`--customAppScopeId [customAppScopeId]`
: Id of a custom application scope to which the assignment is scoped. Specify either `customAppScopeId` or `customAppScopeName` when scope is set to `custom`.

`--customAppScopeName [customAppScopeName]`
: Name of a custom application scope to which the assignment is scoped. Specify either `customAppScopeId` or `customAppScopeName` when scope is set to `custom`.
```

<Global />

## Remarks

:::info

To use this command you must be at least **Privileged Role Administrator**.

:::

## Examples

Assign a role specified by id to a service principal specified by id and scope the assignment to the whole tenant

```sh
m365 exo approleassignment add --roleDefinitionId 777b752-f9b7-4205-a2b1-5db0d6a0ccfc --principalId 7a2ca997-9461-402e-9882-58088a370889 --scope tenant
```

Assign a role specified by id to a service principal specified by id and scope the assignment to a user specified by id

```sh
m365 exo approleassignment add --roleDefinitionId 777b752-f9b7-4205-a2b1-5db0d6a0ccfc --principalId 7a2ca997-9461-402e-9882-58088a370889 --scope user --userId a4738dd8-fc0f-4646-87fb-47539f5c651b
```

Assign a role specified by name to a service principal specified by name and scope the assignment to a group specified by name

```sh
m365 exo approleassignment add --roleDefinitionName 'Application Contacts.ReadWrite' --principalName 'ContactsSyncApp' --scope group --groupName 'Marketing'
```

Assign a role specified by name to a service principal specified by id and scope the assignment to an administrative unit specified by name

```sh
m365 exo approleassignment add --roleDefinitionName 'Application Calendars.Read' --principalId fa631c4d-ac9f-4884-a7f5-13c659d177e3 --scope administrativeUnit --administrativeUnitName 'Equipment - EMEA'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "6615d221-3834-4f8f-bbc9-7d0d23620a8e",
    "principalId": "/ServicePrincipals/e483a0d9-8440-455e-8f9a-b9cac6b8b0ef",
    "roleDefinitionId": "1f704712-7d46-481f-b2cd-dbcc978c4f2a",
    "directoryScopeId": "/",
    "appScopeId": null
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  appScopeId      : null
  directoryScopeId: /
  id              : 6615d221-3834-4f8f-bbc9-7d0d23620a8e
  principalId     : /ServicePrincipals/e483a0d9-8440-455e-8f9a-b9cac6b8b0ef
  roleDefinitionId: 1f704712-7d46-481f-b2cd-dbcc978c4f2a
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,principalId,roleDefinitionId,directoryScopeId,appScopeId
  6615d221-3834-4f8f-bbc9-7d0d23620a8e,/ServicePrincipals/e483a0d9-8440-455e-8f9a-b9cac6b8b0ef,1f704712-7d46-481f-b2cd-dbcc978c4f2a,/,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # exo approleassignment add --debug "false" --verbose "false" --roleDefinitionId "1f704712-7d46-481f-b2cd-dbcc978c4f2a" --principalId "e483a0d9-8440-455e-8f9a-b9cac6b8b0ef" --scope tenant

  Date: 10/3/2024

  ## 6615d221-3834-4f8f-bbc9-7d0d23620a8e

  Property | Value
  ---------|-------
  id | 6615d221-3834-4f8f-bbc9-7d0d23620a8e
  principalId | /ServicePrincipals/e483a0d9-8440-455e-8f9a-b9cac6b8b0ef
  roleDefinitionId | 1f704712-7d46-481f-b2cd-dbcc978c4f2a
  directoryScopeId | /
  ```

  </TabItem>
</Tabs>

## More information

- Role assignment: https://learn.microsoft.com/graph/api/rbacapplication-post-roleassignments?view=graph-rest-beta

The table below lists the available roles and their corresponding ids that are accepted by the `roleDefinitionId` and `roleDefinitionName` parameters.

|Role Definition Id | Role Definition Name |
| --- | --- |
|1f704712-7d46-481f-b2cd-dbcc978c4f2a|Application Mail.Read|
|3eca55c8-0e73-4c12-81bf-526549f2e5a3|Application Mail.ReadBasic|
|82fd214e-61ca-4dc7-98f6-090700bdb205|Application Mail.ReadWrite|
|8679f4ff-c91d-40d0-809c-c86d114821a5|Application Mail.Send|
|c40299e0-2107-455f-85dd-6e8862c3a0cc|Application MailboxSettings.Read|
|459cb245-07c5-44f1-8133-3da40b4b6197|Application MailboxSettings.ReadWrite|
|a3123d4e-4256-4ad0-bef0-205a00807fae|Application Calendars.Read|
|b92761c0-5311-4908-92ca-2c1f8c71aa1c|Application Calendars.ReadWrite|
|9b87c446-d3c1-4146-9d39-45ae63b4eeb7|Application Contacts.Read|
|265cabb3-13d9-4e05-b2cd-460cfa7ad3cc|Application Contacts.ReadWrite|
|b49ae303-7a8f-4ba1-aa37-27b40461aabb|Application Mail Full Access|
|48d6a78c-0681-4d73-acec-9f9ffad56ddb|Application Exchange Full Access|

More info about supported application roles: https://learn.microsoft.com/exchange/permissions-exo/application-rbac#supported-application-roles
