-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra m365group list

Lists Microsoft 365 Groups in the current tenant

## Usage

```sh
m365 entra m365group list [options]
```

## Options

```md definition-list
`-d, --displayName [displayName]`
: Retrieve only groups with displayName starting with the specified value.

`-m, --mailNickname [displayName]`
: Retrieve only groups with mailNickname starting with the specified value.

`--includeSiteUrl`
: (deprecated. Use option `withSiteUrl` instead) Set to retrieve the site URL for each group.

`--withSiteUrl`
: Set to retrieve the site URL for each group.

`--orphaned`
: Set to only retrieve groups without owners.
```

<Global />

## Remarks

Using the `--withSiteUrl` option, you can retrieve the URL of the site associated with the particular Microsoft 365 Group. If you however retrieve too many groups and will try to get their site URLs, you will most likely get an error as the command will get throttled, issuing too many requests, too frequently. If you get an error, consider narrowing down the result set using the `--displayName` and `--mailNickname` filters.

Using the `--orphaned` option, you can retrieve Microsoft 365 Groups without owners.

## Examples

List all Microsoft 365 Groups in the tenant.

```sh
m365 entra m365group list
```

List Microsoft 365 Groups with display name starting with _Project_.

```sh
m365 entra m365group list --displayName Project
```

List Microsoft 365 Groups mail nick name starting with _team_.

```sh
m365 entra m365group list --mailNickname team
```

List Microsoft 365 Groups with display name starting with _Project_ including the URL of the corresponding SharePoint site.

```sh
m365 entra m365group list --displayName Project --withSiteUrl
```

List Microsoft 365 Groups without owners.

```sh
m365 entra m365group list --orphaned
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "0bc3d172-dfab-463f-b79a-ed8ec5d3d455",
      "deletedDateTime": null,
      "classification": null,
      "createdDateTime": "2022-12-12T12:51:12Z",
      "creationOptions": [
        "YammerProvisioning"
      ],
      "description": "Share what's on your mind and get important announcements from Patti and the rest of the Leadership Team.",
      "displayName": "Leadership",
      "expirationDateTime": null,
      "groupTypes": [
        "Unified"
      ],
      "isAssignableToRole": null,
      "mail": "leadership@contoso.onmicrosoft.com",
      "mailEnabled": true,
      "mailNickname": "leadership",
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
        "SMTP:leadership@contoso.onmicrosoft.com"
      ],
      "renewedDateTime": "2022-12-12T12:51:12Z",
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
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    displayName  mailNickname
  ------------------------------------  -----------  ------------
  0bc3d172-dfab-463f-b79a-ed8ec5d3d455  Leadership   leadership  
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,createdDateTime,description,displayName,mail,mailEnabled,mailNickname,renewedDateTime,securityEnabled,securityIdentifier,visibility
  0bc3d172-dfab-463f-b79a-ed8ec5d3d455,2022-12-12T12:51:12Z,Share what's on your mind and get important announcements from Patti and the rest of the Leadership Team.,Leadership,leadership@contoso.onmicrosoft.com,1,leadership,2022-12-12T12:51:12Z,,EXAMPLE_SECRET_VALUE_PLACEHOLDER,Public
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra m365group list

  Date: 2023-06-01

  ## Leadership (0bc3d172-dfab-463f-b79a-ed8ec5d3d455)

  Property | Value
  ---------|-------
  id | 0bc3d172-dfab-463f-b79a-ed8ec5d3d455
  createdDateTime | 2022-12-12T12:51:12Z
  description | Share what's on your mind and get important announcements from Patti and the rest of the Leadership Team.
  displayName | Leadership
  mail | leadership@contoso.onmicrosoft.com
  mailEnabled | true
  mailNickname | leadership
  renewedDateTime | 2022-12-12T12:51:12Z
  securityEnabled | false
  securityIdentifier | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  visibility | Public
  ```

  </TabItem>
</Tabs>
