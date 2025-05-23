-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra m365group add

Creates a Microsoft 365 Group

## Usage

```sh
m365 entra m365group add [options]
```

## Options

```md definition-list
`-n, --displayName <displayName>`
: Display name for the Microsoft 365 Group.

`-m, --mailNickname <mailNickname>`
: Name to use in the group e-mail (part before the `@`).

`-d, --description [description]`
: Description for the Microsoft 365 Group.

`--owners [owners]`
: Comma-separated list of Microsoft 365 Group owners.

`--members [members]`
: Comma-separated list of Microsoft 365 Group members.

`--visibility [visibility]`
: Specifies the group join policy and group content visibility for groups. Allowed values: `Private`, `Public`, or `HiddenMembership`. Defaults to `Public`.

`--allowMembersToPost [allowMembersToPost]`
: Set if only group members should be able to post conversations to the group.

`--hideGroupInOutlook [hideGroupInOutlook]`
: Set to hide the group in Outlook experiences.

`--subscribeNewGroupMembers [subscribeNewGroupMembers]`
: Set to subscribe all new group members to receive group conversation emails when new messages are posted in the group.

`--welcomeEmailDisabled [welcomeEmailDisabled]`
: Set to not send welcome emails to new group members.

`-l, --logoPath [logoPath]`
: Local path to the image file to use as group logo.
```

<Global />

## Remarks

You cannot change the group type when you choose `HiddenMembership` visibility. HiddenMembership can be set only for Microsoft 365 groups, when the groups are created. It can't be updated later.

When specifying the path to the logo image you can use both relative and absolute paths. Note, that ~ in the path, will not be resolved and will most likely result in an error.
If an invalid user is provided in the comma-separated list of Owners or Members, the command operation will fail and the Microsoft 365 Group will not be created.

Group visibility options:

Value	| Description
-------|-------------
Public | Anyone can join the group without needing owner permission. Anyone can view the attributes of the group. Anyone can see the members of the group.
Private | Owner permission is needed to join the group. Anyone can view the attributes of the group. Anyone can see the members of the group.
HiddenMembership | Owner permission is needed to join the group. Guest users cannot view the attributes of the group. Non-members cannot see the members of the group. Administrators (global, company, user, and helpdesk) can view the membership of the group. The group appears in the global address book (GAL).

## Examples

Create a public Microsoft 365 Group.

```sh
m365 entra m365group add --displayName Finance --mailNickname finance
```

Create a private Microsoft 365 Group.

```sh
m365 entra m365group add --displayName Finance --mailNickname finance --visibility Private
```

Create a public Microsoft 365 Group with description and set specified users as its owners.

```sh
m365 entra m365group add --displayName Finance --description "This is the Contoso Finance Group. Please come here and check out the latest news, posts, files, and more." --mailNickname finance --owners "DebraB@contoso.onmicrosoft.com,DiegoS@contoso.onmicrosoft.com"
```

Create a public Microsoft 365 Group with description and set specified users as its members.

```sh
m365 entra m365group add --displayName Finance --description "This is the Contoso Finance Group. Please come here and check out the latest news, posts, files, and more." --mailNickname finance --members "DebraB@contoso.onmicrosoft.com,DiegoS@contoso.onmicrosoft.com"
```

Create a public Microsoft 365 Group and allow only group members to be able to post conversations to the group.

```sh
m365 entra m365group add --displayName Finance --mailNickname finance --allowMembersToPost
```

Create a public Microsoft 365 Group and hide it from the Outlook experiences (web and client).

```sh
m365 entra m365group add --displayName Finance --mailNickname finance --hideGroupInOutlook
```

Create a public Microsoft 365 Group and subscribe all new group members to receive group conversation emails when new messages are posted in the group.

```sh
m365 entra m365group add --displayName Finance --mailNickname finance --subscribeNewGroupMembers
```

Create a public Microsoft 365 Group and set to not send welcome emails to new group members.

```sh
m365 entra m365group add --displayName Finance --mailNickname finance --welcomeEmailDisabled
```

Create a public Microsoft 365 Group and set its logo.

```sh
m365 entra m365group add --displayName Finance --mailNickname finance --logoPath images/logo.png
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "43159e46-373c-4151-84bd-a8cc82cee345",
    "deletedDateTime": null,
    "classification": null,
    "createdDateTime": "2023-06-01T20:15:18Z",
    "creationOptions": [],
    "description": "This is the Contoso Finance Group. Please come here and check out the latest news, posts, files, and more.",
    "displayName": "Finance",
    "expirationDateTime": null,
    "groupTypes": [
      "Unified"
    ],
    "isAssignableToRole": null,
    "mail": "finance@contoso.onmicrosoft.com",
    "mailEnabled": true,
    "mailNickname": "finance",
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
      "SMTP:finance@contoso.onmicrosoft.com"
    ],
    "renewedDateTime": "2023-06-01T20:15:18Z",
    "resourceBehaviorOptions": [],
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
  createdDateTime              : 2023-06-01T20:16:56Z
  creationOptions              : []
  deletedDateTime              : null
  description                  : This is the Contoso Finance Group. Please come here and check out the latest news, posts, files, and more.
  displayName                  : Finance
  expirationDateTime           : null
  groupTypes                   : ["Unified"]
  id                           : 1b21f2fa-a104-45a9-b6f4-5348c2c695d5
  isAssignableToRole           : null
  mail                         : finance@contoso.onmicrosoft.com
  mailEnabled                  : true
  mailNickname                 : finance
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
  proxyAddresses               : ["SMTP:finance@contoso.onmicrosoft.com"]
  renewedDateTime              : 2023-06-01T20:16:56Z
  resourceBehaviorOptions      : []
  resourceProvisioningOptions  : []
  securityEnabled              : false
  securityIdentifier           : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  theme                        : null
  visibility                   : Public
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,createdDateTime,description,displayName,mail,mailEnabled,mailNickname,renewedDateTime,securityEnabled,securityIdentifier,visibility
  62b7b02f-ea88-4e9a-a763-410067bae20e,2023-06-01T20:17:45Z,"This is the Contoso Finance Group. Please come here and check out the latest news, posts, files, and more.",Finance,finance@contoso.onmicrosoft.com,1,finance,2023-06-01T20:17:45Z,,EXAMPLE_SECRET_VALUE_PLACEHOLDER,Public
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra m365group add --displayName "Finance" --description "This is the Contoso Finance Group. Please come here and check out the latest news, posts, files, and more." --mailNickname "finance"

  Date: 2023-06-01

  ## Finance (ff99b38f-0a4b-4fbb-a034-b86988061e6d)

  Property | Value
  ---------|-------
  id | ff99b38f-0a4b-4fbb-a034-b86988061e6d
  createdDateTime | 2023-06-01T20:18:30Z
  description | This is the Contoso Finance Group. Please come here and check out the latest news, posts, files, and more.
  displayName | Finance
  mail | finance@contoso.onmicrosoft.com
  mailEnabled | true
  mailNickname | finance
  renewedDateTime | 2023-06-01T20:18:30Z
  securityEnabled | false
  securityIdentifier | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  visibility | Public
  ```

  </TabItem>
</Tabs>
