-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# graph directoryextension list

Retrieves a list of directory extensions

## Usage

```sh
m365 graph directoryextension list [options]
```

## Options

```md definition-list
`--appId [appId]`
: Application (client) ID of the Entra application where the directory extensions are registered. Specify either `appId`, `appObjectId` or `appName`, but not multiple.

`--appObjectId [appObjectId]`
: Object ID of the Entra application where the directory extensions are registered. Specify either `appId`, `appObjectId` or `appName`, but not multiple.

`--appName [appName]`
: The name of Entra application where the directory extensions are registered. Specify either `appId`, `appObjectId` or `appName`, but not multiple.
```

<Global />

## Remarks

When neither `appId`, `appObjectId` nor `appName` is specified, the command will return all available directory extensions including those registered for multi-tenant apps.

https://learn.microsoft.com/en-us/graph/api/EXAMPLE_SECRET_VALUE_PLACEHOLDER?view=graph-rest-1.0&tabs=http

Otherwise, it will return directory extensions for a specific application.

https://learn.microsoft.com/en-us/graph/api/application-list-extensionproperty?view=graph-rest-1.0&tabs=http

## Examples

Get all available directory extensions including those registered for multi-tenant apps

```sh
m365 graph directoryextension list
```

Get all directory extensions registered for an application specified by app id.

```sh
m365 graph directoryextension list --appId fd918e4b-c821-4efb-b50a-5eddd23afc6f
```

Get all directory extensions registered for an application specified by app object id.

```sh
m365 graph directoryextension list --appObjectId 1caf7dcd-7e83-4c3a-94f7-932a1299c844
```

Get all directory extensions registered for an application specified by name.

```sh
m365 graph directoryextension list --appName ContosoApp
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "8133c498-ad76-4a7b-90a0-675bf5adf492",
      "deletedDateTime": null,
      "appDisplayName": "ContosoApp",
      "dataType": "String",
      "isMultiValued": true,
      "isSyncedFromOnPremises": false,
      "name": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "targetObjects": [
        "User"
      ]
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  appDisplayName        : ContosoApp
  dataType              : String
  deletedDateTime       : null
  id                    : 8133c498-ad76-4a7b-90a0-675bf5adf492
  isMultiValued         : true
  isSyncedFromOnPremises: false
  name                  : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  targetObjects         : ["User"]
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,deletedDateTime,appDisplayName,dataType,isMultiValued,isSyncedFromOnPremises,name
  8133c498-ad76-4a7b-90a0-675bf5adf492,,ContosoApp,String,1,0,EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # graph directoryextension list --debug "false" --verbose "false" --appId "66eac1c5-0538-4aec-9e02-4b9e60f5e4b9"

  Date: 3/23/2025

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER (8133c498-ad76-4a7b-90a0-675bf5adf492)

  Property | Value
  ---------|-------
  id | 8133c498-ad76-4a7b-90a0-675bf5adf492
  appDisplayName | ContosoApp
  dataType | String
  isMultiValued | true
  isSyncedFromOnPremises | false
  name | extension\_66eac1c505384aec9e024b9e60f5e4b9\_jobGroup
  ```

  </TabItem>
</Tabs>

## More information

- Directory extensions: https://learn.microsoft.com/graph/extensibility-overview#directory-microsoft-entra-id-extensions
