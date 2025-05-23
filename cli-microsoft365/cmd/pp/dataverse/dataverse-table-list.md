-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp dataverse table list

Lists dataverse tables in a given environment

## Usage

```sh
m365 pp dataverse table list [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment to list all tables for.

`--asAdmin`
: Set, to retrieve the dataverse tables as admin for environments you are not a member of.
```

<Global />

## Examples

List all tables for the given environment.

```sh
m365 pp dataverse table list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"
```

List all tables for the given environment as Admin.

```sh
m365 pp dataverse table list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --asAdmin
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "MetadataId":"47a9636e-b7a1-4a8d-858a-ebce7d9b7526",
      "IsCustomEntity":true,
      "IsManaged":true,
      "SchemaName":"aaduser",
      "IconVectorName":null,
      "LogicalName":"aaduser",
      "EntitySetName":"aadusers",
      "IsActivity":false,
      "DataProviderId":"54629ed7-0cd3-4c85-9b6c-ea5f8548a9aa",
      "IsRenameable":{
        "Value":true,
        "CanBeChanged":false,
        "ManagedPropertyLogicalName":"isrenameable"
      },
      "IsCustomizable":{
        "Value":true,
        "CanBeChanged":false,
        "ManagedPropertyLogicalName":"iscustomizable"
      },
      "CanCreateForms":{
        "Value":true,
        "CanBeChanged":false,
        "ManagedPropertyLogicalName":"cancreateforms"
      },
      "CanCreateViews":{
        "Value":true,
        "CanBeChanged":false,
        "ManagedPropertyLogicalName":"cancreateviews"
      },
      "CanCreateCharts":{
        "Value":false,
        "CanBeChanged":false,
        "ManagedPropertyLogicalName":"cancreatecharts"
      },
      "CanCreateAttributes":{
        "Value":true,
        "CanBeChanged":false,
        "ManagedPropertyLogicalName":"cancreateattributes"
      },
      "CanChangeTrackingBeEnabled":{
        "Value":false,
        "CanBeChanged":false,
        "ManagedPropertyLogicalName":"canchangetrackingbeenabled"
      },
      "CanModifyAdditionalSettings":{
        "Value":true,
        "CanBeChanged":true,
        "ManagedPropertyLogicalName":"canmodifyadditionalsettings"
      },
      "CanChangeHierarchicalRelationship":{
        "Value":true,
        "CanBeChanged":true,
        "ManagedPropertyLogicalName":"canchangehierarchicalrelationship"
      },
      "CanEnableSyncToExternalSearchIndex":{
        "Value":true,
        "CanBeChanged":true,
        "ManagedPropertyLogicalName":"canenablesynctoexternalsearchindex"
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  SchemaName EntitySetName  LogicalName  IsManaged
  ---------- -------------  -----------  ---------
  aaduser    aadusers       aaduser      true
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  SchemaName,EntitySetName,LogicalName,IsManaged
  aaduser,aadusers,aaduser,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pp dataverse table list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

  Date: 9/1/2023

  Property | Value
  ---------|-------
  MetadataId | "47a9636e-b7a1-4a8d-858a-ebce7d9b7526
  IsCustomEntity | true
  IsManaged | false
  SchemaName | aaduser
  IconVectorName | null
  LogicalName | aaduser
  EntitySetName | aadusers
  IsActivity | false
  DataProviderId | 54629ed7-0cd3-4c85-9b6c-ea5f8548a9aa
  ```

  </TabItem>
</Tabs>
