-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo user ensure

Ensures that a user is available on a specific site

## Usage

```sh
m365 spo user ensure [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Absolute URL of the site.

`--entraId [entraId]`
: Id of the user in Entra ID. Specify either `entraId`, `userName`, `loginName`, `entraGroupId` or `entraGroupName`.

`--userName [userName]`
: User's UPN (user principal name, e.g. john@contoso.com). Specify either `entraId`, `userName`, `loginName`, `entraGroupId` or `entraGroupName`.

`--loginName [loginName]`
: The login name of the principal. Specify either `entraId`, `userName`, `loginName`, `entraGroupId` or `entraGroupName`.

`--entraGroupId [entraGroupId]`
: ID of the Microsoft Entra group. Specify either `entraId`, `userName`, `loginName`, `entraGroupId` or `entraGroupName`.

`--entraGroupName [entraGroupName]`
: Display name of the Microsoft Entra group. Specify either `entraId`, `userName`, `loginName`, `entraGroupId` or `entraGroupName`.
```

<Global />

## Examples

Ensure a user by its Entra Id.

```sh
m365 spo user ensure --webUrl https://contoso.sharepoint.com/sites/project --entraId e254750a-eaa4-44f6-9517-b74f65cdb747
```

Ensure a user by its user principal name.

```sh
m365 spo user ensure --webUrl https://contoso.sharepoint.com/sites/project --userName john@contoso.com
```

Ensure a user by its login name.

```sh
m365 spo user ensure --webUrl https://contoso.sharepoint.com/sites/Marketing --loginName "i:0#.f|membership|john.doe@contoso.com"
```

Ensure a Microsoft Entra group by ID.

```sh
m365 spo user ensure --webUrl https://contoso.sharepoint.com/sites/Marketing --entraGroupId e08e899f-ba40-4e91-ab36-44d4fbaa454e
```

Ensure a Microsoft Entra group by display name.

```sh
m365 spo user ensure --webUrl https://contoso.sharepoint.com/sites/Marketing --entraGroupName "Marketing team"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Id": 35,
    "IsHiddenInUI": false,
    "LoginName": "i:0#.f|membership|john@contoso.com",
    "Title": "John Doe",
    "PrincipalType": 1,
    "Email": "john@contoso.com",
    "Expiration": "",
    "IsEmailAuthenticationGuestUser": false,
    "IsShareByEmailGuestUser": false,
    "IsSiteAdmin": false,
    "UserId": {
      "NameId": "1003200274f51d2d",
      "NameIdIssuer": "urn:federation:microsoftonline"
    },
    "UserPrincipalName": "john@contoso.com"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Email                         : john@contoso.com
  Expiration                    :
  Id                            : 35
  IsEmailAuthenticationGuestUser: false
  IsHiddenInUI                  : false
  IsShareByEmailGuestUser       : false
  IsSiteAdmin                   : false
  LoginName                     : i:0#.f|membership|john@contoso.com
  PrincipalType                 : 1
  Title                         : John Doe
  UserId                        : {"NameId":"1003200274f51d2d","NameIdIssuer":"urn:federation:microsoftonline"}
  UserPrincipalName             : john@contoso.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Id,IsHiddenInUI,LoginName,Title,PrincipalType,Email,Expiration,IsEmailAuthenticationGuestUser,IsShareByEmailGuestUser,IsSiteAdmin,UserId,UserPrincipalName
  35,,i:0#.f|membership|john@contoso.com,John Doe,1,john@contoso.com,,,,,"{""NameId"":""100320009d80e5de"",""NameIdIssuer"":""urn:federation:microsoftonline""}",john@contoso.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo user ensure --webUrl "https://contoso.sharepoint.com" --userName "john@contoso.com"

  Date: 18/02/2023

  ## John Doe (35)

  Property | Value
  ---------|-------
  Id | 35
  IsHiddenInUI | false
  LoginName | i:0#.f\|membership\|john@contoso.com
  Title | John Doe
  PrincipalType | 1
  Email | john@contoso.com
  Expiration |
  IsEmailAuthenticationGuestUser | false
  IsShareByEmailGuestUser | false
  IsSiteAdmin | false
  UserPrincipalName | john@contoso.com
  ```

  </TabItem>
</Tabs>
