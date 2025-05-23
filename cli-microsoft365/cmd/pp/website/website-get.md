-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp website get

Gets information about the specified Power Pages website.

## Usage

```sh
m365 pp website get [options]
```

## Options

```md definition-list
`-u, --url [url]`
: The URL of the website to retrieve. Specify either `url`, `name` or `id`.

`-n, --name [name]`
: The name of the website to retrieve. Specify either `url`, `name` or `id`.

`-i, --id [id]`
: The WebSite Id (GUID) of the website to retrieve. Specify either `url`, `name` or `id`.

`-e, --environmentName <environmentName>`
: The name of the environment from which to retrieve the Power Pages website.
```

<Global />

## Examples

Retrieve Demo Power Pages website by name in the given environment using `name`.

```sh
m365 pp website get --name Demo --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER 
```

Retrieve Demo Power Pages website by name in the given environment using `id`.

```sh
m365 pp website get --id 4916bb2c-91e1-4716-91d5-b6171928fac9 --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER 
```

Retrieve Demo Power Pages website by name in the given environment using `url`.

```sh
m365 pp website get --url https://site-0uaq9.powerappsportals.com --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER 
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "@odata.metadata": "https://api.powerplatform.com/powerpages/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/websites/$metadata#Websites",
    "id": "4916bb2c-91e1-4716-91d5-b6171928fac9",
    "name": "Site 1",
    "createdOn": "2024-10-27T12:00:03",
    "templateName": "DefaultPortalTemplate",
    "websiteUrl": "https://site-0uaq9.powerappsportals.com",
    "tenantId": "727dc1e9-3cd1-4d1f-8102-ab5c936e52f0",
    "dataverseInstanceUrl": "https://org0cd4b2b9.crm4.dynamics.com/",
    "environmentName": "Contoso (default)",
    "environmentId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "dataverseOrganizationId": "2d58aeac-74d4-4939-98d1-e05a70a655ba",
    "selectedBaseLanguage": 1033,
    "customHostNames": [],
    "websiteRecordId": "5eb107a6-5ac2-4e1c-a3b9-d5c21bbc10ce",
    "subdomain": "site-0uaq9",
    "packageInstallStatus": "Installed",
    "type": "Trial",
    "trialExpiringInDays": 86,
    "suspendedWebsiteDeletingInDays": 93,
    "packageVersion": "9.6.9.39",
    "isEarlyUpgradeEnabled": false,
    "isCustomErrorEnabled": true,
    "applicationUserAadAppId": "3f57aca7-5051-41b2-989d-26da8af7a53e",
    "ownerId": "33469a62-c3af-4cfe-b893-854eceab96da",
    "status": "OperationComplete",
    "siteVisibility": "private",
    "dataModel": "Enhanced"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id            : 4916bb2c-91e1-4716-91d5-b6171928fac9
  name          : Site 1
  createdOn     : 2024-10-27T12:00:03
  templateName  : DefaultPortalTemplate
  websiteUrl    : https://site-0uaq9.powerappsportals.com
  tenantId      : 727dc1e9-3cd1-4d1f-8102-ab5c936e52f0
  dataverseInstanceUrl: https://org0cd4b2b9.crm4.dynamics.com/
  environmentName: Contoso (default)
  environmentId : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  dataverseOrganizationId: 2d58aeac-74d4-4939-98d1-e05a70a655ba
  selectedBaseLanguage: 1033
  customHostNames: []
  websiteRecordId: 5eb107a6-5ac2-4e1c-a3b9-d5c21bbc10ce
  subdomain     : site-0uaq9
  packageInstallStatus: Installed
  type          : Trial
  trialExpiringInDays: 86
  suspendedWebsiteDeletingInDays: 93
  packageVersion: 9.6.9.39
  isEarlyUpgradeEnabled: false
  isCustomErrorEnabled: true
  applicationUserAadAppId: 3f57aca7-5051-41b2-989d-26da8af7a53e
  ownerId       : 33469a62-c3af-4cfe-b893-854eceab96da
  status        : OperationComplete
  siteVisibility: private
  dataModel     : Enhanced
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  @odata.metadata,id,name,createdOn,templateName,websiteUrl,tenantId,dataverseInstanceUrl,environmentName,environmentId,dataverseOrganizationId,selectedBaseLanguage,websiteRecordId,subdomain,packageInstallStatus,type,trialExpiringInDays,suspendedWebsiteDeletingInDays,packageVersion,isEarlyUpgradeEnabled,isCustomErrorEnabled,applicationUserAadAppId,ownerId,status,siteVisibility,dataModel
  https://api.powerplatform.com/powerpages/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/websites/$metadata#Websites,4916bb2c-91e1-4716-91d5-b6171928fac9,Site 1,2024-10-27T12:00:03,DefaultPortalTemplate,https://site-0uaq9.powerappsportals.com,727dc1e9-3cd1-4d1f-8102-ab5c936e52f0,https://org0cd4b2b9.crm4.dynamics.com/,Contoso (default),EXAMPLE_SECRET_VALUE_PLACEHOLDER,2d58aeac-74d4-4939-98d1-e05a70a655ba,1033,5eb107a6-5ac2-4e1c-a3b9-d5c21bbc10ce,site-0uaq9,Installed,Trial,86,93,9.6.9.39,0,1,3f57aca7-5051-41b2-989d-26da8af7a53e,33469a62-c3af-4cfe-b893-854eceab96da,OperationComplete,private,Enhanced
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pp website get --debug "false" --verbose "false" --name "Site 1" --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

  Date: 27/10/2024

  ## Site 1 (4916bb2c-91e1-4716-91d5-b6171928fac9)

  Property | Value
  ---------|-------
  @odata.metadata | https://api.powerplatform.com/powerpages/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/websites/$metadata#Websites
  id | 4916bb2c-91e1-4716-91d5-b6171928fac9
  name | Site 1
  createdOn | 2024-10-27T12:00:03
  templateName | DefaultPortalTemplate
  websiteUrl | https://site-0uaq9.powerappsportals.com
  tenantId | 727dc1e9-3cd1-4d1f-8102-ab5c936e52f0
  dataverseInstanceUrl | https://org0cd4b2b9.crm4.dynamics.com/
  environmentName | Contoso (default)
  environmentId | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  dataverseOrganizationId | 2d58aeac-74d4-4939-98d1-e05a70a655ba
  selectedBaseLanguage | 1033
  websiteRecordId | 5eb107a6-5ac2-4e1c-a3b9-d5c21bbc10ce
  subdomain | site-0uaq9
  packageInstallStatus | Installed
  type | Trial
  trialExpiringInDays | 86
  suspendedWebsiteDeletingInDays | 93
  packageVersion | 9.6.9.39
  isEarlyUpgradeEnabled | false
  isCustomErrorEnabled | true
  applicationUserAadAppId | 3f57aca7-5051-41b2-989d-26da8af7a53e
  ownerId | 33469a62-c3af-4cfe-b893-854eceab96da
  status | OperationComplete
  siteVisibility | private
  dataModel | Enhanced
  ```

  </TabItem>
</Tabs>
