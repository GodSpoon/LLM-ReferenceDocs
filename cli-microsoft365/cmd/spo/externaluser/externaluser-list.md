-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo externaluser list

Lists external users in the tenant

## Usage

```sh
m365 spo externaluser list [options]
```

## Options

```md definition-list
`--filter [filter]`
: Limits the results to only those users whose first name, last name or email address begins with the text in the string, using a case-insensitive comparison.

`-p, --pageSize [pageSize]`
: Specifies the maximum number of users to be returned in the collection. The value must be less than or equal to `50`.

`-i, --position [position]`
: Use to specify the zero-based index of the position in the sorted collection of the first result to be returned.

`-s, --sortOrder [sortOrder]`
: Specifies the sort results in Ascending or Descending order on the `SPOUser.Email` property should occur. Allowed values `asc|desc`. Default `asc`.

`-u, --siteUrl [siteUrl]`
: Specifies the site to retrieve external users for. If no site is specified, the external users for all sites are returned.
```

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

List all external users from the current tenant. Show the first batch of 50 users.

```sh
m365 spo externaluser list --pageSize 50 --position 0
```

List all external users from the current tenant whose first name, last name or email address begins with `Vesa`. Show the first batch of 50 users.

```sh
m365 spo externaluser list --pageSize 50 --position 0 --filter Vesa
```

List all external users from the specified site. Show the first batch of 50 users.

```sh
m365 spo externaluser list --pageSize 50 --position 0 --siteUrl https://contoso.sharepoint.com
```

List all external users from the current tenant. Show the first batch of 50 users sorted descending
by e-mail.

```sh
m365 spo externaluser list --pageSize 50 --position 0 --sortOrder desc
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Id": 14,
      "IsHiddenInUI": false,
      "LoginName": "i:0#.f|membership|user_domain.nl#ext#@tenant.onmicrosoft.com",
      "Title": "Jon Doe",
      "PrincipalType": 1,
      "Email": "user@domain.nl",
      "Expiration": "",
      "IsEmailAuthenticationGuestUser": false,
      "IsShareByEmailGuestUser": true,
      "IsSiteAdmin": false,
      "UserId": null,
      "UserPrincipalName": "user_domain.nl#ext#@tenant.onmicrosoft.com"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Id  IsHiddenInUI  LoginName                                                     Title     PrincipalType   Email           Expiration  IsEmailAuthenticationGuestUser  IsShareByEmailGuestUser   IsSiteAdmin   UserId  UserPrincipalName
  --- ------------  ------------------------------------------------------------- --------  --------------  --------------  ----------- ------------------------------- ------------------------  ------------  ------- -------------------------------------------
  14  false         i:0#.f|membership|user_domain.nl#ext#@tenant.onmicrosoft.com  Jon Doe   1               user@domain.nl              false                           true                      false         null    user_domain.nl#ext#@tenant.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Id,IsHiddenInUI,LoginName,Title,PrincipalType,Email,Expiration,IsEmailAuthenticationGuestUser,IsShareByEmailGuestUser,IsSiteAdmin,UserId,UserPrincipalName
  14,false,i:0#.f|membership|user_domain.nl#ext#@tenant.onmicrosoft.com,Jon Doe,1,user@domain.nl,false,true,false,null,user_domain.nl#ext#@tenant.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # m365 spo externaluser list --pageSize 50 --position 0

  Date: 10/3/2023

  ## Jon Doe (14)

  Property | Value
  ---------|-------
  Id | 14
  IsHiddenInUI | false
  LoginName | i:0#.f|membership|user_domain.nl#ext#@tenant.onmicrosoft.com
  Title | Jon Doe
  PrincipalType | 1
  Email | user@domain.nl
  Expiration | 
  IsEmailAuthenticationGuestUser | false
  IsShareByEmailGuestUser | true
  IsSiteAdmin | false
  UserId | null
  UserPrincipalName | user_domain.nl#ext#@tenant.onmicrosoft.com
  ```

  </TabItem>
</Tabs>
