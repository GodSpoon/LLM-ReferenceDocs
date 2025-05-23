-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra roledefinition add

Creates a custom Microsoft Entra ID role definition

## Usage

```sh
m365 entra roledefinition add [options]
```

## Options

```md definition-list
`-n, --displayName <displayName>`
: The display name for the role definition.

`-a, --allowedResourceActions <allowedResourceActions>`	
: Comma-separated list of resource actions allowed for the role.

`-d, --description [description]`
: The description for the role definition.

`-e, --enabled [enabled]`
: Indicates if the role is enabled for the assignment. If not specified, the role is enabled by default.

`-v, --version [version]`
: The version of the role definition.
```

<Global />

## Remarks

Use the `m365 entra rolepermission list --resourceNamespace microsoft.directory` command to get a list of available resource actions.

## Examples

Create a custom Microsoft Entra ID role

```sh
m365 entra roledefinition add --displayName 'Application Remover' --description 'Allows to remove any Entra ID application' --allowedResourceActions 'microsoft.directory/applications/delete'
```

Create a custom Microsoft Entra ID role, but disable it for the assignment

```sh
m365 entra roledefinition add --displayName 'Application Remover' --version '1.0' --enabled false --allowedResourceActions 'microsoft.directory/applications/delete,microsoft.directory/applications/owners/update'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "3844129d-f748-4c03-8165-4412ee9b4ceb",
    "description": null,
    "displayName": "Custom Role",
    "isBuiltIn": false,
    "isEnabled": true,
    "resourceScopes": [
      "/"
    ],
    "templateId": "3844129d-f748-4c03-8165-4412ee9b4ceb",
    "version": "1",
    "rolePermissions": [
      {
        "allowedResourceActions": [
          "microsoft.directory/groups.unified/create",
          "microsoft.directory/groups.unified/delete"
        ],
        "condition": null
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  description    : null
  displayName    : Custom Role
  id             : 3844129d-f748-4c03-8165-4412ee9b4ceb
  isBuiltIn      : false
  isEnabled      : true
  resourceScopes : ["/"]
  rolePermissions: [{"allowedResourceActions":["microsoft.directory/groups.unified/create","microsoft.directory/groups.unified/delete"],"condition":null}]
  templateId     : 3844129d-f748-4c03-8165-4412ee9b4ceb
  version        : 1
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,description,displayName,isBuiltIn,isEnabled,templateId,version
  3844129d-f748-4c03-8165-4412ee9b4ceb,,Custom Role,0,1,3844129d-f748-4c03-8165-4412ee9b4ceb,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra roledefinition add --displayName "Custom Role" --allowedResourceActions "microsoft.directory/groups.unified/create,microsoft.directory/groups.unified/delete" --version 1

  Date: 12/15/2024

  ## Custom Role (3844129d-f748-4c03-8165-4412ee9b4ceb)

  Property | Value
  ---------|-------
  id | 3844129d-f748-4c03-8165-4412ee9b4ceb
  displayName | Custom Role
  isBuiltIn | false
  isEnabled | true
  templateId | 3844129d-f748-4c03-8165-4412ee9b4ceb
  version | 1
  ```

  </TabItem>
</Tabs>

## More information

- https://learn.microsoft.com/graph/api/rbacapplication-post-roledefinitions
