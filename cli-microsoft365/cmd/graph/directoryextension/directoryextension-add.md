-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# graph directoryextension add

Creates a new directory extension

## Usage

```sh
m365 graph directoryextension add [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The name of the directory extension.

`--appId [appId]`
: Application (client) ID of the Entra application where the directory extension is registered. Specify either `appId`, `appObjectId` or `appName`, but not multiple.

`--appObjectId [appObjectId]`
: Object ID of the Entra application where the directory extension is registered. Specify either `appId`, `appObjectId` or `appName`, but not multiple.

`--appName [appName]`
: The name of Entra application where the directory extension is registered. Specify either `appId`, `appObjectId` or `appName`, but not multiple.

`--dataType <dataType>`
: The data type of the value the extension property can hold. Possible values are: `Binary`, `Boolean`, `DateTime`, `Integer`, `LargeInteger` and `String`.

`--targetObjects <targetObjects>`
: Comma-separated list of Microsoft Graph resources that can use the extension. Possible values are: `User`, `Group`, `Application`, `AdministrativeUnit`, `Device` and `Organization`.

`--isMultiValued`
: Defines the directory extension as a multi-valued property.
```

<Global />

## Examples

Create a new directory extension of string type defined for user resource.

```sh
m365 graph directoryextension add --name gitHubWorkAccountName --appName ContosoApp --targetObjects User --dataType String
```

Create a new multi-valued directory extension of integer type defined for device and application resource

```sh
m365 graph directoryextension add --name departmentIds --appId 1caf7dcd-7e83-4c3a-94f7-932a1299c844 --targetObjects 'Application,Device' --dataType Integer --isMultiValued
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "522817ae-5c95-4243-96c1-f85231fcbc1f",
    "deletedDateTime": null,
    "appDisplayName": "ContosoApp",
    "dataType": "String",
    "isMultiValued": false,
    "isSyncedFromOnPremises": false,
    "name": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "targetObjects": [
      "User"
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  appDisplayName        : ContosoApp
  dataType              : String
  deletedDateTime       : null
  id                    : 01e77f60-3dde-4fa3-825b-cac8048994a8
  isMultiValued         : false
  isSyncedFromOnPremises: false
  name                  : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  targetObjects         : ["User"]
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,deletedDateTime,appDisplayName,dataType,isMultiValued,isSyncedFromOnPremises,name
  b0937b01-49ce-45c7-a52a-727954f092ea,,ContosoApp,String,,,EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # graph directoryextension add --debug "false" --verbose "false" --name "githubworkaccount" --appName "ContosoApp" --dataType "String" --targetObjects "User"

  Date: 9/8/2024

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER (cec3c38e-3f4a-4ca8-9523-afa47016f51b)

  Property | Value|
  ---------|-------|
  id | cec3c38e-3f4a-4ca8-9523-afa47016f51b
  appDisplayName | ContosoApp
  dataType | String
  isMultiValued | false
  isSyncedFromOnPremises | false
  name | extension\_105be60b603845fea385e58772d9d630\_githubworkaccount
  ```

  </TabItem>
</Tabs>

## More information

- Directory extensions: https://learn.microsoft.com/graph/extensibility-overview#directory-microsoft-entra-id-extensions
