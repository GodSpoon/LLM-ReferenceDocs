-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams team app list

List apps installed in the specified team

## Usage

```sh
m365 teams team app list [options]
```

## Options

```md definition-list
`-i, --teamId [teamId]`
: The id of the Microsoft Teams team. Specify either `teamId` or `teamName` but not both.

`-n, --teamName [teamName]`
: The name of the Microsoft Teams team. Specify either `teamId` or `teamName` but not both.

```

<Global />

## Examples

List applications installed in the specified Microsoft Teams team by id.

```sh
m365 teams team app list --teamId 2eaf7dcd-7e83-4c3a-94f7-932a1299c844
```

List applications installed in the specified Microsoft Teams team by name.

```sh
m365 teams team app list --teamName "Team Name"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
     {
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER=",
      "teamsApp": {
        "id": "14d6962d-6eeb-4f48-8890-de55454bb136",
        "externalId": null,
        "displayName": "Activity",
        "distributionMethod": "store"
      },
      "teamsAppDefinition": {
        "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER==",
        "teamsAppId": "14d6962d-6eeb-4f48-8890-de55454bb136",
        "displayName": "Activity",
        "version": "1.0",
        "publishingState": "published",
        "shortDescription": "Activity app bar entry.",
        "description": "Activity app bar entry.",
        "lastModifiedDateTime": null,
        "createdBy": null
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                                                                                    displayName  distributionMethod
  ----------------------------------------------------------------------------------------------------  -----------  ------------------
  EXAMPLE_SECRET_VALUE_PLACEHOLDER=  Activity     store
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,distributionMethod
  EXAMPLE_SECRET_VALUE_PLACEHOLDER=,Activity,store
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams team app list --teamName "Team Name"

  Date: 1/3/2023

  ## Activity (EXAMPLE_SECRET_VALUE_PLACEHOLDER==)

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER==
  displayName | Activity
  distributionMethod | store
  ```

  </TabItem>
</Tabs>
