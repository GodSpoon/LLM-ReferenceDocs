-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# graph directoryextension get

Retrieves the definition of a directory extension

## Usage

```sh
m365 graph directoryextension get [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the directory extension. Specify either `id` or `name`, but not both.

`-n, --name [name]`
: The name of the directory extension. Specify either `id` or `name`, but not both.

`--appId [appId]`
: Application (client) ID of the Entra application where the directory extension is registered. Specify either `appId`, `appObjectId` or `appName`, but not multiple.

`--appObjectId [appObjectId]`
: Object ID of the Entra application where the directory extension is registered. Specify either `appId`, `appObjectId` or `appName`, but not multiple.

`--appName [appName]`
: The name of Entra application where the directory extension is registered. Specify either `appId`, `appObjectId` or `appName`, but not multiple.
```

<Global />

## Examples

Get directory extension by id registered for an application specified by app id.

```sh
m365 graph directoryextension get --id 1f0f15e3-925d-40f0-8fc8-9d3ad135bce0 --appId fd918e4b-c821-4efb-b50a-5eddd23afc6f
```

Get directory extension by name registered for an application specified by name.

```sh
m365 graph directoryextension get --name EXAMPLE_SECRET_VALUE_PLACEHOLDER --appName ContosoApp
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

  Date: 3/2/2025

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
