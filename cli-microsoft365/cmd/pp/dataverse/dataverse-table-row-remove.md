-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# pp dataverse table row remove

Removes a row from a dataverse table in a given environment.

## Usage

```sh
m365 pp dataverse table row remove [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment to remove a row from a table from.

`-i, --id <id>`
: The id of the row to remove.

`--entitySetName [entitySetName]`
: The entity set name of the table. Specify either `entitySetName` or `tableName` but not both

`--tableName [tableName]`
: The name of the table. Specify either `entitySetName` or `tableName` but not both

`-f, --force`
: Don't prompt for confirmation

`--asAdmin`
: Set, to remove the row from the dataverse table as admin for environments you are not a member of.
```

<Global />

## Examples

Removes a row from a dataverse table in a given environment

```sh
m365 pp dataverse table row remove --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --tableName "aadusers" --id "21d01cf4-356c-ed11-9561-000d3a4bbea4"
```

Removes a row from a dataverse table in a given environment as Admin

```sh
m365 pp dataverse table row remove --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --tableName "aadusers" --id "21d01cf4-356c-ed11-9561-000d3a4bbea4" --asAdmin
```

Removes a row from a dataverse table in a given environment without prompting for confirmation

```sh
m365 pp dataverse table row remove --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --tableName "aadusers" --id "21d01cf4-356c-ed11-9561-000d3a4bbea4" --force
```

Removes a row from a dataverse table in a given environment based on the entity set name without prompting for confirmation

```sh
m365 pp dataverse table row remove --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --entitySetName "cr6c3_accounts" --id "21d01cf4-356c-ed11-9561-000d3a4bbea4" --force
```

## Response

The command won't return a response on success.
