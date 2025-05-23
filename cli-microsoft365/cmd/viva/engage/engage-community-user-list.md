-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage community user list

Lists all users within a specified Microsoft 365 Viva Engage community

## Usage

```sh
m365 viva engage community user list [options]
```

## Options

```md definition-list
`--communityId [communityId]`
: The ID of the Viva Engage community. Specify `communityId`, `communityDisplayName` or `entraGroupId`.

`-n, --communityDisplayName [communityDisplayName]`
: The display name of the Viva Engage community. Specify `communityId`, `communityDisplayName` or `entraGroupId`.

`--entraGroupId [entraGroupId]`
: The ID of the Microsoft 365 group. Specify `communityId`, `communityDisplayName` or `entraGroupId`.

`-r, --role [role]`
: Filter the results to only users with the given role: `Admin`, `Member`.
```

<Global />

## Examples

List all users from a community specified by ID.

```sh
m365 viva engage community user list --communityId EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

List all admins from a community specified by display name.

```sh
m365 viva engage community user list --communityDisplayName "All company" --role Admin
```

List all members from a community specified by group ID.

```sh
m365 viva engage community user list --entraGroupId b6c35b51-ebca-445c-885a-63a67d24cb53 --role Member
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "da634de7-d23c-4419-ab83-fcd395b4ebd0",
      "businessPhones": [
        "123-555-1215"
      ],
      "displayName": "Anton Johansen",
      "givenName": "Anton",
      "jobTitle": "IT Manager",
      "mail": null,
      "mobilePhone": "123-555-6645",
      "officeLocation": "123455",
      "preferredLanguage": null,
      "surname": "Johansen",
      "userPrincipalName": "Anton.Johansen@contoso.onmicrosoft.com",
      "roles": [
        "Admin"
      ]
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    displayName       userPrincipalName                          roles
  ------------------------------------  ----------------  -----------------------------------------  ------
  da634de7-d23c-4419-ab83-fcd395b4ebd0  Anton Johansen    Anton.Johansen@contoso.onmicrosoft.com    Admin
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,givenName,jobTitle,mail,mobilePhone,officeLocation,preferredLanguage,surname,userPrincipalName
  da634de7-d23c-4419-ab83-fcd395b4ebd0,Anton Johansen,Anton,IT Manager,,123-555-6645,123455,,Johansen,Anton.Johansen@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # viva engage community user list --entraGroupId "b6c35b51-ebca-445c-885a-63a67d24cb53"

  Date: 19/9/2024

  ## Anton Johansen (da634de7-d23c-4419-ab83-fcd395b4ebd0)

  Property | Value
  ---------|-------
  id | da634de7-d23c-4419-ab83-fcd395b4ebd0
  displayName | Anton Johansen
  givenName | Anton
  jobTitle | IT Manager
  mobilePhone | 123-555-6645
  officeLocation | 123455
  surname | Johansen
  userPrincipalName | Anton.Johansen@contoso.onmicrosoft.com
  ```

  </TabItem>
</Tabs>
