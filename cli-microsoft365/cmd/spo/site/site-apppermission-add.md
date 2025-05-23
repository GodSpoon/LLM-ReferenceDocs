-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo site apppermission add

Adds a specific application permissions to the site

## Usage

```sh
m365 spo site apppermission add [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: URL of the site collection to add the permission

`-p, --permission <permission>`
: Permission to site (`read`, `write`, `manage` or `fullcontrol`)

`-i, --appId [appId]`
: Client ID of the Microsoft Entra app for which to grant permissions

`-n, --appDisplayName [appDisplayName]`
: Display name of the Microsoft Entra app for which to grant permissions
```

<Global />

## Remarks

To set permissions, specify at minimum either `appId` or `appDisplayName`. For best performance specify both values to avoid extra lookup.

## Example

Grants the specified app the _read_ permission to site _https://contoso.sharepoint.com/sites/project-x_

```sh
m365 spo site apppermission add --siteUrl https://contoso.sharepoint.com/sites/project-x --permission read --appDisplayName Foo
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
        "displayName": "Foo",
        "id": "5c89fbbf-670e-48e7-a0bc-fa8942c895a2"
      }
    }
  ],
  "grantedToIdentities": [
    {
      "application": {
        "displayName": "Foo",
        "id": "5c89fbbf-670e-48e7-a0bc-fa8942c895a2"
      }
    }
  ]
}
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  grantedToIdentities  : [{"application":{"displayName":"Foo","id":"5c89fbbf-670e-48e7-a0bc-fa8942c895a2"}}]
  grantedToIdentitiesV2: [{"application":{"displayName":"Foo","id":"5c89fbbf-670e-48e7-a0bc-fa8942c895a2"}}]
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
  # spo site apppermission add --siteUrl "https://contoso.sharepoint.com/sites/team1" --permission "read" --appDisplayName "Foo"

  Date: 2023-06-21

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
</Tabs>
