-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra m365group user list

Lists users for the specified Microsoft 365 group

## Usage

```sh
m365 entra m365group user list [options]
```

## Options

```md definition-list
`-i, --groupId [groupId]`
: The ID of the Microsoft 365 group. Specify `groupId` or `groupDisplayName` but not both.

`-n, --groupDisplayName [groupDisplayName]`
: The display name of the Microsoft 365 group. Specify `groupId` or `groupDisplayName` but not both.

`-r, --role [role]`
: Filter the results to only users with the given role. Allowed values: `Owner`, `Member`.

`-p, --properties [properties]`
: Comma-separated list of properties to retrieve.

`-f, --filter [filter]`
: OData filter to use to query the list of users with.
```

<Global />

## Remarks

When the `properties` option includes values with a `/`, for example: `manager/displayName`, an additional `$expand` query parameter will be included on `manager`.

## Examples

List all users and their role from Microsoft 365 group specified by ID.

```sh
m365 entra m365group user list --groupId '00000000-0000-0000-0000-000000000000'
```

List all owners from Microsoft 365 group specified by display name.

```sh
m365 entra m365group user list --groupDisplayName Developers --role Owner
```

List specific properties for all group users from a group specified by ID.

```sh
m365 entra m365group user list --groupId 03cba9da-3974-46c1-afaf-79caa2e45bbe --properties "id,jobTitle,companyName,accountEnabled"
```

List all group members that are guest users.

```sh
m365 entra m365group user list --groupDisplayName Developers --filter "userType eq 'Guest'"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "da52218e-4822-4ac6-b41d-255e2059655e",
      "displayName": "Adele Vance",
      "userPrincipalName": "AdeleV@contoso.OnMicrosoft.com",
      "givenName": "Adele",
      "surname": "Vance",
      "roles": [
        "Owner",
        "Member"
      ]
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    displayName           userPrincipalName                     userType      roles
  ------------------------------------  --------------------  ------------------------------------  --------      --------
  da52218e-4822-4ac6-b41d-255e2059655e  Adele Vance           AdeleV@contoso.OnMicrosoft.com        Owner,Member  Owner,Member
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,userPrincipalName,givenName,surname,userType
  da52218e-4822-4ac6-b41d-255e2059655e,Adele Vance,AdeleV@contoso.OnMicrosoft.com,Adele,Vance,Member
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra m365group user list --groupId "1deaa428-8dde-4043-b028-5492226d6114"

  Date: 2023-06-02

  ## Adele Vance (da52218e-4822-4ac6-b41d-255e2059655e)

  Property | Value
  ---------|-------
  id | da52218e-4822-4ac6-b41d-255e2059655e
  displayName | Adele Vance
  givenName | Adele
  surname | Vance
  userPrincipalName | AdeleV@contoso.OnMicrosoft.com
  userType | Member
  ```

  </TabItem>
</Tabs>
