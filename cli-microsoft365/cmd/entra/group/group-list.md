-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra group list

Lists Entra groups

## Usage

```sh
m365 entra group list [options]
```

## Options

```md definition-list
`--type [type]`
: Filter the results to only groups of a given type. Allowed values: `microsoft365`, `security`, `distribution`, `mailEnabledSecurity`. By default, all groups are listed.

`-p, --properties [properties]`
: Comma-separated list of properties to retrieve.
```

<Global />

## Remarks

Using the `--properties` option, you can specify a comma-separated list of group properties to retrieve from the Microsoft Graph. If you don't specify any properties, the command will output the default properties returned by Graph.

## Examples

Lists all groups defined in Entra ID.

```sh
m365 entra group list
```

List all security groups defined in Entra ID with specified properties.

```sh
m365 entra group list --type security --properties "mail,displayName"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "04e9637c-79d4-4c45-80fb-56fe35f84cf2",
      "deletedDateTime": null,
      "classification": null,
      "createdDateTime": "2019-04-22T09:24:11Z",
      "creationOptions": [
        "HubSiteId:00000000-0000-0000-0000-000000000000",
        "ProvisionGroupHomepage"
      ],
      "description": null,
      "displayName": "Human Resources",
      "expirationDateTime": null,
      "groupTypes": [
        "Unified"
      ],
      "isAssignableToRole": null,
      "mail": "PNP-Contosohr@contoso.onmicrosoft.com",
      "mailEnabled": true,
      "mailNickname": "PNP-Contosohr",
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
        "SMTP:PNP-Contosohr@contoso.onmicrosoft.com",
        "SPO:EXAMPLE_SECRET_VALUE_PLACEHOLDER@EXAMPLE_SECRET_VALUE_PLACEHOLDER"
      ],
      "renewedDateTime": "2019-04-22T09:24:11Z",
      "resourceBehaviorOptions": [],
      "resourceProvisioningOptions": [],
      "securityEnabled": false,
      "securityIdentifier": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "theme": null,
      "visibility": "Private",
      "onPremisesProvisioningErrors": []
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    displayName                     groupType
  ------------------------------------  ------------------------------  ---------------------
  04e9637c-79d4-4c45-80fb-56fe35f84cf2  Human Resources                 Microsoft 365
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,createdDateTime,displayName,mail,mailEnabled,mailNickname,renewedDateTime,securityEnabled,securityIdentifier,visibility
  04e9637c-79d4-4c45-80fb-56fe35f84cf2,2019-04-22T09:24:11Z,Human Resources,PNP-Contosohr@contoso.onmicrosoft.com,1,PNP-Contosohr,2019-04-22T09:24:11Z,,EXAMPLE_SECRET_VALUE_PLACEHOLDER,Private
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra group list

  Date: 2023-06-01

  ## Human Resources (04e9637c-79d4-4c45-80fb-56fe35f84cf2)

  Property | Value
  ---------|-------
  id | 04e9637c-79d4-4c45-80fb-56fe35f84cf2
  createdDateTime | 2019-04-22T09:24:11Z
  displayName | Human Resources
  mail | PNP-Contosohr@contoso.onmicrosoft.com
  mailEnabled | true
  mailNickname | PNP-Contosohr
  renewedDateTime | 2019-04-22T09:24:11Z
  securityEnabled | false
  securityIdentifier | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  visibility | Private
  ```

  </TabItem>
</Tabs>
