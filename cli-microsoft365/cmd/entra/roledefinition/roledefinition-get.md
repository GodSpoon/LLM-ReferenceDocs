-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra roledefinition get

Gets a specific Microsoft Entra ID role definition.

## Usage

```sh
m365 entra roledefinition get [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The id of the role definition. Specify either `id` or `displayName`, but not both.

`-n, --displayName [displayName]`
: The display name of the role definition. Specify either `id` or `displayName`, but not both.

`-p, --properties [properties]`
: Comma-separated list of properties to retrieve.
```

<Global />

## Examples

Get info about a role specified by the id

```sh
m365 entra roledefinition get --id 62e90394-69f5-4237-9190-012177145e10
```

Get limited info about a role specified by the display name

```sh
m365 entra roledefinition get --displayName 'Custom SharePoint Role' --properties 'description,isEnabled'
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "f28a1f50-f6e7-4571-818b-6a12f2af6b6c",
    "description": "Can manage all aspects of the SharePoint service.",
    "displayName": "SharePoint Administrator",
    "isBuiltIn": true,
    "isEnabled": true,
    "resourceScopes": [
      "/"
    ],
    "templateId": "f28a1f50-f6e7-4571-818b-6a12f2af6b6c",
    "version": "1",
    "rolePermissions": [
      {
        "allowedResourceActions": [
          "microsoft.azure.serviceHealth/allEntities/allTasks",
          "microsoft.azure.supportTickets/allEntities/allTasks",
          "microsoft.backup/oneDriveForBusinessProtectionPolicies/allProperties/allTasks",
          "microsoft.backup/oneDriveForBusinessRestoreSessions/allProperties/allTasks",
          "microsoft.backup/restorePoints/sites/allProperties/allTasks",
          "microsoft.backup/restorePoints/userDrives/allProperties/allTasks",
          "microsoft.backup/sharePointProtectionPolicies/allProperties/allTasks",
          "microsoft.backup/sharePointRestoreSessions/allProperties/allTasks",
          "microsoft.backup/siteProtectionUnits/allProperties/allTasks",
          "microsoft.backup/siteRestoreArtifacts/allProperties/allTasks",
          "microsoft.backup/userDriveProtectionUnits/allProperties/allTasks",
          "microsoft.backup/userDriveRestoreArtifacts/allProperties/allTasks",
          "microsoft.directory/groups/hiddenMembers/read",
          "microsoft.directory/groups.unified/basic/update",
          "microsoft.directory/groups.unified/create",
          "microsoft.directory/groups.unified/delete",
          "microsoft.directory/groups.unified/members/update",
          "microsoft.directory/groups.unified/owners/update",
          "microsoft.directory/groups.unified/restore",
          "microsoft.office365.migrations/allEntities/allProperties/allTasks",
          "microsoft.office365.network/performance/allProperties/read",
          "microsoft.office365.serviceHealth/allEntities/allTasks",
          "microsoft.office365.sharePoint/allEntities/allTasks",
          "microsoft.office365.supportTickets/allEntities/allTasks",
          "microsoft.office365.usageReports/allEntities/allProperties/read",
          "microsoft.office365.webPortal/allEntities/standard/read"
        ],
        "condition": null
      }
    ],
    "inheritsPermissionsFrom": [
      {
        "id": "88d8e3e3-8f55-4a1e-953a-9b9898b8876b"
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  description            : Can manage all aspects of the SharePoint service.
  displayName            : SharePoint Administrator
  id                     : f28a1f50-f6e7-4571-818b-6a12f2af6b6c
  inheritsPermissionsFrom: [{"id":"88d8e3e3-8f55-4a1e-953a-9b9898b8876b"}]
  isBuiltIn              : true
  isEnabled              : true
  resourceScopes         : ["/"]
  rolePermissions        : [{"allowedResourceActions":["microsoft.azure.serviceHealth/allEntities/allTasks","microsoft.azure.supportTickets/allEntities/allTasks","microsoft.office365.webPortal/allEntities/standard/read"],"condition":null}]
  templateId             : f28a1f50-f6e7-4571-818b-6a12f2af6b6c
  version                : 1
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,description,displayName,isBuiltIn,isEnabled,templateId,version
  f28a1f50-f6e7-4571-818b-6a12f2af6b6c,Can manage all aspects of the SharePoint service.,SharePoint Administrator,1,1,f28a1f50-f6e7-4571-818b-6a12f2af6b6c,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra roledefinition get --id "f28a1f50-f6e7-4571-818b-6a12f2af6b6c"

  Date: 11/15/2024

  ## SharePoint Administrator (f28a1f50-f6e7-4571-818b-6a12f2af6b6c)

  Property | Value
  ---------|-------
  id | f28a1f50-f6e7-4571-818b-6a12f2af6b6c
  description | Can manage all aspects of the SharePoint service.
  displayName | SharePoint Administrator
  isBuiltIn | true
  isEnabled | true
  templateId | f28a1f50-f6e7-4571-818b-6a12f2af6b6c
  version | 1
  ```

  </TabItem>
</Tabs>
