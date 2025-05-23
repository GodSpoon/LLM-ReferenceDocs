-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp copilot get

Get information about the specified copilot

## Usage

```sh
m365 pp copilot get [options]
```

## Alias

```sh
m365 pp chatbot get [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment.

`-i, --id [id]`
: The id of the copilot. Specify either `id` or `name` but not both.

`-n, --name [name]`
: The name of the copilot. Specify either `id` or `name` but not both.

`--asAdmin`
: Run the command as admin for environments you do not have explicitly assigned permissions to.
```

<Global />

## Examples

Get a specific copilot in a specific environment based on name.

```sh
m365 pp copilot get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "CLI 365 Copilot"
```

Get a specific copilot in a specific environment based on name as admin.

```sh
m365 pp copilot get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "CLI 365 Copilot" --asAdmin
```

Get a specific copilot in a specific environment based on id.

```sh
m365 pp copilot get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --id "3a081d91-5ea8-40a7-8ac9-abbaa3fcb893"
```

Get a specific copilot in a specific environment based on id as admin.

```sh
m365 pp copilot get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --id "3a081d91-5ea8-40a7-8ac9-abbaa3fcb893" --asAdmin
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "authenticationtrigger": 0,
    "_owningbusinessunit_value": "6da087c1-1c4d-ed11-bba1-000d3a2caf7f",
    "statuscode": 1,
    "createdon": "2022-11-19T10:42:22Z",
    "statecode": 0,
    "schemaname": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "_ownerid_value": "5fa787c1-1c4d-ed11-bba1-000d3a2caf7f",
    "overwritetime": "1900-01-01T00:00:00Z",
    "name": "CLI 365 Copilot",
    "solutionid": "fd140aae-4df4-11dd-bd17-0019b9312238",
    "ismanaged": false,
    "versionnumber": 1421457,
    "language": 1033,
    "_modifiedby_value": "5f91d7a7-5f46-494a-80fa-5c18b0221351",
    "_modifiedonbehalfby_value": "5fa787c1-1c4d-ed11-bba1-000d3a2caf7f",
    "modifiedon": "2022-11-19T10:42:24Z",
    "componentstate": 0,
    "botid": "3a081d91-5ea8-40a7-8ac9-abbaa3fcb893",
    "_createdby_value": "5fa787c1-1c4d-ed11-bba1-000d3a2caf7f",
    "componentidunique": "cdcd6496-e25d-4ad1-91cf-3f4d547fdd23",
    "authenticationmode": 1,
    "_owninguser_value": "5fa787c1-1c4d-ed11-bba1-000d3a2caf7f",
    "accesscontrolpolicy": 0,
    "runtimeprovider": 0,
    "_publishedby_value": "John Doe",
    "authenticationconfiguration": null,
    "authorizedsecuritygroupids": null,
    "overriddencreatedon": null,
    "applicationmanifestinformation": null,
    "importsequencenumber": null,
    "synchronizationstatus": null,
    "template": null,
    "_providerconnectionreferenceid_value": null,
    "configuration": null,
    "utcconversiontimezonecode": null,
    "publishedon": "2022-11-19T10:43:24Z",
    "_createdonbehalfby_value": null,
    "iconbase64": null,
    "supportedlanguages": null,
    "_owningteam_value": null,
    "timezoneruleversionnumber": null,
    "iscustomizable": {
      "Value": true,
      "CanBeChanged": true,
      "ManagedPropertyLogicalName": "iscustomizableanddeletable"
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  accesscontrolpolicy           : 0
  applicationmanifestinformation: null
  authenticationconfiguration   : null
  authenticationmode            : 1
  authenticationtrigger         : 0
  authorizedsecuritygroupids    : null
  botid                         : 3a081d91-5ea8-40a7-8ac9-abbaa3fcb893
  componentidunique             : cdcd6496-e25d-4ad1-91cf-3f4d547fdd23
  componentstate                : 0
  configuration                 : null
  createdon                     : 2022-11-19T10:42:22Z
  iconbase64                    : null
  importsequencenumber          : null
  ismanaged                     : false
  iscustomizable                : {"Value":true,"CanBeChanged":true,"ManagedPropertyLogicalName":"iscustomizableanddeletable"}
  language                      : 1033
  modifiedon                    : 2022-11-19T10:42:24Z
  name                          : CLI 365 Copilot
  overriddencreatedon           : null
  overwritetime                 : 1900-01-01T00:00:00Z
  publishedon                   : 2022-11-19T10:43:24Z
  runtimeprovider               : 0
  schemaname                    : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  solutionid                    : fd140aae-4df4-11dd-bd17-0019b9312238
  statecode                     : 0
  statuscode                    : 1
  supportedlanguages            : null
  synchronizationstatus         : null
  template                      : null
  timezoneruleversionnumber     : null
  utcconversiontimezonecode     : null
  versionnumber                 : 1421457
  _createdby_value              : 5fa787c1-1c4d-ed11-bba1-000d3a2caf7f
  _createdonbehalfby_value      : null
  _modifiedby_value             : 5f91d7a7-5f46-494a-80fa-5c18b0221351
  _modifiedonbehalfby_value     : 5fa787c1-1c4d-ed11-bba1-000d3a2caf7f
  _ownerid_value                : 5fa787c1-1c4d-ed11-bba1-000d3a2caf7f
  _owningbusinessunit_value     : 6da087c1-1c4d-ed11-bba1-000d3a2caf7f
  _owningteam_value             : null
  _owninguser_value             : 5fa787c1-1c4d-ed11-bba1-000d3a2caf7f
  _publishedby_value            : John Doe
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  name,botid,publishedon,createdon,modifiedon
  CLI 365 Copilot,3a081d91-5ea8-40a7-8ac9-abbaa3fcb893,2022-11-19T10:43:24Z,2022-11-19T10:42:22Z,2022-11-19T10:42:24Z
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pp copilot get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --id "3a081d91-5ea8-40a7-8ac9-abbaa3fcb893"

  Date: 9/1/2023

  ## CLI 365 Copilot

  Property | Value
  ---------|-------
  authenticationtrigger | 0
  \_owningbusinessunit\_value | 6da087c1-1c4d-ed11-bba1-000d3a2caf7f
  statuscode | 1
  createdon | 2022-11-19T10:42:22Z
  statecode | 0
  schemaname | new\_bot\_23f5f58697fd43d595eb451c9797a53d
  \_ownerid\_value | 5fa787c1-1c4d-ed11-bba1-000d3a2caf7f
  overwritetime | 1900-01-01T00:00:00Z
  name | CLI 365 Copilot
  solutionid | fd140aae-4df4-11dd-bd17-0019b9312238
  ismanaged | false
  versionnumber | 1445843
  language | 1033
  \_modifiedby\_value | 5f91d7a7-5f46-494a-80fa-5c18b0221351
  \_modifiedonbehalfby\_value | 5fa787c1-1c4d-ed11-bba1-000d3a2caf7f
  modifiedon | 2022-11-19T10:42:24Z
  componentstate | 0
  botid | 3a081d91-5ea8-40a7-8ac9-abbaa3fcb893
  \_createdby\_value | 5fa787c1-1c4d-ed11-bba1-000d3a2caf7f
  componentidunique | cdcd6496-e25d-4ad1-91cf-3f4d547fdd23
  authenticationmode | 1
  \_owninguser\_value | 5fa787c1-1c4d-ed11-bba1-000d3a2caf7f
  accesscontrolpolicy | 0
  runtimeprovider | 0
  \_publishedby\_value | null
  authenticationconfiguration | null
  authorizedsecuritygroupids | null
  overriddencreatedon | null
  applicationmanifestinformation | null
  importsequencenumber | null
  synchronizationstatus | null
  template | null
  \_providerconnectionreferenceid\_value | null
  configuration | null
  utcconversiontimezonecode | null
  publishedon | null
  \_createdonbehalfby\_value | null
  iconbase64 | null
  supportedlanguages | null
  \_owningteam\_value | null
  timezoneruleversionnumber | null
  ```

  </TabItem>
</Tabs>
