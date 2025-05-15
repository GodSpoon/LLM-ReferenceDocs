-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage community get

Gets information of a Viva Engage community

## Usage

```sh
m365 viva engage community get [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The unique identifier of the community.
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

## Examples

Get a specific community by ID.

```sh
m365 viva engage community get --id EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "displayName": "New Employee Onboarding",
    "description": "New Employee Onboarding",
    "privacy": "public",
    "groupId": "54dda9b2-2df1-4ce8-ae1e-b400956b5b34"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  description: New Employee Onboarding
  displayName: New Employee Onboarding
  groupId    : 54dda9b2-2df1-4ce8-ae1e-b400956b5b34
  id         : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  privacy    : public
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,description,privacy,groupId
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,New Employee Onboarding,New Employee Onboarding,public,54dda9b2-2df1-4ce8-ae1e-b400956b5b34
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # viva engage community get --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

  Date: 14/03/2024

  ## New Employee Onboarding (EXAMPLE_SECRET_VALUE_PLACEHOLDER)

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  displayName | New Employee Onboarding
  description | New Employee Onboarding
  privacy | public
  groupId | 54dda9b2-2df1-4ce8-ae1e-b400956b5b34
  ```

  </TabItem>
</Tabs>
