<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo site apppermission set

Updates a specific application permission for a site

## Usage

```sh
m365 spo site apppermission set [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: URL of the site collection where the permission to retrieve is located

`-i, --id [id]`
: ID of the permission to update. Specify `id`, `appId` or `appDisplayName`

`--appId [appId]`
: Client ID of the Microsoft Entra app for which to update permissions. Specify `id`, `appId` or `appDisplayName`

`-n, --appDisplayName [appDisplayName]`
: Display name of the Microsoft Entra app for which to update permissions. Specify `id`, `appId` or `appDisplayName`

`-p, --permission <permission>`
: Permission to site (`read`, `write`, `manage` or `fullcontrol`)
```

<Global />

## Examples

Updates a specific application permission to _read_ for the _https://contoso.sharepoint.com/sites/project-x_ site collection with permission id EXAMPLE_SECRET_VALUE_PLACEHOLDER

```sh
m365 spo site apppermission set --siteUrl https://contoso.sharepoint.com/sites/project-x --id EXAMPLE_SECRET_VALUE_PLACEHOLDER --permission read
```

Updates a specific application permission to _read_ for the _https://contoso.sharepoint.com/sites/project-x_ site collection with an application called _Foo_

```sh
m365 spo site apppermission set --siteUrl https://contoso.sharepoint.com/sites/project-x --appDisplayName Foo --permission read
```

Updates a specific application permission to _read_ for the _https://contoso.sharepoint.com/sites/project-x_ site collection with an application id _89ea5c94-7736-4e25-95ad-3fa95f62b66e_

```sh
m365 spo site apppermission set --siteUrl https://contoso.sharepoint.com/sites/project-x --appId 89ea5c94-7736-4e25-95ad-3fa95f62b66e --permission read
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "roles": [
      "read"
    ],
    "grantedToIdentitiesV2": [
      {
        "application": {
          "id": "5c89fbbf-670e-48e7-a0bc-fa8942c895a2"
        }
      }
    ],
    "grantedToIdentities": [
      {
        "application": {
          "id": "5c89fbbf-670e-48e7-a0bc-fa8942c895a2"
        }
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  grantedToIdentities  : [{"application":{"id":"5c89fbbf-670e-48e7-a0bc-fa8942c895a2"}}]
  grantedToIdentitiesV2: [{"application":{"id":"5c89fbbf-670e-48e7-a0bc-fa8942c895a2"}}]
  id                   : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  roles                : ["read"]
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id
  EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo site apppermission set --siteUrl "https://contoso.sharepoint.com/sites/marketing" --appDisplayName "Foo" --permission "read"

  Date: 2023-06-21

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
</Tabs>
