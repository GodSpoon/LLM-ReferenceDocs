-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra user get

Gets information about the specified user

## Usage

```sh
m365 entra user get [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the user to retrieve information for. Use either `id`, `userName` or `email`, but not all.

`-n, --userName [userName]`
: The name of the user to retrieve information for. Use either `id`, `userName` or `email`, but not all.

`--email [email]`
: The email of the user to retrieve information for. Use either `id`, `userName` or `email`, but not all.

`-p, --properties [properties]`
: Comma-separated list of properties to retrieve.

`--withManager`
: Retrieve the direct manager of the user.
```

<Global />

## Remarks

You can retrieve information about a user, either by specifying that user's id, user name (`userPrincipalName`), or email (`mail`), but not all.

If the user with the specified id, user name, or email doesn't exist, you will get a `Resource 'xyz' does not exist or one of its queried reference-property objects are not present.` error.

## Examples

Get information about the user by id.

```sh
m365 entra user get --id 1caf7dcd-7e83-4c3a-94f7-932a1299c844
```

Get information about the user by user name.

```sh
m365 entra user get --userName AarifS@contoso.onmicrosoft.com
```

Get information about the user by email.

```sh
m365 entra user get --email AarifS@contoso.onmicrosoft.com
```

For the user with id _1caf7dcd-7e83-4c3a-94f7-932a1299c844_ retrieve the user name, e-mail address and full name.

```sh
m365 entra user get --id 1caf7dcd-7e83-4c3a-94f7-932a1299c844 --properties "userPrincipalName,mail,displayName"
```

Get information about the currently logged user using the Id token.

```sh
m365 entra user get --id "@meId"
```

Get information about the currently logged in user using the UserName token.

```sh
m365 entra user get --userName "@meUserName"
```

Get information about a user with the manager's details.

```sh
m365 entra user get --userName AarifS@contoso.onmicrosoft.com --withManager
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "businessPhones": ["+32499-99-99-99"],
    "displayName": "John Doe",
    "givenName": "John",
    "jobTitle": "Sales Manager",
    "mail": "john.doe@contoso.com",
    "mobilePhone": "+32499-99-99-99",
    "officeLocation": "Vosselaar",
    "preferredLanguage": "nl-BE",
    "surname": "Doe",
    "userPrincipalName": "john.doe@contoso.com",
    "id": "990e2425-f595-43bc-85ed-b89a44093793"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  businessPhones   : ["+32499-99-99-99"]
  displayName      : John Doe
  givenName        : John
  id               : 990e2425-f595-43bc-85ed-b89a44093793
  jobTitle         : Sales Manager
  mail             : john.doe@contoso.com
  mobilePhone      : +32499-99-99-99
  officeLocation   : Vosselaar
  preferredLanguage: nl-BE
  surname          : Doe
  userPrincipalName: john.doe@contoso.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  displayName,givenName,jobTitle,mail,mobilePhone,officeLocation,preferredLanguage,surname,userPrincipalName,id
  John Doe,John,Sales Manager,john.doe@contoso.com,+32499-99-99-99,Vosselaar,nl-BE,Doe,john.doe@contoso.com,990e2425-f595-43bc-85ed-b89a44093793
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra user get --userName "john.doe@contoso.com"

  Date: 16/02/2023

  ## John Doe (990e2425-f595-43bc-85ed-b89a44093793)

  Property | Value
  ---------|-------
  displayName | John Doe
  givenName | John
  jobTitle | Sales Manager
  mail | john.doe@contoso.com
  mobilePhone | +32499-99-99-99
  officeLocation | Vosselaar
  preferredLanguage | nl-BE
  surname | Doe
  userPrincipalName | john.doe@contoso.com
  id | 990e2425-f595-43bc-85ed-b89a44093793
  ```

  </TabItem>
</Tabs>

### `withManager` response

When we make use of the option `withManager` the response will differ. 

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "businessPhones": ["+32499-99-99-99"],
    "displayName": "John Doe",
    "givenName": "John",
    "jobTitle": "Sales Manager",
    "mail": "john.doe@contoso.com",
    "mobilePhone": "+32499-99-99-99",
    "officeLocation": "Vosselaar",
    "preferredLanguage": "nl-BE",
    "surname": "Doe",
    "userPrincipalName": "john.doe@contoso.com",
    "id": "990e2425-f595-43bc-85ed-b89a44093793",
    "manager": {
      "displayName": "Jane Doe",
      "userPrincipalName": "jane.doe@contoso.com",
      "id": "eb77fbcf-6fe8-458b-985d-1747284793bc",
      "mail": "jane.doe@contoso.com"
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  businessPhones   : ["+32499-99-99-99"]
  displayName      : John Doe
  givenName        : John
  id               : 990e2425-f595-43bc-85ed-b89a44093793
  jobTitle         : Sales Manager
  mail             : john.doe@contoso.com
  manager          : {"displayName":"Jane Doe","userPrincipalName":"jane.doe@contoso.com","id":"eb77fbcf-6fe8-458b-985d-1747284793bc","mail":"jane.doe@contoso.com"}
  mobilePhone      : +32499-99-99-99
  officeLocation   : Vosselaar
  preferredLanguage: nl-BE
  surname          : Doe
  userPrincipalName: john.doe@contoso.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  displayName,givenName,jobTitle,mail,mobilePhone,officeLocation,preferredLanguage,surname,userPrincipalName,id
  John Doe,John,Sales Manager,john.doe@contoso.com,+32499-99-99-99,Vosselaar,nl-BE,Doe,john.doe@contoso.com,990e2425-f595-43bc-85ed-b89a44093793
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra user get --userName "john.doe@contoso.com" --withManager

  Date: 16/02/2023

  ## John Doe (990e2425-f595-43bc-85ed-b89a44093793)

  Property | Value
  ---------|-------
  displayName | John Doe
  givenName | John
  jobTitle | Sales Manager
  mail | john.doe@contoso.com
  mobilePhone | +32499-99-99-99
  officeLocation | Vosselaar
  preferredLanguage | nl-BE
  surname | Doe
  userPrincipalName | john.doe@contoso.com
  id | 990e2425-f595-43bc-85ed-b89a44093793
  ```

  </TabItem>
</Tabs>

## More information

- Microsoft Graph User properties: [https://developer.microsoft.com/en-us/graph/docs/api-reference/v1.0/resources/user#properties](https://developer.microsoft.com/en-us/graph/docs/api-reference/v1.0/resources/user#properties)
