-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra group get

Gets information about the specified Entra group

## Usage

```sh
m365 entra group get [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The object Id of the Entra group. Specify either `id` or `displayName` but not both.

`-n, --displayName [displayName]`
: The display name of the Entra group. Specify either `id` or `displayName` but not both.

`-p, --properties [properties]`
: Comma-separated list of properties to retrieve.
```

<Global />

## Remarks

Using the `--properties` option, you can specify a comma-separated list of group properties to retrieve from the Microsoft Graph. If you don't specify any properties, the command will output the default properties returned by Graph.

## Examples

Get information about an Entra Group by id.

```sh
m365 entra group get --id 1caf7dcd-7e83-4c3a-94f7-932a1299c844
```

Get information about an Entra Group by its display name with specified properties.

```sh
m365 entra group get --displayName Finance --properties "mail,displayName"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "c541afac-508e-40c7-8880-5a601b41737b",
    "deletedDateTime": null,
    "classification": null,
    "createdDateTime": "2022-11-13T19:16:32Z",
    "creationOptions": [
      "YammerProvisioning"
    ],
    "description": "This is the default group for everyone in the network",
    "displayName": "All Company",
    "expirationDateTime": null,
    "groupTypes": [
      "Unified"
    ],
    "isAssignableToRole": null,
    "mail": "allcompany@contoso.onmicrosoft.com",
    "mailEnabled": true,
    "mailNickname": "allcompany",
    "membershipRule": null,
    "membershipRuleProcessingState": null,
    "onPremisesDomainName": null,
    "onPremisesLastSyncDateTime": null,
    "onPremisesNetBiosName": null,
    "onPremisesSamAccountName": null,
    "onPremisesSecurityIdentifier": null,
    "onPremisesSyncEnabled": null,
    "preferredDataLocation": null,
    "preferredLanguage": null,
    "proxyAddresses": [
      "SPO:EXAMPLE_SECRET_VALUE_PLACEHOLDER@EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "SMTP:allcompany@contoso.onmicrosoft.com"
    ],
    "renewedDateTime": "2022-11-13T19:16:32Z",
    "resourceBehaviorOptions": [
      "CalendarMemberReadOnly"
    ],
    "resourceProvisioningOptions": [],
    "securityEnabled": false,
    "securityIdentifier": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "theme": null,
    "visibility": "Public",
    "onPremisesProvisioningErrors": []
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  classification               : null
  createdDateTime              : 2022-11-13T19:16:32Z
  creationOptions              : ["YammerProvisioning"]
  deletedDateTime              : null
  description                  : This is the default group for everyone in the network
  displayName                  : All Company
  expirationDateTime           : null
  groupTypes                   : ["Unified"]
  id                           : c541afac-508e-40c7-8880-5a601b41737b
  isAssignableToRole           : null
  mail                         : allcompany@contoso.onmicrosoft.com
  mailEnabled                  : true
  mailNickname                 : allcompany
  membershipRule               : null
  membershipRuleProcessingState: null
  onPremisesDomainName         : null
  onPremisesLastSyncDateTime   : null
  onPremisesNetBiosName        : null
  onPremisesProvisioningErrors : []
  onPremisesSamAccountName     : null
  onPremisesSecurityIdentifier : null
  onPremisesSyncEnabled        : null
  preferredDataLocation        : null
  preferredLanguage            : null
  proxyAddresses               : ["SPO:EXAMPLE_SECRET_VALUE_PLACEHOLDER@EXAMPLE_SECRET_VALUE_PLACEHOLDER","SMTP:allcompany@contoso.onmicrosoft.com"]
  renewedDateTime              : 2022-11-13T19:16:32Z
  resourceBehaviorOptions      : ["CalendarMemberReadOnly"]
  resourceProvisioningOptions  : []
  securityEnabled              : false
  securityIdentifier           : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  theme                        : null
  visibility                   : Public
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,deletedDateTime,classification,createdDateTime,creationOptions,description,displayName,expirationDateTime,groupTypes,isAssignableToRole,mail,mailEnabled,mailNickname,membershipRule,membershipRuleProcessingState,onPremisesDomainName,onPremisesLastSyncDateTime,onPremisesNetBiosName,onPremisesSamAccountName,onPremisesSecurityIdentifier,onPremisesSyncEnabled,preferredDataLocation,preferredLanguage,proxyAddresses,renewedDateTime,resourceBehaviorOptions,resourceProvisioningOptions,securityEnabled,securityIdentifier,theme,visibility,onPremisesProvisioningErrors
  c541afac-508e-40c7-8880-5a601b41737b,,,2022-11-13T19:16:32Z,"[""YammerProvisioning""]",This is the default group for everyone in the network,All Company,,"[""Unified""]",,allcompany@contoso.onmicrosoft.com,1,allcompany,,,,,,,,,,,"[""SPO:EXAMPLE_SECRET_VALUE_PLACEHOLDER@EXAMPLE_SECRET_VALUE_PLACEHOLDER"",""SMTP:allcompany@contoso.onmicrosoft.com""]",2022-11-13T19:16:32Z,"[""CalendarMemberReadOnly""]",[],,EXAMPLE_SECRET_VALUE_PLACEHOLDER,,Public,[]
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra group get --id "c541afac-508e-40c7-8880-5a601b41737b"

  Date: 2022-11-13

  ## All Company (c541afac-508e-40c7-8880-5a601b41737b)

  Property | Value
  ---------|-------
  id | c541afac-508e-40c7-8880-5a601b41737b
  createdDateTime | 2022-11-13T19:16:32Z
  displayName | All Company
  mail | allcompany@contoso.onmicrosoft.com
  mailEnabled | true
  mailNickname | allcompany
  renewedDateTime | 2022-11-13T19:16:32Z
  securityEnabled | false
  securityIdentifier | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  visibility | Private
  ```

  </TabItem>
</Tabs>
