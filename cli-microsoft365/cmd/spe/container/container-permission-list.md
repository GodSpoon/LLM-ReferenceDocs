-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '../../_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spe container permission list

Lists permissions of a SharePoint Embedded Container

## Usage

```sh
m365 spe container permission list [options]
```

## Options

```md definition-list
`-i, --containerId [id]`
: The ID of the SharePoint Embedded Container. Specify either `containerId` or `containerName` but not both.

`-n, --containerName [containerName]`
: Display name of the SharePoint Embedded Container. Specify either `containerId` or `containerName` but not both.

`--containerTypeId [containerTypeId]`
: The container type ID of the container instance. Specify either `containerTypeId` or `containerTypeName` when using `containerName` but not both.

`--containerTypeName [containerTypeName]`
: The container type name of the container instance. Specify either `containerTypeId` or `containerTypeName` when using `containerName` but not both.
```

<Global />

## Permissions

<Tabs>
  <TabItem value="Delegated">

  | Resource        | Permissions                   |
  |-----------------|-------------------------------|
  | Microsoft Graph | FileStorageContainer.Selected |

  </TabItem>
  <TabItem value="Application">

  | Resource        | Permissions                   |
  |-----------------|-------------------------------|
  | Microsoft Graph | FileStorageContainer.Selected |

  </TabItem>
</Tabs>

## Examples

Lists Container permissions by id.

```sh
m365 spe container permission list --containerId "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER"
```

Lists Container permissions by display name.

```sh
m365 spe container permission list --containerName "My Application Storage Container" --containerTypeId "91710488-5756-407f-9046-fbe5f0b4de73"
```

Lists Container permissions by display name and container type name.

```sh
m365 spe container permission list --containerName "My Application Storage Container"  --containerTypeName "My container type name"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "roles": [
        "owner"
      ],
      "grantedToV2": {
        "user": {
          "displayName": "John Doe",
          "email": "john.doe@contoso.onmicrosoft.com",
          "userPrincipalName": "john.doe@contoso.onmicrosoft.com"
        }
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                                                    userPrincipalName                 roles
  --------------------------------------------------------------------  --------------------------------  ------
  EXAMPLE_SECRET_VALUE_PLACEHOLDER  john.doe@contoso.onmicrosoft.com  owner
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,roles,userPrincipalName
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,owner,john.doe@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spe container permission list --containerId "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER"

  Date: 3/3/2025

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  roles | owner
  userPrincipalName | john.doe@contoso.onmicrosoft.com
  ```

  </TabItem>
</Tabs>
