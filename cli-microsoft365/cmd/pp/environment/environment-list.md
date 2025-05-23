-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp environment list

Lists Microsoft Power Platform environments

## Usage

```sh
m365 pp environment list [options]
```

## Options

```md definition-list
`--asAdmin`
: Run the command as admin and retrieve all environments. Lists only environments you have explicitly are assigned permissions to by default.
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.
Register CLI for Microsoft 365 or Microsoft Entra application as a management application for the Power Platform using m365 pp managementapp add [options]

:::

## Examples

List Microsoft Power Platform environments.

```sh
m365 pp environment list
```

List all Microsoft Power Platform environments.

```sh
m365 pp environment list --asAdmin
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id":"/providers/Microsoft.BusinessAppPlatform/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "type":"Microsoft.BusinessAppPlatform/environments",
      "location":"europe",
      "name":"EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "properties":{
        "tenantId":"e1dd4023-a656-480a-8a0e-c1b1eec51e1d",
        "azureRegion":"northeurope",
        "displayName":"contoso (default)",
        "createdTime":"2020-03-12T13:39:17.9876946Z",
        "createdBy":{
          "id":"SYSTEM",
          "displayName":"SYSTEM",
          "type":"NotSpecified"
        },
        "provisioningState":"Succeeded",
        "creationType":"DefaultTenant",
        "environmentSku":"Default",
        "isDefault":true,
        "clientUris":{
          "admin":"https://admin.powerplatform.microsoft.com/environments/environment/EXAMPLE_SECRET_VALUE_PLACEHOLDER/hub",
          "maker":"https://make.powerapps.com/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/home"
        },
        "runtimeEndpoints":{
          "microsoft.BusinessAppPlatform":"https://europe.api.bap.microsoft.com",
          "microsoft.CommonDataModel":"https://europe.api.cds.microsoft.com",
          "microsoft.PowerApps":"https://europe.api.powerapps.com",
          "microsoft.PowerAppsAdvisor":"https://europe.api.advisor.powerapps.com",
          "microsoft.PowerVirtualAgents":"https://EXAMPLE_SECRET_VALUE_PLACEHOLDER",
          "microsoft.ApiManagement":"https://management.EUROPE.azure-apihub.net",
          "microsoft.Flow":"https://emea.api.flow.microsoft.com"
        },
        "databaseType":"CommonDataService",
        "linkedEnvironmentMetadata":{
          "resourceId":"5041ef46-5a1c-4a0f-a185-6bb49b5c6686",
          "friendlyName":"contoso (default)",
          "uniqueName":"unq5041ef465a1c4a0fa1856bb49b5c6",
          "domainName":"org6633049a",
          "version":"9.2.22101.00168",
          "instanceUrl":"https://org6633049a.crm4.dynamics.com/",
          "instanceApiUrl":"https://org6633049a.api.crm4.dynamics.com",
          "baseLanguage":1033,
          "instanceState":"Ready",
          "createdTime":"2021-10-08T09:50:41.283Z",
          "backgroundOperationsState":"Enabled",
          "scaleGroup":"EURCRMLIVESG644",
          "platformSku":"Standard"
        },
        "trialScenarioType":"None",
        "retentionPeriod":"P7D",
        "states":{
          "management":{
            "id":"NotSpecified"
          },
          "runtime":{
            "runtimeReasonCode":"NotSpecified",
            "requestedBy":{
              "displayName":"SYSTEM",
              "type":"NotSpecified"
            },
            "id":"Enabled"
          }
        },
        "updateCadence":{
          "id":"Frequent"
        },
        "retentionDetails":{
          "retentionPeriod":"P7D",
          "backupsAvailableFromDateTime":"2022-10-23T23:27:16.8059564Z"
        },
        "protectionStatus":{
          "keyManagedBy":"Microsoft"
        },
        "cluster":{
          "category":"Prod",
          "number":"109",
          "uriSuffix":"eu-il109.gateway.prod.island",
          "geoShortName":"EU",
          "environment":"Prod"
        },
        "connectedGroups":[
          
        ],
        "lifecycleOperationsEnforcement":{
          "allowedOperations":[
            {
              "type":{
                "id":"Backup"
              }
            },
            {
              "type":{
                "id":"Edit"
              }
            },
            {
              "type":{
                "id":"Enable"
              }
            },
            {
              "type":{
                "id":"Disable"
              }
            },
            {
              "type":{
                "id":"EnableGovernanceConfiguration"
              }
            }
          ],
          "disallowedOperations":[
            {
              "type":{
                "id":"Provision"
              },
              "reason":{
                "message":"Provision cannot be performed because there is no linked CDS instance or the CDS instance version is not supported."
              }
            },
            {
              "type":{
                "id":"Unlock"
              },
              "reason":{
                "message":"Unlock cannot be performed because there is no linked CDS instance or the CDS instance version is not supported."
              }
            },
            {
              "type":{
                "id":"Convert"
              },
              "reason":{
                "message":"Convert cannot be performed on environment of type Default."
              }
            },
            {
              "type":{
                "id":"Copy"
              },
              "reason":{
                "message":"Copy cannot be performed on environment of type Default."
              }
            },
            {
              "type":{
                "id":"Delete"
              },
              "reason":{
                "message":"Delete cannot be performed on environment of type Default."
              }
            },
            {
              "type":{
                "id":"Promote"
              },
              "reason":{
                "message":"Promote cannot be performed on environment of type Default."
              }
            },
            {
              "type":{
                "id":"Recover"
              },
              "reason":{
                "message":"Recover cannot be performed on environment of type Default."
              }
            },
            {
              "type":{
                "id":"Reset"
              },
              "reason":{
                "message":"Reset cannot be performed on environment of type Default."
              }
            },
            {
              "type":{
                "id":"Restore"
              },
              "reason":{
                "message":"Restore cannot be performed on environment of type Default."
              }
            },
            {
              "type":{
                "id":"UpdateProtectionStatus"
              },
              "reason":{
                "message":"UpdateProtectionStatus cannot be performed on environment of type Default."
              }
            },
            {
              "type":{
                "id":"NewCustomerManagedKey"
              },
              "reason":{
                "message":"NewCustomerManagedKey cannot be performed on environment of type Default."
              }
            },
            {
              "type":{
                "id":"RotateCustomerManagedKey"
              },
              "reason":{
                "message":"RotateCustomerManagedKey cannot be performed on environment of type Default."
              }
            },
            {
              "type":{
                "id":"RevertToMicrosoftKey"
              },
              "reason":{
                "message":"RevertToMicrosoftKey cannot be performed on environment of type Default."
              }
            },
            {
              "type":{
                "id":"NewNetworkInjection"
              },
              "reason":{
                "message":"NewNetworkInjection cannot be performed on environment of type Default."
              }
            },
            {
              "type":{
                "id":"SwapNetworkInjection"
              },
              "reason":{
                "message":"SwapNetworkInjection cannot be performed on environment of type Default."
              }
            },
            {
              "type":{
                "id":"RevertNetworkInjection"
              },
              "reason":{
                "message":"RevertNetworkInjection cannot be performed on environment of type Default."
              }
            },
            {
              "type":{
                "id":"NewIdentity"
              },
              "reason":{
                "message":"NewIdentity cannot be performed on environment of type Default."
              }
            },
            {
              "type":{
                "id":"SwapIdentity"
              },
              "reason":{
                "message":"SwapIdentity cannot be performed on environment of type Default."
              }
            },
            {
              "type":{
                "id":"RevertIdentity"
              },
              "reason":{
                "message":"RevertIdentity cannot be performed on environment of type Default."
              }
            },
            {
              "type":{
                "id":"DisableGovernanceConfiguration"
              },
              "reason":{
                "message":"DisableGovernanceConfiguration cannot be performed on Power Platform environment because of the governance configuration."
              }
            },
            {
              "type":{
                "id":"UpdateGovernanceConfiguration"
              },
              "reason":{
                "message":"UpdateGovernanceConfiguration cannot be performed on Power Platform environment because of the governance configuration."
              }
            }
          ]
        },
        "governanceConfiguration":{
          "protectionLevel":"Basic"
        }
      },
      "displayName":"contoso (default)"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  displayName                             name
  --------------------------------------- --------------------------------------------
  environmentName (default) (org6633050c) EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  name,displayName
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,contoso (default)
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pp environment list

  Date: 9/1/2023

  ## environmentName (default) (/providers/Microsoft.BusinessAppPlatform/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER)

  Property | Value
  ---------|-------
  id | /providers/Microsoft.BusinessAppPlatform/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER
  type | Microsoft.BusinessAppPlatform/environments
  location | europe
  name | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  displayName | contoso (default)
  ```

  </TabItem>
</Tabs>
