-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo serviceprincipal permissionrequest list

Lists pending permission requests

## Usage

```sh
m365 spo serviceprincipal permissionrequest list [options]
```

## Alias

```sh
m365 spo sp permissionrequest list
```

## Options

<Global />

## Remarks

:::info

The admin role that's required to list permissions depends on the API. To approve permissions to any of the third-party APIs registered in the tenant, the application administrator role is sufficient. To approve permissions for Microsoft Graph or any other Microsoft API, the Global Administrator role is required.

:::

## Examples

List all pending permission requests

```sh
m365 spo serviceprincipal permissionrequest list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Id": "6eceed61-77e4-424d-ae1d-696a0de4d768",
      "Resource": "Microsoft Graph",
      "ResourceId": "Microsoft Graph",
      "Scope": "Reports.Read.All"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Id                                    Resource         ResourceId       Scope
  ------------------------------------  ---------------  ---------------  -----------------------
  6eceed61-77e4-424d-ae1d-696a0de4d768  Microsoft Graph  Microsoft Graph  Reports.Read.All
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Id,Resource,ResourceId,Scope
  6eceed61-77e4-424d-ae1d-696a0de4d768,Microsoft Graph,Microsoft Graph,Reports.Read.All
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo serviceprincipal permissionrequest list 

  Date: 5/7/2023

  ## ecc2f667-e219-4c65-908e-957d68244d0c

  Property | Value
  ---------|-------
  Id | ecc2f667-e219-4c65-908e-957d68244d0c
  Resource | Microsoft Graph
  ResourceId | Microsoft Graph
  Scope | Calendars.Read
  ```

  </TabItem>
</Tabs>
