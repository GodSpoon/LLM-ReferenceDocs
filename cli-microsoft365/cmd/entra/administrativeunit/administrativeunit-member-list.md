-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra administrativeunit member list

Retrieves members (users, groups, or devices) of an administrative unit

## Usage

```sh
m365 entra administrativeunit member list [options]
```

## Options

```md definition-list
`-i, --administrativeUnitId [administrativeUnitId]`
: The id of the administrative unit. Specify either `administrativeUnitId` or `administrativeUnitName`.

`-n, --administrativeUnitName [administrativeUnitName]`
: The name of the administrative unit. Specify either `administrativeUnitId` or `administrativeUnitName`.

`-t, --type [type]`
: When specified, the command returns only objects of specified type. Allowed values are `user`, `group` and `device`.

`-p, --properties [properties]`
: Comma-separated list of properties to retrieve.

`-f, --filter [filter]`
: OData filter to use to query the list of members with. Applied only when `type` is specified.
```

<Global />

## Remarks

To list the members of a hidden membership in an administrative unit, the `Member.Read.Hidden` permission is required.

When the `properties` option includes values with a `/`, for example: `manager/displayName`, an additional `$expand` query parameter will be included on manager.

## Examples

List members of an administrative unit specified by id

```sh
m365 entra administrativeunit member list --administrativeUnitId 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7
```

List members of an administrative unit specified by id. For each one return the `id` and the `displayName`

```sh
m365 entra administrativeunit member list --administrativeUnitId 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7 --properties 'id,displayName'
```

List members of an administrative unit specified by name

```sh
m365 entra administrativeunit member list --administrativeUnitName 'Marketing Division'
```

List users of an administrative unit specified by id

```sh
m365 entra administrativeunit member list --administrativeUnitId 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7 --type user
```

List users of an administrative unit specified by id that are guest users

```sh
m365 entra administrativeunit member list --administrativeUnitId 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7 --type user --filter "userType eq 'Guest'"
```

List groups of an administrative unit specified by id

```sh
m365 entra administrativeunit member list --administrativeUnitId 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7 --type group
```

List groups of an administrative unit specified by id and include owners names, for each member return the `id` and the `displayName`

```sh
m365 entra administrativeunit member list --administrativeUnitId 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7 --type group --properties 'id,displayName,owners/displayName'
```

List devices of an administrative unit specified by id

```sh
m365 entra administrativeunit member list --administrativeUnitId 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7 --type device
```

List devices with linux operating system of an administrative unit specified by id

```sh
m365 entra administrativeunit member list --administrativeUnitId 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7 --type device --filter "operatingSystem eq 'linux'"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "64131a70-beb9-4ccb-b590-4401e58446ec",
      "businessPhones": [
        "+20 255501070"
      ],
      "displayName": "Pradeep Gupta",
      "givenName": "Pradeep",
      "jobTitle": "Accountant",
      "mail": "PradeepG@contoso.com",
      "mobilePhone": null,
      "officeLocation": "98/2202",
      "preferredLanguage": "en-US",
      "surname": "Gupta",
      "userPrincipalName": "PradeepG@contoso.com",
      "type": "user"
    },
    {
      "id": "c121c70b-deb1-43f7-8298-9111bf3036b4",
      "deletedDateTime": null,
      "classification": null,
      "createdDateTime": "2023-02-22T06:39:13Z",
      "creationOptions": [
        "Team",
        "ExchangeProvisioningFlags:3552"
      ],
      "description": "Welcome to the team that we've assembled to create the Mark 8.",
      "displayName": "Mark 8 Project Team",
      "expirationDateTime": null,
      "groupTypes": [
        "Unified"
      ],
      "isAssignableToRole": null,
      "mail": "Mark8ProjectTeam@contoso.com",
      "mailEnabled": true,
      "mailNickname": "Mark8ProjectTeam",
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
        "SMTP:Mark8ProjectTeam@contoso.com"
      ],
      "renewedDateTime": "2023-02-22T06:39:13Z",
      "resourceBehaviorOptions": [
        "HideGroupInOutlook",
        "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
        "WelcomeEmailDisabled"
      ],
      "resourceProvisioningOptions": [
        "Team"
      ],
      "securityEnabled": false,
      "securityIdentifier": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "theme": null,
      "visibility": "Public",
      "onPremisesProvisioningErrors": [],
      "serviceProvisioningErrors": [],
      "type": "group"
    },
    {
      "id": "3f9fd7c3-73ad-4ce3-b053-76bb8252964d",
      "deletedDateTime": null,
      "accountEnabled": true,
      "approximateLastSignInDateTime": null,
      "complianceExpirationDateTime": null,
      "createdDateTime": "2023-11-06T06:18:26Z",
      "deviceCategory": null,
      "deviceId": "4c299165-6e8f-4b45-a5ba-c5d250a707ff",
      "deviceMetadata": null,
      "deviceOwnership": null,
      "deviceVersion": null,
      "displayName": "AdeleVence-PC",
      "domainName": null,
      "enrollmentProfileName": null,
      "enrollmentType": null,
      "externalSourceName": null,
      "isCompliant": null,
      "isManaged": null,
      "isRooted": null,
      "managementType": null,
      "manufacturer": null,
      "mdmAppId": null,
      "model": null,
      "onPremisesLastSyncDateTime": null,
      "onPremisesSyncEnabled": null,
      "operatingSystem": "windows",
      "operatingSystemVersion": "10",
      "physicalIds": [],
      "profileType": null,
      "registrationDateTime": null,
      "sourceType": null,
      "systemLabels": [],
      "trustType": null,
      "extensionAttributes": {
        "extensionAttribute1": null,
        "extensionAttribute2": null,
        "extensionAttribute3": null,
        "extensionAttribute4": null,
        "extensionAttribute5": null,
        "extensionAttribute6": null,
        "extensionAttribute7": null,
        "extensionAttribute8": null,
        "extensionAttribute9": null,
        "extensionAttribute10": null,
        "extensionAttribute11": null,
        "extensionAttribute12": null,
        "extensionAttribute13": null,
        "extensionAttribute14": null,
        "extensionAttribute15": null
      },
      "alternativeSecurityIds": [
        {
          "type": 2,
          "identityProvider": null,
          "key": "Y3YxN2E1MWFlYw=="
        }
      ],
      "type": "device"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    displayName
  ------------------------------------  -------------------
  64131a70-beb9-4ccb-b590-4401e58446ec  Pradeep Gupta
  c121c70b-deb1-43f7-8298-9111bf3036b4  Mark 8 Project Team
  3f9fd7c3-73ad-4ce3-b053-76bb8252964d  AdeleVence-PC
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,givenName,jobTitle,mail,officeLocation,preferredLanguage,surname,userPrincipalName,type
  64131a70-beb9-4ccb-b590-4401e58446ec,Pradeep Gupta,Pradeep,Accountant,PradeepG@contoso.com,98/2202,en-US,Gupta,PradeepG@contoso.com,user
  c121c70b-deb1-43f7-8298-9111bf3036b4,Mark 8 Project Team,,,Mark8ProjectTeam@contoso.com,,,,,group
  3f9fd7c3-73ad-4ce3-b053-76bb8252964d,AdeleVence-PC,,,,,,,,device
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Date: 11/9/2023

  ## Pradeep Gupta (64131a70-beb9-4ccb-b590-4401e58446ec)

  Property | Value
  ---------|-------
  id | 64131a70-beb9-4ccb-b590-4401e58446ec
  displayName | Pradeep Gupta
  givenName | Pradeep
  jobTitle | Accountant
  mail | PradeepG@contoso.com
  officeLocation | 98/2202
  preferredLanguage | en-US
  surname | Gupta
  userPrincipalName | PradeepG@contoso.com
  type | user

  ## Mark 8 Project Team (c121c70b-deb1-43f7-8298-9111bf3036b4)

  Property | Value
  ---------|-------
  id | c121c70b-deb1-43f7-8298-9111bf3036b4
  createdDateTime | 2023-02-22T06:39:13Z
  description | Welcome to the team that we've assembled to create the Mark 8.
  displayName | Mark 8 Project Team
  mail | Mark8ProjectTeam@contoso.com
  mailEnabled | true
  mailNickname | Mark8ProjectTeam
  renewedDateTime | 2023-02-22T06:39:13Z
  securityEnabled | false
  securityIdentifier | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  visibility | Public
  type | group

  ## AdeleVence-PC (3f9fd7c3-73ad-4ce3-b053-76bb8252964d)

  Property | Value
  ---------|-------
  id | 3f9fd7c3-73ad-4ce3-b053-76bb8252964d
  accountEnabled | true
  createdDateTime | 2023-11-09T06:18:26Z
  deviceId | 4c299165-6e8f-4b45-a5ba-c5d250a707ff
  displayName | AdeleVence-PC
  operatingSystem | windows
  operatingSystemVersion | 10
  type | device
  ```

  </TabItem>
</Tabs>

## More information

- Administrative units: https://learn.microsoft.com/entra/identity/role-based-access-control/administrative-units
