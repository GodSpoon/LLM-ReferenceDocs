-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra app role list

Gets Entra app registration roles

## Usage

```sh
m365 entra app role list [options]
```

## Alias

```sh
m365 entra appregistration role list [options]
```

## Options

```md definition-list
`--appId [appId]`
: Application (client) ID of the Entra application registration for which to retrieve roles. Specify either `appId`, `appObjectId` or `appName`

`--appObjectId [appObjectId]`
: Object ID of the Entra application registration for which to retrieve roles. Specify either `appId`, `appObjectId` or `appName`

`--appName [appName]`
: Name of the Entra application registration for which to retrieve roles. Specify either `appId`, `appObjectId` or `appName`
```

<Global />

## Remarks

For best performance use the `appObjectId` option to reference the Entra application registration for which to retrieve roles. If you use `appId` or `appName`, this command will first need to find the corresponding object ID for that application.

If the command finds multiple Entra application registrations with the specified app name, it will prompt you to disambiguate which app it should use, listing the discovered object IDs.

## Examples

Get roles for the Entra application registration specified by its object ID

```sh
m365 entra app role list --appObjectId d75be2e1-0204-4f95-857d-51a37cf40be8
```

Get roles for the Entra application registration specified by its app (client) ID

```sh
m365 entra app role list --appId e75be2e1-0204-4f95-857d-51a37cf40be8
```

Get roles for the Entra application registration specified by its name

```sh
m365 entra app role list --appName "My app"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "allowedMemberTypes": [
        "User"
      ],
      "description": "Managers",
      "displayName": "Managers",
      "id": "0a545986-9142-4c88-909c-34f3c11abbc4",
      "isEnabled": true,
      "origin": "Application",
      "value": "managers"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  displayName  description  id
  -----------  -----------  ------------------------------------
  Managers     Managers     0a545986-9142-4c88-909c-34f3c11abbc4
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  description,displayName,id,isEnabled,origin,value
  Managers,Managers,0a545986-9142-4c88-909c-34f3c11abbc4,1,Application,managers
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra app role list --appObjectId "29d99e17-96b7-46aa-816d-b52bfeeafeb9"

  Date: 2023-06-01

  ## Managers (0a545986-9142-4c88-909c-34f3c11abbc4)

  Property | Value
  ---------|-------
  description | Managers
  displayName | Managers
  id | 0a545986-9142-4c88-909c-34f3c11abbc4
  isEnabled | true
  origin | Application
  value | managers
  ```

  </TabItem>
</Tabs>
