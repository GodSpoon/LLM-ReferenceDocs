-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo group member list

List the members of a SharePoint Group

## Usage

```sh
m365 spo group member list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the SharePoint site.

`--groupId [groupId]`
: Id of the SharePoint group. Specify either `groupName` or `groupId`, but not both.

`--groupName [groupName]`
: Name of the SharePoint group. Specify either `groupName` or `groupId`, but not both.
```

<Global />

## Examples

List the members of the group with ID for the specified web.

```sh
m365 spo group member list --webUrl https://contoso.sharepoint.com/sites/SiteA --groupId 5
```

List the members of the group with name for the specified web.

```sh
m365 spo group member list --webUrl https://contoso.sharepoint.com/sites/SiteA --groupName "Contoso Site Members"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Id": 7,
      "IsHiddenInUI": false,
      "LoginName": "i:0#.f|membership|admin@contoso.onmicrosoft.com",
      "Title": "Jon Doe",
      "PrincipalType": 1,
      "Email": "admin@contoso.onmicrosoft.com",
      "Expiration": "",
      "IsEmailAuthenticationGuestUser": false,
      "IsShareByEmailGuestUser": false,
      "IsSiteAdmin": true,
      "UserId": {
        "NameId": "100320006513e584",
        "NameIdIssuer": "urn:federation:microsoftonline"
      },
      "UserPrincipalName": "admin@contoso.onmicrosoft.com"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Email            : admin@contoso.onmicrosoft.com
  Id               : 7
  Title            : Jon Doe
  UserPrincipalName: admin@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Id,IsHiddenInUI,LoginName,Title,PrincipalType,Email,Expiration,IsEmailAuthenticationGuestUser,IsShareByEmailGuestUser,IsSiteAdmin,UserPrincipalName
  7,,i:0#.f|membership|admin@contoso.onmicrosoft.com,Jon Doe,1,admin@contoso.onmicrosoft.com,,,,1,admin@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo group member list --webUrl "https://contoso.sharepoint.com/sites/SiteA" --groupName "Contoso Site Members"

  Date: 10/3/2023

  ## Jon Doe (7)

  Property | Value
  ---------|-------
  Id | 7
  IsHiddenInUI | false
  LoginName | i:0#.f\|membership\|admin@contoso.onmicrosoft.com
  Title | Jon Doe
  PrincipalType | 1
  Email | admin@contoso.onmicrosoft.com
  Expiration |
  IsEmailAuthenticationGuestUser | false
  IsShareByEmailGuestUser | false
  IsSiteAdmin | true
  UserPrincipalName | admin@contoso.onmicrosoft.com
  ```

  </TabItem>
</Tabs>
