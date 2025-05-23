-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pa app list

Lists all Power Apps apps

## Usage

```sh
m365 pa app list [options]
```

## Options

```md definition-list
`-e, --environmentName [environmentName]`
: The name of the environment for which to retrieve available apps.

`--asAdmin`
: Set, to list all Power Apps as admin. Otherwise will return only your own apps.
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reaches general availability.

:::

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

By default, the `app list` command returns only your apps. To list all apps, use the `asAdmin` option and make sure to specify the `environment` option. You cannot specify only one of the options, when specifying the `environment` option the `asAdmin` option has to be present as well.

## Examples

List all your apps.

```sh
m365 pa app list
```

List all apps in a given environment.

```sh
m365 pa app list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --asAdmin
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "name":"37ea6004-f07b-46ca-8ef3-a256b67b4dbb",
      "id":"/providers/Microsoft.PowerApps/apps/37ea6004-f07b-46ca-8ef3-a256b67b4dbb",
      "type":"Microsoft.PowerApps/apps",
      "tags":{
        "primaryDeviceWidth":"1366",
        "primaryDeviceHeight":"768",
        "supportsPortrait":"true",
        "supportsLandscape":"true",
        "primaryFormFactor":"Tablet",
        "publisherVersion":"3.22102.32",
        "minimumRequiredApiVersion":"2.2.0",
        "hasComponent":"false",
        "hasUnlockedComponent":"false",
        "isUnifiedRootApp":"false",
        "sienaVersion":"20221025T212812Z-3.22102.32.0"
      },
      "properties":{
        "appVersion":"2022-10-25T21:28:12Z",
        "lastDraftVersion":"2022-10-25T21:28:12Z",
        "lifeCycleId":"Published",
        "status":"Ready",
        "createdByClientVersion":{
          "major":3,
          "minor":22102,
          "build":32,
          "revision":0,
          "majorRevision":0,
          "minorRevision":0
        },
        "minClientVersion":{
          "major":3,
          "minor":22102,
          "build":32,
          "revision":0,
          "majorRevision":0,
          "minorRevision":0
        },
        "owner":{
          "id":"fe36f75e-c103-410b-a18a-2bf6df06ac3a",
          "displayName":"contoso",
          "email":"user@contoso.onmicrosoft.com",
          "type":"User",
          "tenantId":"e1dd4023-a656-480a-8a0e-c1b1eec51e1d",
          "userPrincipalName":"user@contoso.onmicrosoft.com"
        },
        "createdBy":{
          "id":"fe36f75e-c103-410b-a18a-2bf6df06ac3a",
          "displayName":"contoso",
          "email":"user@contoso.onmicrosoft.com",
          "type":"User",
          "tenantId":"e1dd4023-a656-480a-8a0e-c1b1eec51e1d",
          "userPrincipalName":"user@contoso.onmicrosoft.com"
        },
        "lastModifiedBy":{
          "id":"fe36f75e-c103-410b-a18a-2bf6df06ac3a",
          "displayName":"contoso",
          "email":"user@contoso.onmicrosoft.com",
          "type":"User",
          "tenantId":"e1dd4023-a656-480a-8a0e-c1b1eec51e1d",
          "userPrincipalName":"user@contoso.onmicrosoft.com"
        },
        "lastPublishedBy":{
          "id":"fe36f75e-c103-410b-a18a-2bf6df06ac3a",
          "displayName":"contoso",
          "email":"user@contoso.onmicrosoft.com",
          "type":"User",
          "tenantId":"e1dd4023-a656-480a-8a0e-c1b1eec51e1d",
          "userPrincipalName":"user@contoso.onmicrosoft.com"
        },
        "backgroundColor":"RGBA(0,176,240,1)",
        "backgroundImageUri":"https://pafeblobprodam.blob.core.windows.net:443/EXAMPLE_SECRET_VALUE_PLACEHOLDER/logoSmallFile?sv=2018-03-28&sr=c&sig=cOkbwChyhCO%2BEJpqMDRxrXaxRoPD1TbTy%2B%2BFkdJEOjI%3D&se=2022-12-24T10%3A06%3A27Z&sp=rl",
        "teamsColorIconUrl":"https://pafeblobprodam.blob.core.windows.net:443/EXAMPLE_SECRET_VALUE_PLACEHOLDER/teamscoloricon.png?sv=2018-03-28&sr=c&sig=EXAMPLE_SECRET_VALUE_PLACEHOLDER%3D&se=2022-12-24T10%3A06%3A27Z&sp=rl",
        "teamsOutlineIconUrl":"https://pafeblobprodam.blob.core.windows.net:443/EXAMPLE_SECRET_VALUE_PLACEHOLDER/teamsoutlineicon.png?sv=2018-03-28&sr=c&sig=EXAMPLE_SECRET_VALUE_PLACEHOLDER%3D&se=2022-12-24T10%3A06%3A27Z&sp=rl",
      "displayName":"Test application",
        "description":"",
        "commitMessage":"",
        "appUris":{
          "documentUri":{
            "value":"https://pafeblobprodam.blob.core.windows.net:443/EXAMPLE_SECRET_VALUE_PLACEHOLDER/document.msapp?sv=2018-03-28&sr=c&sig=EXAMPLE_SECRET_VALUE_PLACEHOLDER%3D&se=2022-11-04T12%3A00%3A00Z&sp=rl",
            "readonlyValue":"https://EXAMPLE_SECRET_VALUE_PLACEHOLDER/EXAMPLE_SECRET_VALUE_PLACEHOLDER/document.msapp?sv=2018-03-28&sr=c&sig=EXAMPLE_SECRET_VALUE_PLACEHOLDER%3D&se=2022-11-04T12%3A00%3A00Z&sp=rl"
          },
          "imageUris":[],
          "additionalUris":[]
        },
        "createdTime":"2022-10-25T21:28:12.7171469Z",
        "lastModifiedTime":"2022-10-25T21:28:12.7456297Z",
        "lastPublishTime":"2022-10-25T21:28:12Z",
        "sharedGroupsCount":0,
        "sharedUsersCount":0,
        "appOpenProtocolUri":"ms-apps:///providers/Microsoft.PowerApps/apps/37ea6004-f07b-46ca-8ef3-a256b67b4dbb",
        "appOpenUri":"https://apps.powerapps.com/play/e/EXAMPLE_SECRET_VALUE_PLACEHOLDER/a/37ea6004-f07b-46ca-8ef3-a256b67b4dbb?tenantId=e1dd4023-a656-480a-8a0e-c1b1eec51e1d&hint=296b0ef7-b4d0-4124-b835-f9c220a1f4bc",
        "appPlayUri":"https://apps.powerapps.com/play/e/EXAMPLE_SECRET_VALUE_PLACEHOLDER/a/37ea6004-f07b-46ca-8ef3-a256b67b4dbb?tenantId=e1dd4023-a656-480a-8a0e-c1b1eec51e1d",
        "appPlayEmbeddedUri":"https://apps.powerapps.com/play/e/EXAMPLE_SECRET_VALUE_PLACEHOLDER/a/37ea6004-f07b-46ca-8ef3-a256b67b4dbb?tenantId=e1dd4023-a656-480a-8a0e-c1b1eec51e1d&hint=296b0ef7-b4d0-4124-b835-f9c220a1f4bc&telemetryLocation=eu",
        "appPlayTeamsUri":"https://apps.powerapps.com/play/e/EXAMPLE_SECRET_VALUE_PLACEHOLDER/a/37ea6004-f07b-46ca-8ef3-a256b67b4dbb?tenantId=e1dd4023-a656-480a-8a0e-c1b1eec51e1d&source=teamstab&hint=296b0ef7-b4d0-4124-b835-f9c220a1f4bc&telemetryLocation=eu&locale={locale}&channelId={channelId}&channelType={channelType}&chatId={chatId}&groupId={groupId}&hostClientType={hostClientType}&isFullScreen={isFullScreen}&entityId={entityId}&subEntityId={subEntityId}&teamId={teamId}&teamType={teamType}&theme={theme}&userTeamRole={userTeamRole}",
        "userAppMetadata":{
          "favorite":"NotSpecified",
          "includeInAppsList":true
        },
        "isFeaturedApp":false,
        "bypassConsent":false,
        "isHeroApp":false,
        "environment":{
          "id":"/providers/Microsoft.PowerApps/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER",
          "name":"EXAMPLE_SECRET_VALUE_PLACEHOLDER"
        },
        "appPackageDetails":{
          "playerPackage":{
            "value":"https://pafeblobprodam.blob.core.windows.net:443/EXAMPLE_SECRET_VALUE_PLACEHOLDER/5b38cd68-a930-4a14-be71-c622de887d1a/player.msappk?sv=2018-03-28&sr=c&sig=eztEkTd1pFaFEITA%2Bqqj2XCpxwgeujMC7FahMmEkujA%3D&se=2022-11-04T12%3A00%3A00Z&sp=rl",
            "readonlyValue":"https://EXAMPLE_SECRET_VALUE_PLACEHOLDER/EXAMPLE_SECRET_VALUE_PLACEHOLDER/5b38cd68-a930-4a14-be71-c622de887d1a/player.msappk?sv=2018-03-28&sr=c&sig=eztEkTd1pFaFEITA%2Bqqj2XCpxwgeujMC7FahMmEkujA%3D&se=2022-11-04T12%3A00%3A00Z&sp=rl"
          },
          "webPackage":{
            "value":"https://pafeblobprodam.blob.core.windows.net:443/EXAMPLE_SECRET_VALUE_PLACEHOLDER/5b38cd68-a930-4a14-be71-c622de887d1a/web/index.web.html?sv=2018-03-28&sr=c&sig=eztEkTd1pFaFEITA%2Bqqj2XCpxwgeujMC7FahMmEkujA%3D&se=2022-11-04T12%3A00%3A00Z&sp=rl",
            "readonlyValue":"https://EXAMPLE_SECRET_VALUE_PLACEHOLDER/EXAMPLE_SECRET_VALUE_PLACEHOLDER/5b38cd68-a930-4a14-be71-c622de887d1a/web/index.web.html?sv=2018-03-28&sr=c&sig=eztEkTd1pFaFEITA%2Bqqj2XCpxwgeujMC7FahMmEkujA%3D&se=2022-11-04T12%3A00%3A00Z&sp=rl"
          },
          "unauthenticatedWebPackage":{
            "value":"https://pafeblobprodam.blob.core.windows.net/EXAMPLE_SECRET_VALUE_PLACEHOLDER/20221025T212824Z/index.web.html"
          },
          "documentServerVersion":{
            "major":3,
            "minor":22102,
            "build":33,
            "revision":0,
            "majorRevision":0,
            "minorRevision":0
          },
          "appPackageResourcesKind":"Split",
          "packagePropertiesJson":"{\"cdnUrl\":\"https://content.powerapps.com/resource/app\",\"preLoadIdx\":\"https://content.powerapps.com/resource/app/kdfj31mdao7t9/preloadindex.web.html\",\"id\":\"638023301009567627\",\"v\":2.1}",
          "id":"EXAMPLE_SECRET_VALUE_PLACEHOLDER://pafeblobprodam.blob.core.windows.net/EXAMPLE_SECRET_VALUE_PLACEHOLDER/5b38cd68-a930-4a14-be71-c622de887d1a/web/index.web.html?sv=2018-03-28&sr=c&sig=eztEkTd1pFaFEITA%2Bqqj2XCpxwgeujMC7FahMmEkujA%3D&se=2022-11-04T12%3A00%3A00Z&sp=rlhttps://pafeblobprodam.blob.core.windows.net/EXAMPLE_SECRET_VALUE_PLACEHOLDER/5b38cd68-a930-4a14-be71-c622de887d1a/player.msappk?sv=2018-03-28&sr=c&sig=eztEkTd1pFaFEITA%2Bqqj2XCpxwgeujMC7FahMmEkujA%3D&se=2022-11-04T12%3A00%3A00Z&sp=rlhttps://pafeblobprodam.blob.core.windows.net/EXAMPLE_SECRET_VALUE_PLACEHOLDER/20221025T212824Z/index.web.html"
        },
        "almMode":"Environment",
        "performanceOptimizationEnabled":true,
        "unauthenticatedWebPackageHint":"296b0ef7-b4d0-4124-b835-f9c220a1f4bc",
        "canConsumeAppPass":true,
        "enableModernRuntimeMode":false,
        "executionRestrictions":{
          "isTeamsOnly":false,
          "dataLossPreventionEvaluationResult":{
            "status":"Compliant",
            "lastEvaluationDate":"2022-10-25T21:28:30.2281817Z",
            "violations":[],
            "violationsByPolicy":[],
            "violationErrorMessage":"De app gebruikt de volgende connectors: ."
          }
        },
        "appPlanClassification":"Standard",
        "usesPremiumApi":false,
        "usesOnlyGrandfatheredPremiumApis":true,
        "usesCustomApi":false,
        "usesOnPremiseGateway":false,
        "usesPcfExternalServiceUsage":false,
        "isCustomizable":true
      },
      "appLocation":"europe",
      "appType":"ClassicCanvasApp",
      "displayName":"PowerApps Application"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  name                                 displayName
  ------------------------------------ ---------------------
  37ea6004-f07b-46ca-8ef3-a256b67b4dbb PowerApps Application   
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  name,displayName
  37ea6004-f07b-46ca-8ef3-a256b67b4dbb,"PowerApps Application"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pa app list

  Date: 9/1/2023

  ## PowerApps Application (/providers/Microsoft.PowerApps/apps/37ea6004-f07b-46ca-8ef3-a256b67b4dbb)

  Property | Value
  ---------|-------
  name | 37ea6004-f07b-46ca-8ef3-a256b67b4dbb
  id | /providers/Microsoft.PowerApps/apps/37ea6004-f07b-46ca-8ef3-a256b67b4dbb
  type | Microsoft.PowerApps/apps
  appLocation | europe
  appType | ClassicCanvasApp
  displayName | PowerApps Application
  ```

  </TabItem>
</Tabs>
