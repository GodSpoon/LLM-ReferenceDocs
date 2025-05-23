-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra group add

Creates a Microsoft Entra group

## Usage

```sh
m365 entra group add [options]
```

## Options

```md definition-list
`-n, --displayName <displayName>`
: The name for the group. The maximum length is 256 characters.

`-d, --description [description]`
: The description for the group.

`-t, --type <type>`
: The group type. Valid values: `microsoft365` or `security`.

`-m, --mailNickname [mailNickname]`
: The mail alias for the group (part before the @). Maximum length is 64 characters.

`--ownerIds [ownerIds]`
: Comma-separated list of IDs of Microsoft Entra ID users that will be group owners. Specify either `ownerIds` or `ownerUserNames`, but not both.

`--ownerUserNames [ownerUserNames]`
: Comma-separated list of UPNs of Microsoft Entra ID users that will be group owners. Specify either `ownerIds` or `ownerUserNames`, but not both.

`--memberIds [memberIds]`
: Comma-separated list of IDs of Microsoft Entra ID users that will be group members. Specify either `memberIds` or `memberUserNames`, but not both.

`--memberUserNames [memberUserNames]`
: Comma-separated list of UPNs of Microsoft Entra ID users that will be group members. Specify either `memberIds` or `memberUserNames`, but not both.

`--visibility [visibility]`
: Specifies the group join policy and group content visibility for Microsoft 365 groups. Possible values are: `Private`, `Public`, or `HiddenMembership`. Defaults to `Public`. Specify only when creating a group of type `microsoft365`.
```

<Global />

## Remarks

The `visibility` option affects the behavior of the group.

With the `Public` visibility:
- Anyone can join the group without needing owner permission. 
- Anyone can view the attributes of the group. 
- Anyone can see the members of the group.

With the `Private` visibilty:
- Owner permission is needed to join the group.
- Anyone can view the attributes of the group.
- Anyone can see the members of the group.

With the `HiddenMembership` visibility:
- Owner permission is needed to join the group.
- Guest users cannot view the attributes of the group.
- Non-members cannot see the members of the group. This setting doesn't affect visibility of group owners.
- Administrators (global, company, user, and helpdesk) can view the membership of the group.
- The group appears in the global address book (GAL).

:::note

The `HiddenMembership` visibility can be set only for Microsoft 365 groups when the groups are created. It can't be updated later.

:::

This command allows using unknown options. For a comprehensive list of group properties, please refer to the [Graph documentation page](https://learn.microsoft.com/graph/api/resources/group?view=graph-rest-1.0#properties).

If the specified option is not found, you will receive a `Resource 'xyz' does not exist or one of its queried reference-property objects are not present.` error.

## Examples

Create a security group without any owners or members

```sh
m365 entra group add --displayName Developers --type security
```

Create a private Microsoft 365 group with owners and members and a custom mail address

```sh
m365 entra group add --displayName Developers --type microsoft365 --mailNickname devs --ownerUserNames john.doe@contoso.com --memberUserNames "john.doe@contoso.com,adele.vance@contoso.com" --visibility Private
```

Create a public Microsoft 365 group without any owners or members

```sh
m365 entra group add --displayName Developers --type microsoft365 --description "This group is for all developers in the company." --visibility Public
```


## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "ae0e8388-cd70-427f-9503-c57498ee3337",
    "deletedDateTime": null,
    "classification": null,
    "createdDateTime": "2024-01-10T11:33:18Z",
    "creationOptions": [],
    "description": "This group is for all developers in the company.",
    "displayName": "Developers",
    "expirationDateTime": null,
    "groupTypes": [
      "Unified"
    ],
    "isAssignableToRole": null,
    "mail": "devs@contoso.com",
    "mailEnabled": true,
    "mailNickname": "devs",
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
      "SMTP:devs@contoso.com"
    ],
    "renewedDateTime": "2024-01-10T11:33:18Z",
    "resourceBehaviorOptions": [],
    "resourceProvisioningOptions": [],
    "securityEnabled": true,
    "securityIdentifier": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "theme": null,
    "visibility": "Public",
    "onPremisesProvisioningErrors": [],
    "serviceProvisioningErrors": []
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  classification               : null
  createdDateTime              : 2024-01-10T11:36:31Z
  creationOptions              : []
  deletedDateTime              : null
  description                  : This group is for all developers in the company.
  displayName                  : Developers
  expirationDateTime           : null
  groupTypes                   : ["Unified"]
  id                           : f7bce6b2-c017-4a00-ba0c-fbbe458364aa
  isAssignableToRole           : null
  mail                         : dev@contoso.com
  mailEnabled                  : true
  mailNickname                 : devs
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
  proxyAddresses               : ["SMTP:devs@contoso.com"]
  renewedDateTime              : 2024-01-10T11:36:31Z
  resourceBehaviorOptions      : []
  resourceProvisioningOptions  : []
  securityEnabled              : true
  securityIdentifier           : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  serviceProvisioningErrors    : []
  theme                        : null
  visibility                   : Public
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,deletedDateTime,classification,createdDateTime,description,displayName,expirationDateTime,isAssignableToRole,mail,mailEnabled,mailNickname,membershipRule,membershipRuleProcessingState,onPremisesDomainName,onPremisesLastSyncDateTime,onPremisesNetBiosName,onPremisesSamAccountName,onPremisesSecurityIdentifier,onPremisesSyncEnabled,preferredDataLocation,preferredLanguage,renewedDateTime,securityEnabled,securityIdentifier,theme,visibility
  4c63e8cd-eb2b-4b0d-9251-d709cc75cf5e,,,2024-01-10T11:37:02Z,This group is for all developers in the company.,Developers,,,devs@contoso.com,1,devs,,,,,,,,,,,2024-01-10T11:37:02Z,1,EXAMPLE_SECRET_VALUE_PLACEHOLDER,,Public
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra group add --displayName "Developers" --type "microsoft365" --description "This group is for all developers in the company." --visibility "Public" --mailNickname "devs"

  Date: 1/10/2024

  ## Developers (b3fd8e8f-eced-45c7-a366-178bc5c1db37)

  Property | Value
  ---------|-------
  id | b3fd8e8f-eced-45c7-a366-178bc5c1db37
  createdDateTime | 2024-01-10T11:37:39Z
  description | This group is for all developers in the company.
  displayName | Developers
  mail | devs@contoso.com
  mailEnabled | true
  mailNickname | devs
  renewedDateTime | 2024-01-10T11:37:39Z
  securityEnabled | true
  securityIdentifier | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  visibility | Public
  ```

  </TabItem>
</Tabs>
