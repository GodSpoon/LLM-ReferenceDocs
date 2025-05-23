-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra user signin list

Retrieves the Entra ID user sign-ins for the tenant

## Usage

```sh
m365 entra user signin list [options]
```

## Options

```md definition-list
`-n, --userName [userName]`
: Filter the user sign-ins by given User's UPN (user principal name), eg. `johndoe@example.com`. Specify either userName or userId

`--userId [userId]`
: Filter the user sign-ins by given User's Id. Specify either userName or userId

`--appDisplayName [appDisplayName]`
: Filter the user sign-ins by the given application display name. Specify either appDisplayName or appId

`--appId [appId]`
: Filter the user sign-ins by the given application identifier. Specify either appDisplayName or appId
```

<Global />

## Examples

Get all user's sign-ins in your tenant.

```sh
m365 entra user signin list
```

Get all user's sign-ins filter by given user's UPN in the tenant.

```sh
m365 entra user signin list --userName 'johndoe@example.com'
```

Get all user's sign-ins filter by given user's Id in the tenant.

```sh
m365 entra user signin list --userId '11111111-1111-1111-1111-111111111111'
```

Get all user's sign-ins filter by given application display name in the tenant.

```sh
m365 entra user signin list --appDisplayName 'Graph explorer'
```

Get all user's sign-ins filter by given application identifier in the tenant.

```sh
m365 entra user signin list --appId '00000000-0000-0000-0000-000000000000'
```

Get all user's sign-ins filter by given user's UPN and application display name in the tenant.

```sh
m365 entra user signin list --userName 'johndoe@example.com' --appDisplayName 'Graph explorer'
```

Get all user's sign-ins filter by given user's Id and application display name in the tenant.

```sh
m365 entra user signin list --userId '11111111-1111-1111-1111-111111111111' --appDisplayName 'Graph explorer'
```

Get all user's sign-ins filter by given user's UPN and application identifier in the tenant.

```sh
m365 entra user signin list --userName 'johndoe@example.com' --appId '00000000-0000-0000-0000-000000000000'
```

Get all user's sign-ins filter by given user's Id and application identifier in the tenant.

```sh
m365 entra user signin list --userId '11111111-1111-1111-1111-111111111111' --appId '00000000-0000-0000-0000-000000000000'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "66ea54eb-6301-4ee5-be62-ff5a759b0100",
      "createdDateTime": "2020-03-13T19:15:41.6195833Z",
      "userDisplayName": "Test Contoso",
      "userPrincipalName": "john@contoso.com",
      "userId": "26be570a-ae82-4189-b4e2-a37c6808512d",
      "appId": "de8bc8b5-d9f9-48b1-a8ad-b748da725064",
      "appDisplayName": "Graph explorer",
      "ipAddress": "131.107.159.37",
      "clientAppUsed": "Browser",
      "correlationId": "d79f5bee-5860-4832-928f-3133e22ae912",
      "conditionalAccessStatus": "notApplied",
      "isInteractive": true,
      "riskDetail": "none",
      "riskLevelAggregated": "none",
      "riskLevelDuringSignIn": "none",
      "riskState": "none",
      "riskEventTypes": [],
      "resourceDisplayName": "Microsoft Graph",
      "resourceId": "00000003-0000-0000-c000-000000000000",
      "status": {
        "errorCode": 0,
        "failureReason": null,
        "additionalDetails": null
      },
      "deviceDetail": {
        "deviceId": "",
        "displayName": null,
        "operatingSystem": "Windows 10",
        "browser": "Edge 80.0.361",
        "isCompliant": null,
        "isManaged": null,
        "trustType": null
      },
      "location": {
        "city": "Redmond",
        "state": "Washington",
        "countryOrRegion": "US",
        "geoCoordinates": {
          "altitude": null,
          "latitude": 47.68050003051758,
          "longitude": -122.12094116210938
        }
      },
      "appliedConditionalAccessPolicies": [
        {
          "id": "de7e60eb-ed89-4d73-8205-2227def6b7c9",
          "displayName": "SharePoint limited access for guest workers",
          "enforcedGrantControls": [],
          "enforcedSessionControls": [],
          "result": "notEnabled"
        },
        {
          "id": "6701123a-b4c6-48af-8565-565c8bf7cabc",
          "displayName": "Medium signin risk block",
          "enforcedGrantControls": [],
          "enforcedSessionControls": [],
          "result": "notEnabled"
        }
      ]
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    userPrincipalName         appId                                 appDisplayName  createdDateTime
  ------------------------------------  ------------------------  ------------------------------------  --------------  ----------------------------
  66ea54eb-6301-4ee5-be62-ff5a759b0100  testaccount1@contoso.com  de8bc8b5-d9f9-48b1-a8ad-b748da725064  Graph explorer  2020-03-13T19:15:41.6195833Z
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,userPrincipalName,appId,appDisplayName,createdDateTime
  66ea54eb-6301-4ee5-be62-ff5a759b0100,john@contoso.com,de8bc8b5-d9f9-48b1-a8ad-b748da725064,Graph explorer,2020-03-13T19:15:41.6195833Z
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra user signin list

  Date: 2023-06-02

  Property | Value
  ---------|-------
  # entra user signin list

  Date: 2023-06-02

  ## 66ea54eb-6301-4ee5-be62-ff5a759b0100

  Property | Value
  ---------|-------
  id | 66ea54eb-6301-4ee5-be62-ff5a759b0100
  createdDateTime | 2020-03-13T19:15:41.6195833Z
  userDisplayName | Test Contoso
  userPrincipalName | john@contoso.com
  userId | 26be570a-ae82-4189-b4e2-a37c6808512d
  appId | de8bc8b5-d9f9-48b1-a8ad-b748da725064
  appDisplayName | Graph explorer
  ipAddress | 131.107.159.37
  clientAppUsed | Browser
  correlationId | d79f5bee-5860-4832-928f-3133e22ae912
  conditionalAccessStatus | notApplied
  isInteractive | true
  riskDetail | none
  riskLevelAggregated | none
  riskLevelDuringSignIn | none
  riskState | none
  resourceDisplayName | Microsoft Graph
  resourceId | 00000003-0000-0000-c000-000000000000
  ```

  </TabItem>
</Tabs>
