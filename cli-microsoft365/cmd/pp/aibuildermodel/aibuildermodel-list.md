-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp aibuildermodel list

List available AI builder models in the specified Power Platform environment

## Usage

```sh
m365 pp aibuildermodel list [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment.

`--asAdmin`
: Run the command as admin for environments you do not have explicitly assigned permissions to.
```

<Global />

## Examples

List all AI Builder models in a specific environment.

```sh
m365 pp aibuildermodel list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"
```

List all AI Builder models in a specific environment as admin.

```sh
m365 pp aibuildermodel list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --asAdmin
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "statecode": 0,
      "_msdyn_templateid_value": "10707e4e-1d56-e911-8194-000d3a6cd5a5",
      "msdyn_modelcreationcontext": "{}",
      "createdon": "2022-11-29T11:58:45Z",
      "_ownerid_value": "5fa787c1-1c4d-ed11-bba1-000d3a2caf7f",
      "modifiedon": "2022-11-29T11:58:45Z",
      "msdyn_sharewithorganizationoncreate": false,
      "msdyn_aimodelidunique": "b0328b67-47e2-4202-8189-e617ec9a88bd",
      "solutionid": "fd140aae-4df4-11dd-bd17-0019b9312238",
      "ismanaged": false,
      "versionnumber": 1458121,
      "msdyn_name": "Document Processing 11/29/2022, 12:58:43 PM",
      "introducedversion": "1.0",
      "statuscode": 0,
      "_modifiedby_value": "5fa787c1-1c4d-ed11-bba1-000d3a2caf7f",
      "overwritetime": "1900-01-01T00:00:00Z",
      "componentstate": 0,
      "_createdby_value": "5fa787c1-1c4d-ed11-bba1-000d3a2caf7f",
      "_owningbusinessunit_value": "6da087c1-1c4d-ed11-bba1-000d3a2caf7f",
      "_owninguser_value": "5fa787c1-1c4d-ed11-bba1-000d3a2caf7f",
      "msdyn_aimodelid": "08ffffbe-ec1c-4e64-b64b-dd1db926c613",
      "_msdyn_activerunconfigurationid_value": null,
      "overriddencreatedon": null,
      "_msdyn_retrainworkflowid_value": null,
      "importsequencenumber": null,
      "EXAMPLE_SECRET_VALUE_PLACEHOLDER": null,
      "_modifiedonbehalfby_value": null,
      "utcconversiontimezonecode": null,
      "_createdonbehalfby_value": null,
      "_owningteam_value": null,
      "timezoneruleversionnumber": null,
      "iscustomizable": {
        "Value": true,
        "CanBeChanged": true,
        "ManagedPropertyLogicalName": "iscustomizableanddeletable"
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  createdon             modifiedon            msdyn_aimodelid                       msdyn_name
  --------------------  --------------------  ------------------------------------  -------------------------------------------
  2022-10-25T14:44:48Z  2022-10-25T14:44:48Z  08ffffbe-ec1c-4e64-b64b-dd1db926c613  Document Processing 11/29/2022, 12:58:43 PM
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  msdyn_name,msdyn_aimodelid,createdon,modifiedon
  "Document Processing 11/29/2022, 12:58:43 PM",08ffffbe-ec1c-4e64-b64b-dd1db926c613,2022-11-29T11:58:45Z,2022-11-29T11:58:45Z
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pp aibuildermodel list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

  Date: 9/1/2023

  Property | Value
  ---------|-------
  statecode | 0
  \_msdyn\_templateid\_value | 10707e4e-1d56-e911-8194-000d3a6cd5a5
  createdon | 2022-11-29T11:58:45Z
  \_ownerid\_value | 5fa787c1-1c4d-ed11-bba1-000d3a2caf7f
  modifiedon | 2022-11-29T11:58:45Z
  msdyn\_sharewithorganizationoncreate | false
  msdyn\_aimodelidunique | b0328b67-47e2-4202-8189-e617ec9a88bd
  solutionid | fd140aae-4df4-11dd-bd17-0019b9312238
  ismanaged | false
  versionnumber | 1458121
  msdyn\_name | Document Processing 11/29/2022, 12:58:43 PM
  introducedversion | 1.0
  statuscode | 0
  \_modifiedby\_value | 5fa787c1-1c4d-ed11-bba1-000d3a2caf7f
  overwritetime | 1900-01-01T00:00:00Z
  componentstate | 0
  \_createdby\_value | 5fa787c1-1c4d-ed11-bba1-000d3a2caf7f
  \_owningbusinessunit\_value | 6da087c1-1c4d-ed11-bba1-000d3a2caf7f
  \_owninguser\_value | 5fa787c1-1c4d-ed11-bba1-000d3a2caf7f
  msdyn\_aimodelid | 08ffffbe-ec1c-4e64-b64b-dd1db926c613
  \_msdyn\_activerunconfigurationid\_value | null
  overriddencreatedon | null
  \_msdyn\_retrainworkflowid\_value | null
  importsequencenumber | null
  \_msdyn\_scheduleinferenceworkflowid\_value | null
  \_modifiedonbehalfby\_value | null
  utcconversiontimezonecode | null
  \_createdonbehalfby\_value | null
  \_owningteam\_value | null
  timezoneruleversionnumber | null
  ```

  </TabItem>
</Tabs>
