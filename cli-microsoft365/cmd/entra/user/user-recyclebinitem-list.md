-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra user recyclebinitem list

Lists users from the recycle bin in the current tenant

## Usage

```sh
m365 entra user recyclebinitem list [options]
```

## Options

<Global />

## Examples

List all removed users.

```sh
m365 entra user recyclebinitem list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "businessPhones": [],
      "displayName": "John Doe",
      "givenName": "John Doe",
      "jobTitle": "Developer",
      "mail": "john@contoso.com",
      "mobilePhone": "0476345130",
      "officeLocation": "Washington",
      "preferredLanguage": "nl-BE",
      "surname": "John",
      "userPrincipalName": "7e06b56615f340138bf879874d52e68ajohn@contoso.com",
      "id": "7e06b566-15f3-4013-8bf8-79874d52e68a"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    displayName  userPrincipalName
  ------------------------------------  -----------  -----------------------------------------------
  7e06b566-15f3-4013-8bf8-79874d52e68a  John Doe     7e06b56615f340138bf879874d52e68ajohn@contoso.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,userPrincipalName
  7e06b566-15f3-4013-8bf8-79874d52e68a,John Doe,7e06b56615f340138bf879874d52e68ajohn@contoso.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra user recyclebinitem list

  Date: 14/02/2023

  ## John Doe (7e06b566-15f3-4013-8bf8-79874d52e68a)

  Property | Value
  ---------|-------
  displayName | John Doe
  givenName | John Doe
  jobTitle | Developer
  mail | john@contoso.com
  mobilePhone | 0476345130
  officeLocation | Washington
  preferredLanguage | nl-BE
  surname | John
  userPrincipalName | 7e06b56615f340138bf879874d52e68ajohn@contoso.com
  id | 7e06b566-15f3-4013-8bf8-79874d52e68a
  ```

  </TabItem>
</Tabs>
