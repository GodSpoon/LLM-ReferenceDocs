-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra administrativeunit member get

Retrieves info about a specific member of an administrative unit

## Usage

```sh
m365 entra administrativeunit member get [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The id of a member to be retrieved.

`-u, --administrativeUnitId [administrativeUnitId]`
: The id of the administrative unit. Specify either `administrativeUnitId` or `administrativeUnitName`.

`-n, --administrativeUnitName [administrativeUnitName]`
: The name of the administrative unit. Specify either `administrativeUnitId` or `administrativeUnitName`.

`-p, --properties [properties]`
: Comma-separated list of properties to retrieve.
```

<Global />

## Remarks

To get the member of a hidden membership in an administrative unit, the `Member.Read.Hidden` permission is required.

When the `properties` option includes values with a `/`, for example: `manager/displayName`, an additional `$expand` query parameter will be included on manager.

## Examples

Get information about a member specified by id from an administrative unit specified by id

```sh
m365 entra administrativeunit member get --id 64131a70-beb9-4ccb-b590-4401e58446ec --administrativeUnitId 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7 
```

Get information about a member specified by id from an administrative unit specified by name

```sh
m365 entra administrativeunit member get --id 64131a70-beb9-4ccb-b590-4401e58446ec --administrativeUnitName 'Marketing Division' 
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
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
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  businessPhones   : ["+20 255501070"]
  displayName      : Pradeep Gupta
  givenName        : Pradeep
  id               : 64131a70-beb9-4ccb-b590-4401e58446ec
  jobTitle         : Accountant
  mail             : PradeepG@contoso.com
  mobilePhone      : null
  officeLocation   : 98/2202
  preferredLanguage: en-US
  surname          : Gupta
  type             : user
  userPrincipalName: PradeepG@contoso.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,givenName,jobTitle,mail,officeLocation,preferredLanguage,surname,userPrincipalName,type
  64131a70-beb9-4ccb-b590-4401e58446ec,Pradeep Gupta,Pradeep,Accountant,PradeepG@contoso.com,98/2202,en-US,Gupta,PradeepG@contoso.com,user
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Date: 11/10/2023

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
  ```

  </TabItem>
</Tabs>

## More information

- Administrative units: https://learn.microsoft.com/entra/identity/role-based-access-control/administrative-units
