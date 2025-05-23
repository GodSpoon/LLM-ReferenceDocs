-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# flow run list

Lists runs of the specified Microsoft Flow

## Usage

```sh
m365 flow run list [options]
```

## Options

```md definition-list
`--flowName <flowName>`
: The name of the Microsoft Flow to retrieve the runs for.

`-e, --environmentName <environmentName>`
: The name of the environment to which the flow belongs.

`--status [status]` 
: Filter the results to only flow runs with a given status: `Succeeded`, `Running`, `Failed` or `Cancelled`. By default all flow runs are listed.

`--triggerStartTime [triggerStartTime]`
: Time indicating the inclusive start of a time range of flow runs to return. This should be defined as a valid ISO 8601 string (2021-12-16T18:28:48.6964197Z).

`--triggerEndTime [triggerEndTime]`
: Time indicating the exclusive end of a time range of flow runs to return. This should be defined as a valid ISO 8601 string (2021-12-16T18:28:48.6964197Z).

`--withTrigger`
: If specified, include information about the trigger details for each run.

`--asAdmin`
: Run the command as admin. Use this flag when targeting flows you don't own.
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

If the Microsoft Flow with the name you specified doesn't exist, you will get the `The caller with object id 'abc' does not have permission for connection 'xyz' under Api 'shared_logicflows'.` error.

When using `--withTrigger`, extra requests will get fired for each retrieved flow run. This has an impact on the time the command takes to run.  

## Examples

List runs of the specified Microsoft Flow.

```sh
m365 flow run list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 5923cb07-ce1a-4a5c-ab81-257ce820109a
```

List runs of the specified Microsoft Flow with a specific status

```sh
m365 flow run list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 5923cb07-ce1a-4a5c-ab81-257ce820109a --status Running
```

List runs of the specified Microsoft Flow between a specific time range.

```sh
m365 flow run list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 5923cb07-ce1a-4a5c-ab81-257ce820109a --triggerStartTime 2023-01-21T18:19:00Z --triggerEndTime 2023-01-22T00:00:00Z
```

List runs of the specified Microsoft Flow owned by another user.

```sh
m365 flow run list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 5923cb07-ce1a-4a5c-ab81-257ce820109a --asAdmin
```

List runs of the specified Microsoft Flow with the trigger information.

```sh
m365 flow run list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 5923cb07-ce1a-4a5c-ab81-257ce820109a --withTrigger
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  [      
    {
      "name": "08585329112602833828909892130CU17",
      "id": "/providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/flows/170fb67e-a514-4d84-8727-582022bd13a9/runs/08585329112602833828909892130CU17",
      "type": "Microsoft.ProcessSimple/environments/flows/runs",
      "properties": {
        "startTime": "2022-11-17T14:33:45.2763872Z",
        "status": "Running",
        "correlation": {
          "clientTrackingId": "08585329112602833829909892130CU00"
        },
        "trigger": {
          "name": "When_a_new_response_is_submitted",
          "inputsLink": {
            "uri": "https://prod-08.centralindia.logic.azure.com:443/workflows/f7bf8f6b5c494e63bfc21b54087a596e/runs/08585329112602833828909892130CU17/contents/TriggerInputs?api-version=2016-06-01&se=2022-11-17T18%3A00%3A00.0000000Z&sp=%2Fruns%2F08585329112602833828909892130CU17%2Fcontents%2FTriggerInputs%2Fread&sv=1.0&sig=EXAMPLE_SECRET_VALUE_PLACEHOLDER",
            "contentVersion": "6ZrBBE+MJg7IvhMgyJLMmA==",
            "contentSize": 349,
            "contentHash": {
              "algorithm": "md5",
              "value": "6ZrBBE+MJg7IvhMgyJLMmA=="
            }
          },
          "outputsLink": {
            "uri": "https://prod-08.centralindia.logic.azure.com:443/workflows/f7bf8f6b5c494e63bfc21b54087a596e/runs/08585329112602833828909892130CU17/contents/TriggerOutputs?api-version=2016-06-01&se=2022-11-17T18%3A00%3A00.0000000Z&sp=%2Fruns%2F08585329112602833828909892130CU17%2Fcontents%2FTriggerOutputs%2Fread&sv=1.0&sig=EXAMPLE_SECRET_VALUE_PLACEHOLDER",
            "contentVersion": "Z/4a8tfYygNAR1xpc44iww==",
            "contentSize": 493,
            "contentHash": {
              "algorithm": "md5",
              "value": "Z/4a8tfYygNAR1xpc44iww=="
            }
          },
          "startTime": "2022-11-17T14:33:45.1914506Z",
          "endTime": "2022-11-17T14:33:45.1914506Z",
          "originHistoryName": "08585329112602833829909892130CU00",
          "correlation": {
            "clientTrackingId": "08585329112602833829909892130CU00"
          },
          "status": "Succeeded"
        }
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  name                               startTime                     status
  ---------------------------------  ----------------------------  ---------
  08585329112602833828909892130CU17  2022-11-17T14:33:45.2763872Z  Running
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  name,startTime,status
  08585329112602833828909892130CU17,2022-11-17T14:33:45.2763872Z,Running
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # flow run list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --flowName "08585329112602833828909892130CU17"

  Date: 1/3/2023

  ## 08585329112602833828909892130CU17 (/providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/flows/170fb67e-a514-4d84-8727-582022bd13a9/runs/08585329112602833828909892130CU17)

  Property | Value
  ---------|-------
  name | 08585329112602833828909892130CU17
  id | /providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/flows/170fb67e-a514-4d84-8727-582022bd13a9/runs/08585329112602833828909892130CU17
  type | Microsoft.ProcessSimple/environments/flows/runs
  startTime | 2022-11-17T14:33:45.2763872Z
  status | Running
  ```

  </TabItem>
</Tabs>

### `withTrigger` response

When using the option `withTrigger`, the response for the json-output will differ.

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "name": "08584917134229837167098637545CU67",
      "id": "/providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/flows/a18e89d1-4c75-41e4-9517-e90aedc079be/runs/08584917134229837167098637545CU67",
      "type": "Microsoft.ProcessSimple/environments/flows/runs",
      "properties": {
        "startTime": "2024-03-08T10:24:22.4948083Z",
        "endTime": "2024-03-08T10:24:22.6662784Z",
        "status": "Succeeded",
        "correlation": {
          "clientTrackingId": "08584917134229837167098637545CU67"
        },
        "trigger": {
          "name": "manual",
          "inputsLink": {
            "uri": "https://prod-93.westeurope.logic.azure.com:443/workflows/21b6d99931344cc1bc644e57e415d259/runs/08584917134229837167098637545CU67/contents/TriggerInputs?api-version=2016-06-01&se=2024-03-08T16%3A00%3A00.0000000Z&sp=%2Fruns%2F08584917134229837167098637545CU67%2Fcontents%2FTriggerInputs%2Fread&sv=1.0&sig=EXAMPLE_SECRET_VALUE_PLACEHOLDER",
            "contentVersion": "qp1b8NIh2ZLUxjxKwnkWng==",
            "contentSize": 507,
            "contentHash": {
              "algorithm": "md5",
              "value": "qp1b8NIh2ZLUxjxKwnkWng=="
            }
          },
          "outputsLink": {
            "uri": "https://prod-93.westeurope.logic.azure.com:443/workflows/21b6d99931344cc1bc644e57e415d259/runs/08584917134229837167098637545CU67/contents/TriggerOutputs?api-version=2016-06-01&se=2024-03-08T16%3A00%3A00.0000000Z&sp=%2Fruns%2F08584917134229837167098637545CU67%2Fcontents%2FTriggerOutputs%2Fread&sv=1.0&sig=EXAMPLE_SECRET_VALUE_PLACEHOLDER",
            "contentVersion": "1S3nJ0ffDf82K46CzvjNyQ==",
            "contentSize": 1672,
            "contentHash": {
              "algorithm": "md5",
              "value": "1S3nJ0ffDf82K46CzvjNyQ=="
            }
          },
          "startTime": "2024-03-08T10:24:22.4892073Z",
          "endTime": "2024-03-08T10:24:22.4892073Z",
          "originHistoryName": "08584917134229837167098637545CU67",
          "correlation": {
            "clientTrackingId": "08584917134229837167098637545CU67"
          },
          "status": "Succeeded"
        },
        "isAborted": false
      },
      "triggerInformation": {
        "text": "This is text",
        "boolean": true,
        "number": 10
      }
    }
  ]
  ```

  </TabItem>
</Tabs>
