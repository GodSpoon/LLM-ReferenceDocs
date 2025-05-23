-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# flow recyclebinitem list

Lists all soft-deleted Power Automate flows within an environment

## Usage

```sh
m365 flow recyclebinitem list [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment.
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reaches general availability.

:::

:::info

To use this command, you must be a Global or Power Platform administrator.

:::

A Power Automate flow is soft-deleted when:
- It's a non-solution flow.
- It's been deleted less than 21 days ago.

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

## Examples

List all soft-deleted flows within a specific environment

```sh
m365 flow recyclebinitem list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "name": "26a9a283-af42-4c09-aa3e-60c3cc166b90",
      "id": "/providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/flows/26a9a283-af42-4c09-aa3e-60c3cc166b90",
      "type": "Microsoft.ProcessSimple/environments/flows",
      "properties": {
        "apiId": "/providers/Microsoft.PowerApps/apis/shared_logicflows",
        "displayName": "Invoicing flow",
        "state": "Deleted",
        "createdTime": "2024-08-05T23:13:54Z",
        "lastModifiedTime": "2024-08-05T23:14:00Z",
        "flowSuspensionReason": "None",
        "environment": {
          "name": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
          "type": "Microsoft.ProcessSimple/environments",
          "id": "/providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER"
        },
        "definitionSummary": {
          "triggers": [],
          "actions": []
        },
        "creator": {
          "tenantId": "a16e76a1-837f-4bf9-82dc-78874d18e434",
          "objectId": "bd51c64d-c262-4184-ba3f-5361ea553820",
          "userId": "bd51c64d-c262-4184-ba3f-5361ea553820",
          "userType": "ActiveDirectory"
        },
        "flowFailureAlertSubscribed": false,
        "isManaged": false,
        "machineDescriptionData": {},
        "flowOpenAiData": {
          "isConsequential": false,
          "isConsequentialFlagOverwritten": false
        }
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  name                                  displayName
  ------------------------------------  --------------
  26a9a283-af42-4c09-aa3e-60c3cc166b90  Invoicing flow
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  name,id,type
  26a9a283-af42-4c09-aa3e-60c3cc166b90,/providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/flows/26a9a283-af42-4c09-aa3e-60c3cc166b90,Microsoft.ProcessSimple/environments/flows
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # flow recyclebinitem list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

  Date: 06/08/2024

  ## 26a9a283-af42-4c09-aa3e-60c3cc166b90 (/providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/flows/26a9a283-af42-4c09-aa3e-60c3cc166b90)

  Property | Value
  ---------|-------
  name | 26a9a283-af42-4c09-aa3e-60c3cc166b90
  id | /providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/flows/26a9a283-af42-4c09-aa3e-60c3cc166b90
  type | Microsoft.ProcessSimple/environments/flows
  ```

  </TabItem>
</Tabs>
