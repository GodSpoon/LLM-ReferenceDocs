-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# planner tenant settings list

Lists the Microsoft Planner configuration of the tenant

## Usage

```sh
m365 planner tenant settings list [options]
```

## Options

<Global />

## Remarks

:::info

To use this command you must be a global administrator.

:::

After executing the command `planner tenant settings set`, it can take some time for all changes to propagate across the tenant. Because of this, executing this command right away can return some unexpected results.

## Examples

Lists the Microsoft Planner settings of the tenant.

```sh
m365 planner tenant settings list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "1",
    "isPlannerAllowed": true,
    "allowCalendarSharing": true,
    "allowTenantMoveWithDataLoss": false,
    "allowTenantMoveWithDataMigration": false,
    "allowRosterCreation": true,
    "allowPlannerMobilePushNotifications": true
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  allowCalendarSharing               : true
  allowPlannerMobilePushNotifications: true
  allowRosterCreation                : true
  allowTenantMoveWithDataLoss        : false
  allowTenantMoveWithDataMigration   : false
  isPlannerAllowed                   : true
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  isPlannerAllowed,allowCalendarSharing,allowTenantMoveWithDataLoss,allowTenantMoveWithDataMigration,allowRosterCreation,allowPlannerMobilePushNotifications
  1,1,,,1,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # planner tenant settings list

  Date: 4/2/2023

  ## 1

  Property | Value
  ---------|-------
  id | 1
  isPlannerAllowed | true
  allowCalendarSharing | true
  allowTenantMoveWithDataLoss | false
  allowTenantMoveWithDataMigration | false
  allowRosterCreation | true
  allowPlannerMobilePushNotifications | true
  ```

  </TabItem>
</Tabs>
