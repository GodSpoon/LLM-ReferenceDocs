-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra administrativeunit roleassignment add

Assigns a Microsoft Entra role with administrative unit scope to a user

## Usage

```sh
m365 entra administrativeunit roleassignment add [options]
```

## Options

```md definition-list
`-i, --administrativeUnitId [administrativeUnitId]`
: The id of the administrative unit. Specify either `administrativeUnitId` or `administrativeUnitName`.

`-n, --administrativeUnitName [administrativeUnitName]`
: The name of the administrative unit. Specify either `administrativeUnitId` or `administrativeUnitName`.

`--roleDefinitionId [roleDefinitionId]`
: The id of the role definition that the member is in. Specify either `roleDefinitionId` or `roleDefinitionName`.

`--roleDefinitionName [roleDefinitionName]`
: The name of the role definition that the member is in. Specify either `roleDefinitionId` or `roleDefinitionName`.

`--userId [userId]`
: The id of the user that is a member of the scoped role. Specify either `userId` or `userName`.

`--userName [userName]`
: The name of the user that is a member of the scoped role. Specify either `userId` or `userName`.
```

<Global />

## Remarks

:::info

To use this command you must be either **Global Administrator** or **Privileged Role Administrator**.

:::

## Examples

Assign a role definition specified by id to a user specified by id for an administrative unit specified by id

```sh
m365 entra administrativeunit roleassignment add --administrativeUnitId 81bb36e4-f4c6-4984-8e56-d4f8feae9e09 --roleDefinitionId 4d6ac14f-3453-41d0-bef9-a3e0c569773a --userId 5f91f951-7305-4a27-9b63-7b00906de09f
```

Assign a role definition specified by name to a user specified by name for an administrative unit specified by name

```sh
m365 entra administrativeunit roleassignment add --administrativeUnitName 'Marketing Division' --roleDefinitionName 'License Administrator' --userName 'john.doe@contoso.com'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "principalId": "5f91f951-7305-4a27-9b63-7b00906de09f",
    "directoryScopeId": "/administrativeUnits/81bb36e4-f4c6-4984-8e56-d4f8feae9e09",
    "roleDefinitionId": "4d6ac14f-3453-41d0-bef9-a3e0c569773a"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  directoryScopeId: /administrativeUnits/81bb36e4-f4c6-4984-8e56-d4f8feae9e09
  id              : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  principalId     : 5f91f951-7305-4a27-9b63-7b00906de09f
  roleDefinitionId: 4d6ac14f-3453-41d0-bef9-a3e0c569773a
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,principalId,directoryScopeId,roleDefinitionId
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,5f91f951-7305-4a27-9b63-7b00906de09f,/administrativeUnits/81bb36e4-f4c6-4984-8e56-d4f8feae9e09,4d6ac14f-3453-41d0-bef9-a3e0c569773a
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra administrativeunit roleassignment add --administrativeUnitId "81bb36e4-f4c6-4984-8e56-d4f8feae9e09" --roleDefinitionId "4d6ac14f-3453-41d0-bef9-a3e0c569773a" --userId "5f91f951-7305-4a27-9b63-7b00906de09f"

  Date: 11/16/2023

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER\_kNruBxvSESY5W1Pj-rp4J-2
  principalId | 5f91f951-7305-4a27-9b63-7b00906de09f
  directoryScopeId | /administrativeUnits/81bb36e4-f4c6-4984-8e56-d4f8feae9e09
  roleDefinitionId | 4d6ac14f-3453-41d0-bef9-a3e0c569773a
  ```

  </TabItem>
</Tabs>

## More information

- [Roles with administrative unit scope](https://learn.microsoft.com/entra/identity/role-based-access-control/admin-units-assign-roles#EXAMPLE_SECRET_VALUE_PLACEHOLDER)
