-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra app permission list

Lists the application and delegated permissions for a specified Entra Application Registration

## Usage

```sh
m365 entra app permission list [options]
```

## Options

```md definition-list
`-i, --appId [appId]`
: Client ID of the Entra application registration to retrieve the permissions for. Specify either `appId`, `appName` or `appObjectId`.

`-n, --appName [appName]`
: Display name of the Entra application registration to add the API permissions to. Specify either `appId`, `appName` or `appObjectId`.

`--appObjectId [appObjectId]`
: Object ID of the Entra application registration to retrieve the permissions for. Specify either `appId`, `appName` or `appObjectId`.

`--type [type]`
: The type of permissions to retrieve. Allowed values: `delegated`, `application`, `all`. Defaults to `all`.
```

<Global />

## Remarks

For best performance use the `objectId` option to reference the Entra application registration to get. If you use `appId`, this command will first need to find the corresponding object ID for that application.

## Examples

Retrieves all permissions for an Entra application registration specified by client id.

```sh
m365 entra app permission list --appId 'f1417aa3-bf0b-4cc5-a845-a0b2cf11f690'
```

Retrieves all permissions for an Entra application registration by specified by app display name.

```sh
m365 entra app permission list --appName 'Contoso App'
```

Retrieves all delegated permissions for an Entra application registration specified by object id.

```sh
m365 entra app permission list --appObjectId '64381cda-d40d-4fb0-bce2-bece391546a2' --type delegated
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "resource": "Microsoft Graph",
      "resourceId": "00000003-0000-0000-c000-000000000000",
      "permission": "User.Read",
      "type": "Delegated"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  resource                      resourceId                            permission                         type
  ----------------------------  ------------------------------------  ---------------------------------  -----------
  Microsoft Graph               00000003-0000-0000-c000-000000000000  User.Read                          Delegated
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  resource,resourceId,permission,type
  Microsoft Graph,00000003-0000-0000-c000-000000000000,User.Read,Delegated
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra app permission list --appId "2bf26ae1-9be3-425f-a393-5fe8390e3a36"

  Date: 27/12/2023

  Property | Value
  ---------|-------
  resource | Microsoft Graph
  resourceId | 00000003-0000-0000-c000-000000000000
  permission | User.Read
  type | Delegated
  ```

  </TabItem>
</Tabs>
