-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pa app permission list

Lists all permissions of a Power Apps app

## Usage

```sh
m365 pa app permission list [options]
```

## Options

```md definition-list
`--appName <appName>`
: The name (GUID) of the Microsoft Power App.

`--roleName [roleName]`
: Filter the results to only a given role: `Owner`, `CanEdit`, `CanView`.

`--asAdmin`
: Run the command as admin for apps you don't own.

`-e, --environmentName [environmentName]`
: The name of the environment. Required when using `asAdmin`.
```

<Global />

## Remarks

When you specify a value for `roleName`, consider the following:

- `Owner` shows all the owners of the application.
- `CanEdit` shows all the co-owners of the application.
- `CanView` shows all the users with run only permissions.

## Examples

List all permissions for an app you have access to

```sh
m365 pa app permission list --appName bc9f0a7e-53df-46af-b669-5888bb2f63d0
```

List all permissions as admin for an app you don't have access to

```sh
m365 pa app permission list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --appName bc9f0a7e-53df-46af-b669-5888bb2f63d0 --asAdmin
```

List all co-owners for an app you have access to

```sh
m365 pa app permission list --appName bc9f0a7e-53df-46af-b669-5888bb2f63d0 --roleName CanEdit
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "name": "fe36f75e-c103-410b-a18a-2bf6df06ac3a",
      "id": "/providers/Microsoft.PowerApps/apps/37ea6004-f07b-46ca-8ef3-a256b67b4dbb/permissions/fe36f75e-c103-410b-a18a-2bf6df06ac3a",
      "type": "Microsoft.PowerApps/apps/permissions",
      "properties": {
        "roleName": "Owner",
        "principal": {
          "id": "fe36f75e-c103-410b-a18a-2bf6df06ac3a",
          "displayName": "John Doe",
          "email": "john@contoso.com",
          "type": "User",
          "tenantId": "e1dd4023-a656-480a-8a0e-c1b1eec51e1d"
        },
        "scope": "/providers/Microsoft.PowerApps/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/apps/37ea6004-f07b-46ca-8ef3-a256b67b4dbb",
        "notifyShareTargetOption": "NotSpecified",
        "inviteGuestToTenant": false,
        "createdOn": "2022-10-25T21:28:14.2122305Z",
        "createdBy": "f0db9c91-3dae-49c8-98fa-8059b8909d45"
      },
      "roleName": "Owner",
      "principalId": "fe36f75e-c103-410b-a18a-2bf6df06ac3a",
      "principalType": "User"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  roleName  principalId                           principalType
  --------  ------------------------------------  -------------
  Owner     fe36f75e-c103-410b-a18a-2bf6df06ac3a  User
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  name,id,type,roleName,principalId,principalType
  fe36f75e-c103-410b-a18a-2bf6df06ac3a,/providers/Microsoft.PowerApps/apps/37ea6004-f07b-46ca-8ef3-a256b67b4dbb/permissions/fe36f75e-c103-410b-a18a-2bf6df06ac3a,Microsoft.PowerApps/apps/permissions,Owner,fe36f75e-c103-410b-a18a-2bf6df06ac3a,User
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pa app permission list --appName "37ea6004-f07b-46ca-8ef3-a256b67b4dbb"

  Date: 25/06/2023

  ## fe36f75e-c103-410b-a18a-2bf6df06ac3a (/providers/Microsoft.PowerApps/apps/37ea6004-f07b-46ca-8ef3-a256b67b4dbb/permissions/fe36f75e-c103-410b-a18a-2bf6df06ac3a)

  Property | Value
  ---------|-------
  name | fe36f75e-c103-410b-a18a-2bf6df06ac3a
  id | /providers/Microsoft.PowerApps/apps/37ea6004-f07b-46ca-8ef3-a256b67b4dbb/permissions/fe36f75e-c103-410b-a18a-2bf6df06ac3a
  type | Microsoft.PowerApps/apps/permissions
  roleName | Owner
  principalId | fe36f75e-c103-410b-a18a-2bf6df06ac3a
  principalType | User
  ```

  </TabItem>
</Tabs>
