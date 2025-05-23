-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo user list

Lists all the users within specific web

## Usage

```sh
m365 spo user list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the web to list the users from
```

<Global />

## Examples

Get list of users in a web

```sh
m365 spo user list --webUrl https://contoso.sharepoint.com/sites/project-x
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Id": 10,
      "IsHiddenInUI": false,
      "LoginName": "i:0#.f|membership|johndoe@contoso.onmicrosoft.com",
      "Title": "John DOe",
      "PrincipalType": 1,
      "Email": "johndoe@contoso.onmicrosoft.com",
      "Expiration": "",
      "IsEmailAuthenticationGuestUser": false,
      "IsShareByEmailGuestUser": false,
      "IsSiteAdmin": false,
      "UserId": {
        "NameId": "100320022ec308a7",
        "NameIdIssuer": "urn:federation:microsoftonline"
      },
      "UserPrincipalName": "johndoe@contoso.onmicrosoft.com"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Id   Title     LoginName
  ---  --------  -------------------------------------------------
  10   John Doe  i:0#.f|membership|johndoe@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Id,Title,LoginName
  10,John Doe,i:0#.f|membership|johndoe@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo user list --webUrl "https://contoso.sharepoint.com/sites/project-x"

  Date: 4/10/2023

  ## John Doe (10)

  Property | Value
  ---------|-------
  Id | 7
  IsHiddenInUI | false
  LoginName | c:0o.c\|membership\|johndoe@contoso.onmicrosoft.com
  Title | John Doe
  PrincipalType | 1
  Email | johndoe@contoso.onmicrosoft.com
  Expiration | 
  IsEmailAuthenticationGuestUser | false
  IsShareByEmailGuestUser | false
  IsSiteAdmin | false
  UserPrincipalName | johndoe@contoso.onmicrosoft.com
  ```

  </TabItem>
</Tabs>
