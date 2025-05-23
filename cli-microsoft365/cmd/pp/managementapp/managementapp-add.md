-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp managementapp add

Register management application for Power Platform

## Usage

```sh
m365 pp managementapp add [options]
```

## Options

```md definition-list
`--appId [appId]`
: Application (client) ID of the Microsoft Entra application registration to register as a management app. Specify either `appId`, `objectId` or `name`

`--objectId [objectId]`
: Object ID of the Microsoft Entra application registration to register as a management app. Specify either `appId`, `objectId` or `name`

`--name [name]`
: Name of the Microsoft Entra application registration to register as a management app. Specify either `appId`, `objectId` or `name`
```

<Global />

## Remarks

To execute this command the first time you'll need sign in using the Microsoft Azure PowerShell application registration. You can do this by executing `m365 login --appId 1950a258-227b-4e31-a9cf-717495945fc2`. To register the Microsoft Entra application registration that CLI for Microsoft 365 uses by default, execute `m365 pp managementapp add--appId 31359c7f-bd7e-475c-86db-fdb8c937548e`.

For best performance use the `appId` option to reference the Microsoft Entra application registration to update. If you use `objectId` or `name`, this command will first need to find the corresponding `appId` for that application.

If the command finds multiple Microsoft Entra application registrations with the specified app name, it will prompt you to disambiguate which app it should use, listing the discovered object IDs.

## Examples

Register CLI for Microsoft 365 as a management application for the Power Platform.

```sh
m365 pp managementapp add --appId 31359c7f-bd7e-475c-86db-fdb8c937548e
```

Register a Microsoft Entra application with the specified object ID as a management application for the Power Platform.

```sh
m365 pp managementapp add --objectId d75be2e1-0204-4f95-857d-51a37cf40be8
```

Register a Microsoft Entra application named _My app_ as a management application for the Power Platform.

```sh
m365 pp managementapp add --name "My app"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "applicationId":"31359c7f-bd7e-475c-86db-fdb8c937548e"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  applicationId: 31359c7f-bd7e-475c-86db-fdb8c937548e
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  applicationId
  31359c7f-bd7e-475c-86db-fdb8c937548e
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pp managementapp add --appId "31359c7f-bd7e-475c-86db-fdb8c937548e"

  Date: 9/1/2023

  Property | Value
  ---------|-------
  applicationId | 31359c7f-bd7e-475c-86db-fdb8c937548e
  ```

  </TabItem>
</Tabs>
