-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo site admin list

Lists all administrators of a specific SharePoint site

## Usage

```sh
m365 spo site admin list [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: The URL of the SharePoint site

`--asAdmin`
: List admins as admin for sites you don't have permission to
```

<Global />

## Remarks

:::info

To use this command with the `--asAdmin` mode, you must be at least SharePoint administrator.

Without this parameter, you must have site collection admin permissions for the requested site.

:::

## Examples

Lists all admins of a SharePoint site

```sh
m365 spo site admin list --siteUrl https://contoso.sharepoint.com
```

Lists all admins of a SharePoint site as admin

```sh
m365 spo site admin list --siteUrl https://contoso.sharepoint.com --asAdmin
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Id": 6,
      "LoginName": "i:0#.f|membership|user@contoso.com",
      "Title": "User Example",
      "PrincipalType": 1,
      "PrincipalTypeString": "User",
      "Email": "user@contoso.com",
      "IsPrimaryAdmin": true
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Id  LoginName                                                                    Title    PrincipalTypeString
  --  ---------------------------------------------------------------------------  -------  -------------------
  15  c:0o.c|federateddirectoryclaimprovider|d8430798-5a00-00ba-83b0-dd7a032d549a  Members  SecurityGroup
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Id,LoginName,Title,PrincipalType,PrincipalTypeString,Email,IsPrimaryAdmin
  6,i:0#.f|membership|user@contoso.com,User Example,1,User,user@contoso.com,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo site admin list --siteUrl "https://contoso.sharepoint.com/sites/Test"

  Date: 20/03/2024

  ## User Example

  Property | Value
  ---------|-------
  Id | 6
  LoginName | i:0#.f\|membership\|user@contoso.com
  Title | User Example
  PrincipalType | 1
  PrincipalTypeString | User
  Email | user@contoso.com
  IsPrimaryAdmin | true
  ```

  </TabItem>
</Tabs>

### `asAdmin` response

When we make use of the option `asAdmin` the response will differ. 

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Email": "user@contoso.com",
      "LoginName": "i:0#.f|membership|user@contoso.com",
      "Title": "User Example",
      "IsPrimaryAdmin": true
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  LoginName                                                                    Title          
  ---------------------------------------------------------------------------  ---------------
  c:0o.c|federateddirectoryclaimprovider|d8430798-5a00-00ba-83b0-dd7a032d549a  Members        
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Email,LoginName,Title,IsPrimaryAdmin
  user@contoso.com,i:0#.f|membership|user@contoso.com,User Example,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo site admin list --siteUrl "https://contoso.sharepoint.com/sites/Test" --asAdmin

  Date: 20/03/2024

  ## User Example

  Property | Value
  ---------|-------
  Email | user@contoso.com
  LoginName | i:0#.f\|membership\|user@contoso.com
  Title | User Example
  IsPrimaryAdmin | true
  ```

  </TabItem>
</Tabs>
