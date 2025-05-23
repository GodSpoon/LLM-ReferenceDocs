-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp dataverse table row list

Lists table rows for the given Dataverse table

## Usage

```sh
m365 pp dataverse table row list [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment

`--entitySetName [entitySetName]`
: The entity set name of the table. Specify either `entitySetName` or `tableName` but not both

`--tableName [tableName]`
: The name of the table. Specify either `entitySetName` or `tableName` but not both

`--asAdmin`
: Run the command as admin for environments you do not have explicitly assigned permissions to
```

<Global />

## Examples

List all table rows for the given environment based on the entity set name

```sh
m365 pp dataverse table row list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --entitySetName "cr6c3_accounts"
```

List all table rows for the given environment based on the table name

```sh
m365 pp dataverse table row list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --tableName "cr6c3_account"
```

List all table rows for the given environment based on the entity set name as Admin

```sh
m365 pp dataverse table row list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --entitySetName "cr6c3_accounts" --asAdmin
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "cr6c3_accountsid": "95c80273-3764-ed11-9561-000d3a4bbea4",
      "_owningbusinessunit_value": "6da087c1-1c4d-ed11-bba1-000d3a2caf7f",
      "statecode": 0,
      "statuscode": 1,
      "_createdby_value": "5fa787c1-1c4d-ed11-bba1-000d3a2caf7f",
      "_ownerid_value": "5fa787c1-1c4d-ed11-bba1-000d3a2caf7f",
      "modifiedon": "2022-11-14T16:14:45Z",
      "_owninguser_value": "5fa787c1-1c4d-ed11-bba1-000d3a2caf7f",
      "_modifiedby_value": "5fa787c1-1c4d-ed11-bba1-000d3a2caf7f",
      "versionnumber": 1413873,
      "createdon": "2022-11-14T16:14:45Z",
      "cr6c3_name": "Column1 value",
      "overriddencreatedon": null,
      "importsequencenumber": null,
      "_modifiedonbehalfby_value": null,
      "utcconversiontimezonecode": null,
      "_createdonbehalfby_value": null,
      "_owningteam_value": null,
      "timezoneruleversionnumber": null
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  cr6c3_accountsid                       _owningbusinessunit_value             statecode  statuscode  _createdby_value                      _ownerid_value                        modifiedon            _owninguser_value                     _modifiedby_value                     versionnumber  createdon             cr6c3_name      overriddencreatedon  importsequencenumber  _modifiedonbehalfby_value  utcconversiontimezonecode  _createdonbehalfby_value  _owningteam_value  timezoneruleversionnumber
  ------------------------------------  ------------------------------------  ---------  ----------  ------------------------------------  ------------------------------------  --------------------  ------------------------------------  ------------------------------------  -------------  --------------------  ----------      -------------------  --------------------  -------------------------  -------------------------  ------------------------  -----------------  -------------------------
  95c80273-3764-ed11-9561-000d3a4bbea4  6da087c1-1c4d-ed11-bba1-000d3a2caf7f  0          1           5fa787c1-1c4d-ed11-bba1-000d3a2caf7f  5fa787c1-1c4d-ed11-bba1-000d3a2caf7f  2022-11-14T16:14:45Z  5fa787c1-1c4d-ed11-bba1-000d3a2caf7f  5fa787c1-1c4d-ed11-bba1-000d3a2caf7f  1413873        2022-11-14T16:14:45Z  Column1 value   null                 null                  null                       null                       null                      null               null
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  cr6c3_accountsid,_owningbusinessunit_value,statecode,statuscode,_createdby_value,_ownerid_value,modifiedon,_owninguser_value,_modifiedby_value,versionnumber,createdon,cr6c3_name,overriddencreatedon,importsequencenumber,_modifiedonbehalfby_value,utcconversiontimezonecode,_createdonbehalfby_value,_owningteam_value,timezoneruleversionnumber
  95c80273-3764-ed11-9561-000d3a4bbea4,6da087c1-1c4d-ed11-bba1-000d3a2caf7f,0,1,5fa787c1-1c4d-ed11-bba1-000d3a2caf7f,5fa787c1-1c4d-ed11-bba1-000d3a2caf7f,2022-11-14T16:14:45Z,5fa787c1-1c4d-ed11-bba1-000d3a2caf7f,5fa787c1-1c4d-ed11-bba1-000d3a2caf7f,1413873,2022-11-14T16:14:45Z,Column1 value,,,,,,,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pp dataverse table row list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --tableName "cr6c3_accounts"

  Date: 9/1/2023

  Property | Value
  ---------|-------
  cr6c3\_accountsid | 95c80273-3764-ed11-9561-000d3a4bbea4
  \_owningbusinessunit\_value | 6da087c1-1c4d-ed11-bba1-000d3a2caf7f
  statecode | 0
  statuscode | 1
  \_createdby\_value | 5fa787c1-1c4d-ed11-bba1-000d3a2caf7f
  \_ownerid\_value | 5fa787c1-1c4d-ed11-bba1-000d3a2caf7f
  modifiedon | 2022-11-14T16:14:45Z
  \_owninguser\_value | 5fa787c1-1c4d-ed11-bba1-000d3a2caf7f
  \_modifiedby\_value | 5fa787c1-1c4d-ed11-bba1-000d3a2caf7f
  versionnumber | 1413873
  createdon | 2022-11-14T16:14:45Z
  cr6c3\_name | Column1 value
  overriddencreatedon | null
  importsequencenumber | null
  \_modifiedonbehalfby\_value | null
  utcconversiontimezonecode | null
  \_createdonbehalfby\_value | null
  \_owningteam\_value | null
  timezoneruleversionnumber | null
  ```

  </TabItem>
</Tabs>
