-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra rolepermission list

Lists all Microsoft Entra ID role permissions

## Usage

```sh
m365 entra rolepermission list [options]
```

## Options

```md definition-list
`-n, --resourceNamespace [resourceNamespace]`
: The namespace of the resource for which to retrieve role permissions.

`-p, --privileged`
: Retrieve only sensitive role permissions.
```

<Global />

## Remarks

:::warning

The command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

Use the `m365 entra resourcenamespace list` command to get a list of available resource namespaces.

## Examples

Get a list of role permissions

```sh
m365 entra rolepermission list --resourceNamespace 'microsoft.directory'
```

Get a list of sensitive role permissions

```sh
m365 entra rolepermission list --resourceNamespace 'microsoft.directory' --privileged
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "actionVerb": null,
      "description": "Create and delete access reviews, and read and update all properties of access reviews in Microsoft Entra ID",
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "isPrivileged": false,
      "name": "microsoft.directory/accessReviews/allProperties/allTasks",
      "resourceScopeId": null
    },
    {
      "actionVerb": "GET",
      "description": "Read all properties of access reviews",
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "isPrivileged": false,
      "name": "microsoft.directory/accessReviews/allProperties/read",
      "resourceScopeId": null
    },
    {
      "actionVerb": null,
      "description": "Manage access reviews of application role assignments in Microsoft Entra ID",
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "isPrivileged": false,
      "name": "microsoft.directory/accessReviews/definitions.applications/allProperties/allTasks",
      "resourceScopeId": null
    },
    {
      "actionVerb": "GET",
      "description": "Read all properties of access reviews of application role assignments in Microsoft Entra ID",
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "isPrivileged": false,
      "name": "microsoft.directory/accessReviews/definitions.applications/allProperties/read",
      "resourceScopeId": null
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                                                                      name                                                                                     actionVerb  isPrivileged
  --------------------------------------------------------------------------------------  ---------------------------------------------------------------------------------------  ----------  ------------
  EXAMPLE_SECRET_VALUE_PLACEHOLDER                                microsoft.directory/accessReviews/allProperties/allTasks                                 null        false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER                                microsoft.directory/accessReviews/allProperties/read                                     GET         false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER       microsoft.directory/accessReviews/definitions.applications/allProperties/allTasks        null        false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER       microsoft.directory/accessReviews/definitions.applications/allProperties/read            GET         false
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  actionVerb,description,id,isPrivileged,name,resourceScopeId
  ,"Create and delete access reviews, and read and update all properties of access reviews in Microsoft Entra ID",EXAMPLE_SECRET_VALUE_PLACEHOLDER,0,microsoft.directory/accessReviews/allProperties/allTasks,
  GET,Read all properties of access reviews,EXAMPLE_SECRET_VALUE_PLACEHOLDER,0,microsoft.directory/accessReviews/allProperties/read,
  ,Manage access reviews of application role assignments in Microsoft Entra ID,EXAMPLE_SECRET_VALUE_PLACEHOLDER,0,microsoft.directory/accessReviews/definitions.applications/allProperties/allTasks,
  GET,Read all properties of access reviews of application role assignments in Microsoft Entra ID,EXAMPLE_SECRET_VALUE_PLACEHOLDER,0,microsoft.directory/accessReviews/definitions.applications/allProperties/read,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra rolepermission list --resourceNamespace "microsoft.directory"

  Date: 1/16/2025

  ## microsoft.directory/accessReviews/allProperties/allTasks (EXAMPLE_SECRET_VALUE_PLACEHOLDER)

  Property | Value
  ---------|-------
  description | Create and delete access reviews, and read and update all properties of access reviews in Microsoft Entra ID
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  isPrivileged | false
  name | microsoft.directory/accessReviews/allProperties/allTasks

  ## microsoft.directory/accessReviews/allProperties/read (EXAMPLE_SECRET_VALUE_PLACEHOLDER)

  Property | Value
  ---------|-------
  actionVerb | GET
  description | Read all properties of access reviews
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  isPrivileged | false
  name | microsoft.directory/accessReviews/allProperties/read

  ## microsoft.directory/accessReviews/definitions.applications/allProperties/allTasks (EXAMPLE_SECRET_VALUE_PLACEHOLDER)

  Property | Value
  ---------|-------
  description | Manage access reviews of application role assignments in Microsoft Entra ID
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  isPrivileged | false
  name | microsoft.directory/accessReviews/definitions.applications/allProperties/allTasks

  ## microsoft.directory/accessReviews/definitions.applications/allProperties/read (EXAMPLE_SECRET_VALUE_PLACEHOLDER)

  Property | Value
  ---------|-------
  actionVerb | GET
  description | Read all properties of access reviews of application role assignments in Microsoft Entra ID
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  isPrivileged | false
  name | microsoft.directory/accessReviews/definitions.applications/allProperties/read
  ```

  </TabItem>
</Tabs>
