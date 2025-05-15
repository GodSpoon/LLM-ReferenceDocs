-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams user app list

List the apps installed in the personal scope of the specified user

## Usage

```sh
m365 teams user app list [options]
```

## Options

```md definition-list
`--userId [userId]`
: The ID of the user to get the apps from. Specify `userId` or `userName` but not both.

`--userName [userName]`
: The UPN of the user to get the apps from. Specify `userId` or `userName` but not both.
```

<Global />

## Examples

List the apps installed in the personal scope of the specified user using its ID.

```sh
m365 teams user app list --userId 4440558e-8c73-4597-abc7-3644a64c4bce
```

List the apps installed in the personal scope of the specified user using its UPN.

```sh
m365 teams user app list --userName admin@contoso.com
```

## Response

<Tabs>
  <TabItem value="JSON">

  ``` json
  [
    {
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER=",
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
      },
      "teamsApp": {
          "id": "14d6962d-6eeb-4f48-8890-de55454bb136",
          "externalId": null,
          "displayName": "Activity",
          "distributionMethod": "store"
      },
      "appId": "14d6962d-6eeb-4f48-8890-de55454bb136"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ``` text
  id                                                                                                        appId                                    displayName                 version
  --------------------------------------------------------------------------------------------------------  ---------------------------------------  --------------------------  -------
  EXAMPLE_SECRET_VALUE_PLACEHOLDER=      14d6962d-6eeb-4f48-8890-de55454bb136     Activity                    1.0
  ```

  </TabItem>
  <TabItem value="CSV">

  ``` text
  id,appId,displayName,version
  EXAMPLE_SECRET_VALUE_PLACEHOLDER=,14d6962d-6eeb-4f48-8890-de55454bb136,Activity,1.0
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams user app list --userName "admin@contoso.com"

  Date: 1/3/2023

  ## Activity (EXAMPLE_SECRET_VALUE_PLACEHOLDER=)

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  appId | 14d6962d-6eeb-4f48-8890-de55454bb136
  displayName | Activity
  version | 1.0
  ```

  </TabItem>
</Tabs>
