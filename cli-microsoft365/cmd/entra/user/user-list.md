-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra user list

Lists users matching specified criteria

## Usage

```sh
m365 entra user list [options]
```

## Options

```md definition-list
`--type [type]`
: Filter the results to only users of a given type: `Member` or `Guest`. By default, all users are listed.

`-p, --properties [properties]`
: Comma-separated list of properties to retrieve.
```

<Global />

## Remarks

Using the `--properties` option, you can specify a comma-separated list of user properties to retrieve from the Microsoft Graph. If you don't specify any properties, the command will output the default properties returned by Graph.  

When the `properties` option includes values with a `/`, for example: `manager/displayName`, an additional `$expand` query parameter will be included on `manager`.

To filter the list of users, include additional options that match the user property that you want to filter with. For example `--displayName Patt` will return all users whose `displayName` starts with `Patt`. Multiple filters will be combined using the `and` operator.

Certain properties cannot be returned within a user collection. The following properties are only supported when retrieving an single user using: `aboutMe`, `birthday`, `hireDate`, `interests`, `mySite`, `pastProjects`, `preferredName`, `responsibilities`, `schools`, `skills`, `mailboxSettings`.

## Examples

List all users in the tenant.

```sh
m365 entra user list
```

List all guest users in the tenant.

```sh
m365 entra user list --type Guest
```

List all users in the tenant. For each one return the display name and e-mail address.

```sh
m365 entra user list --properties "displayName,mail"
```

Show users whose display name starts with _Patt_.

```sh
m365 entra user list --displayName Patt
```

Show all account managers whose display name starts with _Patt_.

```sh
m365 entra user list --displayName Patt --jobTitle 'Account manager'
```

List users from the tenant. For each one return the display name, e-mail address, and manager information.

```sh
m365 entra user list --properties "displayName,mail,manager/*"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "businessPhones": [
        "+32 456 789 123"
      ],
      "displayName": "John Doe",
      "givenName": "John",
      "jobTitle": "Sales Manager",
      "mail": "John@contoso.onmicrosoft.com",
      "mobilePhone": "+32 456 789 123",
      "officeLocation": "Antwerp",
      "preferredLanguage": "nl-BE",
      "surname": "Doe",
      "userPrincipalName": "John@contoso.onmicrosoft.com",
      "id": "ef0d4f29-e359-4443-a15d-bc3dccc8143f"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    displayName  mail                          userPrincipalName
  ------------------------------------  -----------  ----------------------------  ----------------------------
  ef0d4f29-e359-4443-a15d-bc3dccc8143f  John Doe     John@contoso.onmicrosoft.com  John@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  displayName,givenName,jobTitle,mail,mobilePhone,officeLocation,preferredLanguage,surname,userPrincipalName,id
  John Doe,John,Sales Manager,John@contoso.onmicrosoft.com,+32 456 789 123,Antwerp,nl-BE,Doe,John@contoso.onmicrosoft.com,ef0d4f29-e359-4443-a15d-bc3dccc8143f
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra user list

  Date: 2023-06-02

  ## John Doe (1f5595b2-aa07-445d-9801-a45ea18160b2)

  Property | Value
  ---------|-------
  displayName | John Doe
  givenName | John
  jobTitle | Sales Manager
  mail | John@contoso.onmicrosoft.com
  mobilePhone | +32 456 789 123
  officeLocation | Antwerp
  preferredLanguage | nl-BE
  surname | Doe
  userPrincipalName | John@contoso.onmicrosoft.com  
  id | 1f5595b2-aa07-445d-9801-a45ea18160b2
  ```

  </TabItem>
</Tabs>

## More information

- Microsoft Graph User properties: [https://learn.microsoft.com/graph/api/resources/user?view=graph-rest-1.0#properties](https://learn.microsoft.com/graph/api/resources/user?view=graph-rest-1.0#properties)
