-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo site apppermission get

Get a specific application permissions for the site

## Usage

```sh
m365 spo site apppermission get [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: URL of the site collection where the permission to retrieve is located

`-i, --id <id>`
: ID of the permission to retrieve
```

<Global />

## Example

Return a specific application permissions for the _https://contoso.sharepoint.com/sites/project-x_ site collection with permission id EXAMPLE_SECRET_VALUE_PLACEHOLDER

```sh
m365 spo site apppermission get --siteUrl https://contoso.sharepoint.com/sites/project-x --id EXAMPLE_SECRET_VALUE_PLACEHOLDER
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
      "roles": "read"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  appDisplayName: Foo
  appId         : 5c89fbbf-670e-48e7-a0bc-fa8942c895a2
  permissionId  : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  roles         : read
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  appDisplayName,appId,permissionId,roles
  Foo,5c89fbbf-670e-48e7-a0bc-fa8942c895a2,EXAMPLE_SECRET_VALUE_PLACEHOLDER,read
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo site apppermission get --siteUrl "https://contoso.sharepoint.com/sites/marketing" --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

  Date: 2023-06-21

  Property | Value
  ---------|-------
  appDisplayName | Foo
  appId | 5c89fbbf-670e-48e7-a0bc-fa8942c895a2
  permissionId | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  roles | read
  ```

  </TabItem>
</Tabs>
