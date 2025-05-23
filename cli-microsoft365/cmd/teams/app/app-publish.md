-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams app publish

Publishes Teams app to the organization's app catalog

## Usage

```sh
m365 teams app publish [options]
```

## Options

```md definition-list
`-p, --filePath <filePath>`
: Absolute or relative path to the Teams manifest zip file to add to the app catalog.
```

<Global />

## Remarks

:::info

To use this command you must be a Global administrator.

:::

## Examples

Add the _teams-manifest.zip_ file to the organization's app catalog

```sh
m365 teams app publish --filePath ./teams-manifest.zip
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
      "id": "e3e29acb-8c79-412b-b746-e6c39ff4cd22",
      "externalId": "b5561ec9-8cab-4aa3-8aa2-d8d7172e4311",
      "displayName": "Test App",
      "distributionMethod": "organization"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  displayName       : Test App
  distributionMethod: organization
  externalId        : b5561ec9-8cab-4aa3-8aa2-d8d7172e4311
  id                : e3e29acb-8c79-412b-b746-e6c39ff4cd22
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,externalId,displayName,distributionMethod
  e3e29acb-8c79-412b-b746-e6c39ff4cd22,b5561ec9-8cab-4aa3-8aa2-d8d7172e4311,Test App,organization
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams app publish

  Date: 4/3/2023

  ## Test App (e3e29acb-8c79-412b-b746-e6c39ff4cd22)

  Property | Value
  ---------|-------
  id | e3e29acb-8c79-412b-b746-e6c39ff4cd22
  externalId | b5561ec9-8cab-4aa3-8aa2-d8d7172e4311
  displayName | Test App
  distributionMethod | organization
  ```

  </TabItem>
</Tabs>
