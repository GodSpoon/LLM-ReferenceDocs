-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo user get

Gets a site user within specific web

## Usage

```sh
m365 spo user get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the web to get the user within.

`-i, --id [id]`
: ID of the user to retrieve information for. Specify either `id`, `loginName`, `email`, `userName`, `entraGroupId`, or `entraGroupName`.

`--email [email]`
: Email of the user to retrieve information for. Specify either `id`, `loginName`, `email`, `userName`, `entraGroupId`, or `entraGroupName`.

`--loginName [loginName]`
: Login name of the user to retrieve information for. Specify either `id`, `loginName`, `email`, `userName`, `entraGroupId`, or `entraGroupName`.

`--userName [userName]`
: User's UPN (user principal name, eg. megan.bowen@contoso.com). Specify either `id`, `loginName`, `email`, `userName`, `entraGroupId`, or `entraGroupName`.

`--entraGroupId [entraGroupId]`
: The object ID of the Microsoft Entra group. Specify either `id`, `loginName`, `email`, `userName`, `entraGroupId`, or `entraGroupName`.

`--entraGroupName [entraGroupName]`
: The name of the Microsoft Entra group. Specify either `id`, `loginName`, `email`, `userName`, `entraGroupId`, or `entraGroupName`.
```

<Global />

## Examples

Get user by email for a web.

```sh
m365 spo user get --webUrl https://contoso.sharepoint.com/sites/project-x --email john.doe@mytenant.onmicrosoft.com
```

Get user by ID for a web.

```sh
m365 spo user get --webUrl https://contoso.sharepoint.com/sites/project-x --id 6
```

Get user by login name for a web.

```sh
m365 spo user get --webUrl https://contoso.sharepoint.com/sites/project-x --loginName "i:0#.f|membership|john.doe@mytenant.onmicrosoft.com"
```

Get user by user's UPN for a web.

```sh
m365 spo user get --webUrl https://contoso.sharepoint.com/sites/project-x --userName "john.doe@mytenant.onmicrosoft.com"
```

Get user by entraGroupId for a web.

```sh
m365 spo user get --webUrl https://contoso.sharepoint.com/sites/project-x --entraGroupId f832a493-de73-4fef-87ed-8c6fffd91be6
```

Get user by entraGroupName for a web.

```sh
m365 spo user get --webUrl https://contoso.sharepoint.com/sites/project-x --entraGroupName "Test Members"
```

Get the currently logged-in user.

```sh
m365 spo user get --webUrl https://contoso.sharepoint.com/sites/project-x
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Id": 10,
    "IsHiddenInUI": false,
    "LoginName": "i:0#.f|membership|johndoe@contoso.onmicrosoft.com",
    "Title": "John Doe",
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
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Email                         : johndoe@contoso.onmicrosoft.com
  Expiration                    :
  Id                            : 10
  IsEmailAuthenticationGuestUser: false
  IsHiddenInUI                  : false
  IsShareByEmailGuestUser       : false
  IsSiteAdmin                   : false
  LoginName                     : i:0#.f|membership|johndoe@contoso.onmicrosoft.com
  PrincipalType                 : 1
  Title                         : John Doe
  UserId                        : {"NameId":"100320022ec308a7","NameIdIssuer":"urn:federation:microsoftonline"}
  UserPrincipalName             : johndoe@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Id,IsHiddenInUI,LoginName,Title,PrincipalType,Email,Expiration,IsEmailAuthenticationGuestUser,IsShareByEmailGuestUser,IsSiteAdmin,UserId,UserPrincipalName
  10,,i:0#.f|membership|johndoe@contoso.onmicrosoft.com,John Doe,1,johndoe@contoso.onmicrosoft.com,,,,,"{""NameId"":""100320022ec308a7"",""NameIdIssuer"":""urn:federation:microsoftonline""}",johndoe@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo user get --webUrl "https://contoso.sharepoint.com" --loginName "i:0#.f|membership|john.doe@contoso.onmicrosoft.com"

  Date: 4/10/2023

  ## John Doe (9)

  Property | Value
  ---------|-------
  Id | 10
  IsHiddenInUI | false
  LoginName | i:0#.f\|membership\|john.doe@contoso.onmicrosoft.com
  Title | Reshmee Auckloo
  PrincipalType | 1
  Email | john.doe@contoso.onmicrosoft.com
  Expiration | 
  IsEmailAuthenticationGuestUser | false
  IsShareByEmailGuestUser | false
  IsSiteAdmin | false
  UserPrincipalName | john.doe@contoso.onmicrosoft.com
  ```

  </TabItem>
</Tabs>
