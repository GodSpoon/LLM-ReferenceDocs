-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo tenant site membership list

Retrieves information about default site groups' membership

## Usage

```sh
m365 spo tenant site membership list [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: The URL of the site.

`-r, --role [role]`
: Filter the results to include only users with the specified roles: `Owner`, `Member`, or `Visitor`.
```

<Global />

## Remarks

:::info

To use this command, you must be a Global or SharePoint administrator.

:::

For other scenarios, refer to the [spo web get --withGroups](../web/web-get.mdx) and [spo group member list](../group/group-member-list.mdx) commands.

## Examples

Retrieve information about default site groups' owners, members, and visitors of the site.

```sh
m365 spo tenant site membership list --siteUrl https://contoso.sharepoint.com
```

Retrieve information about site owners.

```sh
m365 spo tenant site membership list --siteUrl https://contoso.sharepoint.com --role Owner
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "AssociatedOwnerGroup": [
      {
        "email": "jdoe@contoso.onmicrosoft.com",
        "loginName": "i:0#.f|membership|jdoe@contoso.onmicrosoft.com",
        "name": "John Doe",
        "userPrincipalName": "jdoe@contoso.onmicrosoft.com"
      }
    ],
    "AssociatedMemberGroup": [
      {
        "email": "avance@contoso.onmicrosoft.com",
        "loginName": "i:0#.f|membership|avance@contoso.onmicrosoft.com",
        "name": "Adele Vance",
        "userPrincipalName": "avance@contoso.onmicrosoft.com"
      }
    ],
    "AssociatedVisitorGroup": [
      {
        "email": "",
        "loginName": "c:0-.f|rolemanager|spo-grid-all-users/dc109ffd-4298-487e-9cbc-6b9b1a2cd3e2",
        "name": "Everyone except external users",
        "userPrincipalName": null
      }
    ]
  }
  ```
  </TabItem>
  <TabItem value="Text">

  ```text
  email                             name                            userPrincipalName                 associatedGroupType
  --------------------------------  ------------------------------  --------------------------------  -------------------
  jdoe@contoso.onmicrosoft.com      John Doe                        jdoe@contoso.onmicrosoft.com      Owner
  ```

  </TabItem>
    <TabItem value="CSV">

  ```csv
  email,loginName,name,userPrincipalName,associatedGroupType
  jdoe@contoso.onmicrosoft.com,i:0#.f|membership|jdoe@contoso.onmicrosoft.com,John Doe,jdoe@contoso.onmicrosoft.com,Owner
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo tenant site membership list --siteUrl "https://contoso.sharepoint.com/sites/AudienceTest"

  Date: 11/08/2024

  ## John Doe

  Property | Value
  ---------|-------
  email | jdoe@contoso.onmicrosoft.com
  loginName | i:0#.f\|membership\|jdoe@contoso.onmicrosoft.com
  name | John Doe
  userPrincipalName | jdoe@contoso.onmicrosoft.com
  associatedGroupType | Owner

  ```

  </TabItem>
</Tabs>
