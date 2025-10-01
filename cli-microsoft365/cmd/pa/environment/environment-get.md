-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pa environment get

Gets information about the specified Power Apps environment

## Usage

```sh
m365 pa environment get [options]
```

## Options

```md definition-list
`-n, --name [name]`
: The name of the environment. When not specified, the default environment is retrieved. Specify either `name` or `default`, but not both.

`--default`
: Indicates that the default environment should be retrieved. Specify either `name` or `default`, but not both.
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

## Examples

Get information about the default Power Apps environment.

```sh
m365 pa environment get --default
```

Get information about the Power Apps environment with the specified name.

```sh
m365 pa environment get --name EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "/providers/Microsoft.PowerApps/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "name": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "location": "europe",
    "type": "Microsoft.PowerApps/environments",
    "properties": {
      "azureRegionHint": "westeurope",
      "displayName": "contoso (default)",
      "createdTime": "2020-03-12T13:39:17.9876946Z",
      "createdBy": {
        "id": "SYSTEM",
        "displayName": "SYSTEM",
        "type": "NotSpecified"
      },
      "provisioningState": "Succeeded",
      "creationType": "DefaultTenant",
      "environmentSku": "Default",
      "isDefault": true,
      "clientUris": {
        "admin": "https://admin.powerplatform.microsoft.com/environments/environment/EXAMPLE_SECRET_VALUE_PLACEHOLDER/hub",
        "maker": "https://make.powerapps.com/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/home"
      },
      "runtimeEndpoints": {
        "microsoft.BusinessAppPlatform": "https://europe.api.bap.microsoft.com",
        "microsoft.CommonDataModel": "https://europe.api.cds.microsoft.com",
        "microsoft.PowerApps": "https://europe.api.powerapps.com",
        "microsoft.PowerAppsAdvisor": "https://europe.api.advisor.powerapps.com",
        "microsoft.PowerVirtualAgents": "https://EXAMPLE_SECRET_VALUE_PLACEHOLDER",
        "microsoft.ApiManagement": "https://management.EUROPE.azure-apihub.net",
        "microsoft.Flow": "https://emea.api.flow.microsoft.com"
      },
      "databaseType": "CommonDataService",
      "linkedEnvironmentMetadata": {
        "resourceId": "5041ef46-5a1c-4a0f-a185-6bb49b5c6686",
        "friendlyName": "contoso (default)",
        "uniqueName": "unq5041ef465a1c4a0fa1856bb49b5c6",
        "domainName": "org6633049a",
        "version": "9.2.22101.00168",
        "instanceUrl": "https://org6633049a.crm4.dynamics.com/",
        "instanceApiUrl": "https://org6633049a.api.crm4.dynamics.com",
        "baseLanguage": 1033,
        "instanceState": "Ready",
        "createdTime": "2021-10-08T09:50:41.283Z",
        "platformSku": "Standard"
      },
      "retentionPeriod": "P7D",
      "lifecycleAuthority": "Environment",
      "states": {
        "management": {
          "id": "NotSpecified"
        },
        "runtime": {
          "runtimeReasonCode": "NotSpecified",
          "requestedBy": {
            "displayName": "SYSTEM",
            "type": "NotSpecified"
          },
          "id": "Enabled"
        }
      },
      "updateCadence": {
        "id": "Frequent"
      },
      "connectedGroups": [],
      "protectionStatus": {
        "keyManagedBy": "Microsoft"
      },
      "trialScenarioType": "None",
      "cluster": {
        "category": "Prod",
        "number": "109",
        "uriSuffix": "eu-il109.gateway.prod.island",
        "geoShortName": "EU",
        "environment": "Prod"
      },
      "governanceConfiguration": {
        "protectionLevel": "Basic"
      }
    },
    "displayName": "contoso (default)",
    "provisioningState": "Succeeded",
    "environmentSku": "Default",
    "azureRegionHint": "westeurope",
    "isDefault": true
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  azureRegionHint  : westeurope
  displayName      : contoso (default)
  environmentSku   : Default
  id               : /providers/Microsoft.PowerApps/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER
  isDefault        : true
  location         : europe
  name             : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  properties       : {"azureRegionHint":"westeurope","clientUris":{"admin":"https://admin.powerplatform.microsoft.com/environments/environment/EXAMPLE_SECRET_VALUE_PLACEHOLDER/hub","maker":"https://make.powerapps.com/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/home"},"cluster":{"category":"Prod","environment":"Prod","geoShortName":"EU","number":"109","uriSuffix":"eu-il109.gateway.prod.island"},"connectedGroups":[],"createdBy":{"displayName":"SYSTEM","id":"SYSTEM","type":"NotSpecified"},"createdTime":"2020-03-12T13:39:17.9876946Z","creationType":"DefaultTenant","databaseType":"CommonDataService","displayName":"contoso (default)","governanceConfiguration":{"protectionLevel":"Basic"},"lifecycleAuthority":"Environment","linkedEnvironmentMetadata":{"baseLanguage":1033,"createdTime":"2021-10-08T09:50:41.283Z","domainName":"org6633049a","friendlyName":"contoso (default)","instanceApiUrl":"https://org6633049a.api.crm4.dynamics.com","instanceState":"Ready","instanceUrl":"https://org6633049a.crm4.dynamics.com/","platformSku":"Standard","resourceId":"5041ef46-5a1c-4a0f-a185-6bb49b5c6686","uniqueName":"unq5041ef465a1c4a0fa1856bb49b5c6","version":"9.2.22101.00168"},"protectionStatus":{"keyManagedBy":"Microsoft"},"provisioningState":"Succeeded","retentionPeriod":"P7D","runtimeEndpoints":{"microsoft.ApiManagement":"https://management.EUROPE.azure-apihub.net","microsoft.BusinessAppPlatform":"https://europe.api.bap.microsoft.com","microsoft.CommonDataModel":"https://europe.api.cds.microsoft.com","microsoft.Flow":"https://emea.api.flow.microsoft.com","microsoft.PowerApps":"https://europe.api.powerapps.com","microsoft.PowerAppsAdvisor":"https://europe.api.advisor.powerapps.com","microsoft.PowerVirtualAgents":"https://EXAMPLE_SECRET_VALUE_PLACEHOLDER"},"states":{"management":{"id":"NotSpecified"},"runtime":{"id":"Enabled","requestedBy":{"displayName":"SYSTEM","type":"NotSpecified"},"runtimeReasonCode":"NotSpecified"}},"trialScenarioType":"None","updateCadence":{"id":"Frequent"}}
  provisioningState: Succeeded
  type             : Microsoft.PowerApps/environments
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  name,id,location,displayName,provisioningState,environmentSku,azureRegionHint,isDefault
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,/providers/Microsoft.PowerApps/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER,europe,environmentName (default),Succeeded,Default,westeurope,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pa environment get --name "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

  Date: 9/1/2023

  ## environmentName (default) (org6633050c) (/providers/Microsoft.PowerApps/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER)

  Property | Value
  ---------|-------
  id | /providers/Microsoft.PowerApps/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER
  name | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  location | europe
  type | Microsoft.PowerApps/environments
  displayName | contoso (default) (org6633049a)
  ```

  </TabItem>
</Tabs>
