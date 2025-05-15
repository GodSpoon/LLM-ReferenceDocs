<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo site apppermission list

Lists application permissions for a site

## Usage

```sh
m365 spo site apppermission list [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: URL of the site collection to retrieve information for

`-i, --appId [appId]`
: Id of the application to filter by

`-n, --appDisplayName [appDisplayName]`
: Display name of the application to filter by
```

<Global />

## Remarks

To filter by an app, pass in either `appId` or `appDisplayName` not both

## Examples

Return list of application permissions for the _https://contoso.sharepoint.com/sites/project-x_ site collection.

```sh
m365 spo site apppermission list --siteUrl https://contoso.sharepoint.com/sites/project-x
```

Return list of application permissions for the _https://contoso.sharepoint.com/sites/project-x_ site collection and filter by an application called Foo

```sh
m365 spo site apppermission list --siteUrl https://contoso.sharepoint.com/sites/project-x --appDisplayName Foo
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "appDisplayName": "Foo",
      "appId": "5c89fbbf-670e-48e7-a0bc-fa8942c895a2",
      "permissionId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "roles": [
        "manage"
      ]
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  appDisplayName  appId                                 permissionId                                                                                                              roles
  --------------  ------------------------------------  ------------------------------------------------------------------------------------------------------------------------  ------
  Foo             5c89fbbf-670e-48e7-a0bc-fa8942c895a2  EXAMPLE_SECRET_VALUE_PLACEHOLDER  manage
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  appDisplayName,appId,permissionId
  Foo,5c89fbbf-670e-48e7-a0bc-fa8942c895a2,EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo site apppermission list --siteUrl "https://contoso.sharepoint.com/sites/team1"

  Date: 2023-06-21

  Property | Value
  ---------|-------
  appDisplayName | Foo
  appId | 5c89fbbf-670e-48e7-a0bc-fa8942c895a2
  permissionId | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
</Tabs>
