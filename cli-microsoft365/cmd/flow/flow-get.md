-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# flow get

Gets information about the specified Power Automate flow

## Usage

```sh
m365 flow get [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The name of the Power Automate flow to get information about

`-e, --environmentName <environmentName>`
: The name of the environment for which to retrieve available flows

`--asAdmin`
: Set, to retrieve the Flow as admin
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

By default, the command will try to retrieve Power Automate flows you own. If you want to retrieve a flow owned by another user, use the `asAdmin` flag.

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

If the Power Automate flow with the name you specified doesn't exist, you will get the `The caller with object id 'abc' does not have permission for connection 'xyz' under Api 'shared_logicflows'.` error. If you try to retrieve a non-existing flow as admin, you will get the `Could not find flow 'xyz'.` error.

## Examples

Get information about the specified Power Automate flow owned by the currently signed-in user

```sh
m365 flow get --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d
```

Get information about the specified Power Automate flow owned by another user

```sh
m365 flow get --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d --asAdmin
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "name": "a18e89d1-4c75-41e4-9517-e90aedc079be",
    "id": "/providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/flows/a18e89d1-4c75-41e4-9517-e90aedc079be",
    "type": "Microsoft.ProcessSimple/environments/flows",
    "properties": {
      "apiId": "/providers/Microsoft.PowerApps/apis/shared_logicflows",
      "displayName": "TEST",
      "userType": "Owner",
      "definition": {
        "$schema": "https://schema.management.azure.com/providers/Microsoft.Logic/schemas/2016-06-01/workflowdefinition.json#",
        "contentVersion": "1.0.0.0",
        "parameters": {
          "$authentication": {
            "defaultValue": {},
            "type": "SecureObject"
          },
          "$connections": {
            "defaultValue": {},
            "type": "Object"
          }
        },
        "triggers": {
          "manual": {
            "metadata": {
              "operationMetadataId": "04077d6a-9fdd-4c79-b742-09a8d5c022eb"
            },
            "type": "Request",
            "kind": "Button",
            "inputs": {
              "schema": {
                "type": "object",
                "properties": {
                  "text": {
                    "description": "Please enter your input",
                    "title": "Text",
                    "type": "string",
                    "x-ms-content-hint": "TEXT",
                    "x-ms-dynamically-added": true
                  },
                  "boolean": {
                    "description": "Please select yes or no",
                    "title": "Boolean",
                    "type": "boolean",
                    "x-ms-content-hint": "BOOLEAN",
                    "x-ms-dynamically-added": true
                  },
                  "number": {
                    "description": "Please enter a number",
                    "title": "Number",
                    "type": "number",
                    "x-ms-content-hint": "NUMBER",
                    "x-ms-dynamically-added": true
                  }
                },
                "required": [
                  "text",
                  "boolean",
                  "number"
                ]
              }
            }
          }
        },
        "actions": {
          "Initialize_variable": {
            "runAfter": {},
            "type": "InitializeVariable",
            "inputs": {
              "variables": [
                {
                  "name": "TEST",
                  "type": "string"
                }
              ]
            }
          }
        }
      },
      "triggerSchema": {
        "type": "object",
        "properties": {
          "text": {
            "description": "Please enter your input",
            "title": "Text",
            "type": "string",
            "x-ms-content-hint": "TEXT",
            "x-ms-dynamically-added": true
          },
          "boolean": {
            "description": "Please select yes or no",
            "title": "Boolean",
            "type": "boolean",
            "x-ms-content-hint": "BOOLEAN",
            "x-ms-dynamically-added": true
          },
          "number": {
            "description": "Please enter a number",
            "title": "Number",
            "type": "number",
            "x-ms-content-hint": "NUMBER",
            "x-ms-dynamically-added": true
          }
        },
        "required": [
          "text",
          "boolean",
          "number"
        ]
      },
      "state": "Started",
      "plan": "NotSpecified",
      "connectionReferences": {},
      "installedConnectionReferences": {
        "shared_approvals": {
          "connectionName": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
          "apiDefinition": {
            "name": "shared_approvals",
            "id": "/providers/Microsoft.PowerApps/apis/shared_approvals",
            "type": "/providers/Microsoft.PowerApps/apis",
            "properties": {
              "displayName": "Approvals",
              "iconUri": "https://connectoricons-prod.azureedge.net/releases/v1.0.1682/1.0.1682.3671/approvals/icon.png",
              "purpose": "NotSpecified",
              "connectionParameters": {},
              "runtimeUrls": [
                "https://europe-002.azure-apim.net/apim/approvals"
              ],
              "primaryRuntimeUrl": "https://europe-002.azure-apim.net/apim/approvals",
              "metadata": {
                "source": "marketplace",
                "brandColor": "#6464F5",
                "connectionLimits": {
                  "*": 1
                },
                "useNewApimVersion": "true",
                "version": {
                  "previous": "releases/v1.0.1679\1.0.1679.3643",
                  "current": "releases/v1.0.1682\1.0.1682.3671"
                }
              },
              "capabilities": [
                "actions"
              ],
              "tier": "Standard",
              "isCustomApi": false,
              "description": "Enables approvals in workflows.",
              "createdTime": "2018-09-16T08:09:23.9434372Z",
              "changedTime": "2024-03-11T18:25:46.7755101Z",
              "publisher": "Microsoft"
            }
          },
          "source": "Invoker",
          "id": "/providers/Microsoft.PowerApps/apis/shared_approvals",
          "displayName": "Approvals",
          "iconUri": "https://connectoricons-prod.azureedge.net/releases/v1.0.1682/1.0.1682.3671/approvals/icon.png",
          "brandColor": "#6464F5",
          "tier": "Standard"
        }
      },
      "createdTime": "2023-07-25T18:42:15.7693633Z",
      "lastModifiedTime": "2024-03-08T10:24:12.0147046Z",
      "flowSuspensionReason": "None",
      "environment": {
        "name": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
        "type": "Microsoft.ProcessSimple/environments",
        "id": "/providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER"
      },
      "definitionSummary": {
        "triggers": [
          {
            "type": "Request",
            "kind": "Button",
            "metadata": {
              "operationMetadataId": "04077d6a-9fdd-4c79-b742-09a8d5c022eb"
            }
          }
        ],
        "actions": [
          {
            "type": "InitializeVariable"
          }
        ]
      },
      "creator": {
        "tenantId": "e1dd4023-a656-480a-8a0e-c1b1eec51e1d",
        "objectId": "fe36f75e-c103-410b-a18a-2bf6df06ac3a",
        "userId": "fe36f75e-c103-410b-a18a-2bf6df06ac3a",
        "userType": "ActiveDirectory"
      },
      "flowTriggerUri": "https://europe-002.azure-apim.net:443/apim/logicflows/EXAMPLE_SECRET_VALUE_PLACEHOLDER/triggers/manual/run?api-version=2016-06-01",
      "installationStatus": "Installed",
      "provisioningMethod": "FromDefinition",
      "flowFailureAlertSubscribed": true,
      "referencedResources": [],
      "licenseData": {
        "performanceProfile": {
          "throttles": {
            "mode": "High"
          }
        },
        "flowLicenseName": "placeholder"
      },
      "isManaged": false,
      "machineDescriptionData": {},
      "flowOpenAiData": {
        "isConsequential": false,
        "isConsequentialFlagOverwritten": false
      }
    },
    "displayName": "TEST",
    "description": "",
    "triggers": "Request-Button",
    "actions": "InitializeVariable"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  actions    : OpenApiConnection-AnalyzeImageV2, Compose, InitializeVariable, OpenApiConnection-HttpRequest, ParseJson, OpenApiConnection-PatchFileItem
  description:
  displayName: My Flow
  id         : /providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/flows/ca76d7b8-3b76-4050-8c03-9fb310ad172f
  name       : ca76d7b8-3b76-4050-8c03-9fb310ad172f
  triggers   : OpenApiConnection
  type       : Microsoft.ProcessSimple/environments/flows
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  name,displayName,description,triggers,actions
  ca76d7b8-3b76-4050-8c03-9fb310ad172f,My Flow,,OpenApiConnection,"OpenApiConnection-AnalyzeImageV2, Compose, InitializeVariable, OpenApiConnection-HttpRequest, ParseJson, OpenApiConnection-PatchFileItem"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # flow get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "ca76d7b8-3b76-4050-8c03-9fb310ad172f"

  Date: 2023-05-18

  ## My Flow (/providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/flows/ca76d7b8-3b76-4050-8c03-9fb310ad172f)

  Property | Value
  ---------|-------
  name | ca76d7b8-3b76-4050-8c03-9fb310ad172f
  id | /providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/flows/ca76d7b8-3b76-4050-8c03-9fb310ad172f
  type | Microsoft.ProcessSimple/environments/flows
  displayName | My Flow
  description | My Flow
  triggers | OpenApiConnection
  actions | OpenApiConnection-AnalyzeImageV2, Compose, InitializeVariable, OpenApiConnection-HttpRequest, ParseJson, OpenApiConnection-PatchFileItem
  ```

  </TabItem>
</Tabs>
