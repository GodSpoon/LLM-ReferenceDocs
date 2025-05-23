-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra m365group recyclebinitem list

Lists Groups from the recycle bin in the current tenant

## Usage

```sh
m365 entra m365group recyclebinitem list [options]
```

## Options

```md definition-list
`-d, --groupName [groupName]`
: Lists groups with DisplayName starting with the specified value

`-m, --groupMailNickname [groupMailNickname]`
: Lists groups with MailNickname starting with the specified value
```

<Global />

## Examples

List all deleted Microsoft 365 Groups in the tenant

```sh
m365 entra m365group recyclebinitem list
```

List deleted Microsoft 365 Groups with display name starting with _Project_

```sh
m365 entra m365group recyclebinitem list --groupName Project
```

List deleted Microsoft 365 Groups mail nick name starting with _team_

```sh
m365 entra m365group recyclebinitem list --groupMailNickname team
```

List deleted Microsoft 365 Groups mail nick name starting with _team_ and with display name starting with _Project_

```sh
m365 entra m365group recyclebinitem list --groupMailNickname team --groupName Project
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "1b21f2fa-a104-45a9-b6f4-5348c2c695d5",
      "deletedDateTime": "2023-06-01T20:17:34Z",
      "classification": null,
      "createdDateTime": "2023-06-01T20:16:56Z",
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
      "renewedDateTime": "2023-06-01T20:16:56Z",
      "resourceBehaviorOptions": [],
      "resourceProvisioningOptions": [],
      "securityEnabled": false,
      "securityIdentifier": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "theme": null,
      "visibility": "Public",
      "onPremisesProvisioningErrors": []
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    displayName  mailNickname
  ------------------------------------  -----------  ------------
  1b21f2fa-a104-45a9-b6f4-5348c2c695d5  Finance      finance
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,deletedDateTime,createdDateTime,description,displayName,mail,mailEnabled,mailNickname,renewedDateTime,securityEnabled,securityIdentifier,visibility
  1b21f2fa-a104-45a9-b6f4-5348c2c695d5,2023-06-01T20:17:34Z,2023-06-01T20:16:56Z,"This is the Contoso Finance Group. Please come here and check out the latest news, posts, files, and more.",Finance,finance@contoso.onmicrosoft.com,1,finance,2023-06-01T20:16:56Z,,EXAMPLE_SECRET_VALUE_PLACEHOLDER,Public
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra m365group recyclebinitem list

  Date: 2023-06-02

  ## Finance (1b21f2fa-a104-45a9-b6f4-5348c2c695d5)

  Property | Value
  ---------|-------
  id | 1b21f2fa-a104-45a9-b6f4-5348c2c695d5
  deletedDateTime | 2023-06-01T20:17:34Z
  createdDateTime | 2023-06-01T20:16:56Z
  description | This is the Contoso Finance Group. Please come here and check out the latest news, posts, files, and more.
  displayName | Finance
  mail | finance@contoso.onmicrosoft.com
  mailEnabled | true
  mailNickname | finance
  renewedDateTime | 2023-06-01T20:16:56Z
  securityEnabled | false
  securityIdentifier | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  visibility | Public
  ```

  </TabItem>
</Tabs>
