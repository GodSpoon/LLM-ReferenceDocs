-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams team add

Adds a new Microsoft Teams team

## Usage

```sh
m365 teams team add [options]
```

## Options

```md definition-list
`-n, --name [name]`
: Display name for the Microsoft Teams team. Required if `template` not supplied.

`-d, --description [description]`
: Description for the Microsoft Teams team. Required if `template` not supplied.

`--template [template]`
: Template to use to create the team. If `name` or `description` are supplied, these take precedence over the template values.

`--wait`
: Wait for the team to be provisioned before completing the command.

`--ownerUserNames [ownerUserNames]`
: User principal names of the owners to set, separated by a `,`. Specify either `ownerUserNames`, `ownerIds` or `ownerEmails`.

`--ownerIds [ownerIds]`
: Ids of the owners to set, separated by a `,`. Specify either `ownerUserNames`, `ownerIds` or `ownerEmails`.

`--ownerEmails [ownerEmails]`
: Email addresses of the owners to set, separated by a `,`. Specify either `ownerUserNames`, `ownerIds` or `ownerEmails`.

`--memberUserNames [memberUserNames]`
: User principal names of the members to set, separated by a `,`. Specify either `memberUserNames`, `memberIds` or `memberEmails`.

`--memberIds [memberIds]`
: Ids of the members to set, separated by a `,`. Specify either `memberUserNames`, `memberIds` or `memberEmails`.

`--memberEmails [memberEmails]`
: Email addresses of the members to set, separated by a `,`. Specify either `memberUserNames`, `memberIds` or `memberEmails`.
```

<Global />

## Remarks

If you want to add a Team to an existing Microsoft 365 Group use the [entra m365group teamify](../../entra/m365group/m365group-teamify.mdx) command instead.

This command will return different responses based on the presence of the `--wait` option. If present, the command will return a `group` resource in the response. If not present, the command will return a `teamsAsyncOperation` resource in the response.

:::info

When using application permissions, you have to specify atleast one owner using the `--ownerUserNames`, `--ownerIds` or `--ownerEmails` options. This will also result in the `--wait` option being enforced if more than one owner is being set.

:::

## Examples

Add a new Microsoft Teams team with a specific owner.

```sh
m365 teams team add --name "Architecture" --description "Architecture Discussion" --ownerIds "d7a3d3e5-3e3d-4f3e-8a3d-3e3d3f3e3d3f"
```

Add a new Microsoft Teams team using a template from a file.

```sh
m365 teams team add --name "Architecture" --description "Architecture Discussion" --template @template.json
```

Add a new Microsoft Teams team using a template and wait for the team to be provisioned with multiple members.

```sh
m365 teams team add --name "Architecture" --description "Architecture Discussion" --template @template.json --wait --memberUserNames "john@contoso.com,doe@contoso.com"
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ``` json
  {
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#teams('a40210cd-0060-4b91-aaa1-a44e0853d979')/operations/$entity",
    "id": "d708ecb3-3325-4f6e-a0f7-2f982901b856",
    "operationType": "createTeam",
    "createdDateTime": "2022-10-31T12:50:44.0819314Z",
    "status": "notStarted",
    "lastActionDateTime": "2022-10-31T12:50:44.0819314Z",
    "attemptsCount": 1,
    "targetResourceId": "a40210cd-0060-4b91-aaa1-a44e0853d979",
    "targetResourceLocation": "/teams('a40210cd-0060-4b91-aaa1-a44e0853d979')",
    "Value": "{\"apps\":[],\"channels\":[],\"WorkflowId\":\"EXAMPLE_SECRET_VALUE_PLACEHOLDER\"}",
    "error": null
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ``` text
  @odata.context        : https://graph.microsoft.com/v1.0/$metadata#teams('6d9e3e6b-88a2-492b-985a-477bc760bd6b')/operations/$entity
  Value                 : {"apps":[],"channels":[],"WorkflowId":"EXAMPLE_SECRET_VALUE_PLACEHOLDER"}
  attemptsCount         : 1
  createdDateTime       : 2022-10-31T12:51:22.8337964Z
  error                 : null
  id                    : 6af66f9c-f73b-42a6-87b8-216dee12f40b
  lastActionDateTime    : 2022-10-31T12:51:22.8337964Z
  operationType         : createTeam
  status                : notStarted
  targetResourceId      : 6d9e3e6b-88a2-492b-985a-477bc760bd6b
  targetResourceLocation: /teams('6d9e3e6b-88a2-492b-985a-477bc760bd6b')
  ```

  </TabItem>
  <TabItem value="CSV">

  ``` text
  @odata.context,id,operationType,createdDateTime,status,lastActionDateTime,attemptsCount,targetResourceId,targetResourceLocation,Value,error
  https://graph.microsoft.com/v1.0/$metadata#teams('40d5758d-5ad9-406d-88ab-0a78992ffbab')/operations/$entity,65778567-595d-4543-bb21-f8d62c678c8e,createTeam,2022-10-31T12:57:42.4956529Z,notStarted,2022-10-31T12:57:42.4956529Z,1,40d5758d-5ad9-406d-88ab-0a78992ffbab,/teams('40d5758d-5ad9-406d-88ab-0a78992ffbab'),"{""apps"":[],""channels"":[],""WorkflowId"":""EXAMPLE_SECRET_VALUE_PLACEHOLDER""}",
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams team add --name "Architecture" --description "Architecture Discussion"

  Date: 1/3/2023

  ## undefined (d708ecb3-3325-4f6e-a0f7-2f982901b856)

  Property | Value
  ---------|-------
  @odata.context | https://graph.microsoft.com/v1.0/$metadata#teams('a40210cd-0060-4b91-aaa1-a44e0853d979')/operations/$entity
  id | d708ecb3-3325-4f6e-a0f7-2f982901b856
  operationType | createTeam
  createdDateTime | 2022-10-31T12:50:44.0819314Z
  status | notStarted
  lastActionDateTime | 2022-10-31T12:50:44.0819314Z
  attemptsCount | 1
  targetResourceId | a40210cd-0060-4b91-aaa1-a44e0853d979
  targetResourceLocation | /teams('a40210cd-0060-4b91-aaa1-a44e0853d979')
  error | null
  ```

  </TabItem>
</Tabs>

### `wait` response

When we make use of the option `wait` the response will differ. 

<Tabs>
  <TabItem value="JSON">

  ``` json
  {
    "id": "d592059d-100f-48c6-8a91-b68eec00ecec",
    "deletedDateTime": null,
    "classification": null,
    "createdDateTime": "2022-11-04T12:46:47Z",
    "creationOptions": [
      "Team",
      "ExchangeProvisioningFlags:3552"
    ],
    "description": "Architecture Discussion",
    "displayName": "Architecture",
    "expirationDateTime": null,
    "groupTypes": [
      "Unified"
    ],
    "isAssignableToRole": null,
    "mail": "Architecture@contoso.onmicrosoft.com",
    "mailEnabled": true,
    "mailNickname": "Architecture",
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
      "SMTP:Architecture@contoso.onmicrosoft.com"
    ],
    "renewedDateTime": "2022-11-04T12:46:47Z",
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
    "onPremisesProvisioningErrors": []
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ``` text
  classification               : null
  createdDateTime              : 2022-11-04T12:47:57Z
  creationOptions              : ["Team","ExchangeProvisioningFlags:3552"]
  deletedDateTime              : null
  description                  : Architecture Discussion
  displayName                  : Architecture
  expirationDateTime           : null
  groupTypes                   : ["Unified"]
  id                           : 29c242bb-a96f-470a-b280-d63154f5446f
  isAssignableToRole           : null
  mail                         : Architecture@contoso.onmicrosoft.com
  mailEnabled                  : true
  mailNickname                 : Architecture
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
  proxyAddresses               : ["SMTP:Architecture@contoso.onmicrosoft.com"]
  renewedDateTime              : 2022-11-04T12:47:57Z
  resourceBehaviorOptions      : ["HideGroupInOutlook","EXAMPLE_SECRET_VALUE_PLACEHOLDER","WelcomeEmailDisabled"]
  resourceProvisioningOptions  : ["Team"]
  securityEnabled              : false
  securityIdentifier           : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  theme                        : null
  visibility                   : Public
  ```

  </TabItem>
  <TabItem value="CSV">

  ``` text
  id,deletedDateTime,classification,createdDateTime,creationOptions,description,displayName,expirationDateTime,groupTypes,isAssignableToRole,mail,mailEnabled,mailNickname,membershipRule,membershipRuleProcessingState,onPremisesDomainName,onPremisesLastSyncDateTime,onPremisesNetBiosName,onPremisesSamAccountName,onPremisesSecurityIdentifier,onPremisesSyncEnabled,preferredDataLocation,preferredLanguage,proxyAddresses,renewedDateTime,resourceBehaviorOptions,resourceProvisioningOptions,securityEnabled,securityIdentifier,theme,visibility,onPremisesProvisioningErrors
  bb57868a-e82e-470b-85aa-8a86942a5bf8,,,2022-11-04T12:51:35Z,"[""Team"",""ExchangeProvisioningFlags:3552""]",Architecture Discussion,Architecture,,"[""Unified""]",,Architecture@contoso.onmicrosoft.com,1,TeamName,,,,,,,,,,,"[""SMTP:Architecture@contoso.onmicrosoft.com""]",2022-11-04T12:51:35Z,"[""HideGroupInOutlook"",""EXAMPLE_SECRET_VALUE_PLACEHOLDER"",""WelcomeEmailDisabled""]","[""Team""]",,EXAMPLE_SECRET_VALUE_PLACEHOLDER,,Public,[]
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams team add --name "Architecture" --description "Architecture Discussion" --wait "true"

  Date: 1/3/2023

  ## Architecture (d592059d-100f-48c6-8a91-b68eec00ecec)

  Property | Value
  ---------|-------
  id | d592059d-100f-48c6-8a91-b68eec00ecec
  deletedDateTime | null
  classification | null
  createdDateTime | 2022-11-04T12:46:47Z
  description | Architecture Discussion
  displayName | Architecture
  expirationDateTime | null
  isAssignableToRole | null
  mail | Architecture@contoso.onmicrosoft.com
  mailEnabled | true
  mailNickname | Architecture
  membershipRule | null
  membershipRuleProcessingState | null
  onPremisesDomainName | null
  onPremisesLastSyncDateTime | null
  onPremisesNetBiosName | null
  onPremisesSamAccountName | null
  onPremisesSecurityIdentifier | null
  onPremisesSyncEnabled | null
  preferredDataLocation | null
  preferredLanguage | null
  renewedDateTime | 2022-11-04T12:46:47Z
  securityEnabled | false
  securityIdentifier | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  theme | null
  visibility | Public
  ```

  </TabItem>
</Tabs>

## More information

- Get started with Teams templates: [https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates)
- group resource type: [https://docs.microsoft.com/graph/api/resources/group?view=graph-rest-1.0](https://docs.microsoft.com/graph/api/resources/group?view=graph-rest-1.0)
- teamsAsyncOperation resource type: [https://docs.microsoft.com/graph/api/resources/teamsasyncoperation?view=graph-rest-1.0](https://docs.microsoft.com/graph/api/resources/teamsasyncoperation?view=graph-rest-1.0)
