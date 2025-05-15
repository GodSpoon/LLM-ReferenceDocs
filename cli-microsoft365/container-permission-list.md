<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spe container permission list

Lists permissions of a SharePoint Embedded Container

## Usage

```sh
m365 spe container permission list [options]
```

## Options

```md definition-list
`-i, --containerId <id>`
: The ID of the SharePoint Embedded Container.
```

<Global />

## Examples

Lists Container permissions.

```sh
m365 spe container permission list --containerId "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "roles": [
        "owner"
      ],
      "grantedToV2": {
        "user": {
          "displayName": "John Doe",
          "email": "john.doe@contoso.onmicrosoft.com",
          "userPrincipalName": "john.doe@contoso.onmicrosoft.com"
        }
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                                                    userPrincipalName                 roles
  --------------------------------------------------------------------  --------------------------------  ------
  EXAMPLE_SECRET_VALUE_PLACEHOLDER  john.doe@contoso.onmicrosoft.com  owner
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,roles,userPrincipalName
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,owner,john.doe@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spe container permission list --containerId "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER"

  Date: 3/3/2025

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  roles | owner
  userPrincipalName | john.doe@contoso.onmicrosoft.com
  ```

  </TabItem>
</Tabs>
