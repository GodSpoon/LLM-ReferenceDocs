-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# flow environment list

Lists Microsoft Flow environments in the current tenant

## Usage

```sh
m365 flow environment list [options]
```

## Options

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

## Examples

List Microsoft Flow environments in the current tenant.

```sh
m365 flow environment list
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "name": "d87a7535-dd31-4437-bfe1-95340acd55c5",
      "location": "india",
      "type": "Microsoft.ProcessSimple/environments",
      "id": "/providers/Microsoft.ProcessSimple/environments/d87a7535-dd31-4437-bfe1-95340acd55c5",
      "properties": {
        "displayName": "Contoso Environment",
        "createdTime": "2021-07-28T15:36:00.9624176Z",
        "createdBy": {
          "id": "SYSTEM",
          "displayName": "SYSTEM",
          "type": "NotSpecified"
        },
        "provisioningState": "Succeeded",
        "creationType": "Developer",
        "environmentSku": "Developer",
        "environmentType": "NotSpecified",
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
        "isDefault": false,
        "isPayAsYouGoEnabled": false,
        "azureRegionHint": "centralindia",
        "runtimeEndpoints": {
          "microsoft.BusinessAppPlatform": "https://india.api.bap.microsoft.com",
          "microsoft.CommonDataModel": "https://india.api.cds.microsoft.com",
          "microsoft.PowerApps": "https://india.api.powerapps.com",
          "microsoft.PowerAppsAdvisor": "https://india.api.advisor.powerapps.com",
          "microsoft.PowerVirtualAgents": "https://EXAMPLE_SECRET_VALUE_PLACEHOLDER",
          "microsoft.ApiManagement": "https://management.INDIA.azure-apihub.net",
          "microsoft.Flow": "https://india.api.flow.microsoft.com"
        },
        "linkedEnvironmentMetadata": {
          "type": "NotSpecified",
          "resourceId": "03ebcb5d-f16a-45ad-b326-ed1b5df98bc8",
          "friendlyName": "Contoso Environment",
          "uniqueName": "unq03ebcb5df16a45adb326ed1b5df98",
          "domainName": "orgfc80770f",
          "version": "9.2.22105.00154",
          "instanceUrl": "https://orgfc80770f.crm8.dynamics.com/",
          "instanceApiUrl": "https://orgfc80770f.api.crm8.dynamics.com",
          "baseLanguage": 1033,
          "instanceState": "Ready",
          "createdTime": "2021-07-28T15:36:08.093Z"
        },
        "environmentFeatures": {
          "isOpenApiEnabled": false
        },
        "cluster": {
          "category": "Prod",
          "number": "101",
          "uriSuffix": "in-il101.gateway.prod.island",
          "geoShortName": "IN",
          "environment": "Prod"
        },
        "governanceConfiguration": {
          "protectionLevel": "Basic"
        }
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  name                                          displayName
  --------------------------------------------  -------------------------------
  d87a7535-dd31-4437-bfe1-95340acd55c5          Contoso Environment
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  name,location,type,id,displayName
  d87a7535-dd31-4437-bfe1-95340acd55c5,india,Microsoft.ProcessSimple/environments,/providers/Microsoft.ProcessSimple/environments/d87a7535-dd31-4437-bfe1-95340acd55c5,Contoso Environment
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # flow environment list

  Date: 2023-05-18

  ## Contoso Environment (/providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER)

  Property | Value
  ---------|-------
  name | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  location | europe
  type | Microsoft.ProcessSimple/environments
  id | /providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER
  displayName | Contoso Environment
  ```

  </TabItem>
</Tabs>
