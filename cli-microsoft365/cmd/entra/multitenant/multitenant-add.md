-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra multitenant add

Creates a new multitenant organization

## Usage

```sh
m365 entra multitenant add [options]
```

## Options

```md definition-list
`-n, --displayname <displayName>`
: Display name for the multitenant organization.

`-d, --description [description]`
: Description for the multitenant organiztion.
```

<Global />

## Remarks

:::info

To use this command you must be at least **Security Administrator**.

:::

## Examples

Create a new multitenant organization with display name only.

```sh
m365 entra multitenant add --displayName 'Contoso organization'
```

Create a new multitenant organization with display name and description.

```sh
m365 entra multitenant add --displayName 'Contoso organization' --description 'Multitenant organization between Contoso, Fabrikam, and Woodgrove Bank'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "c231d4a5-138f-4bdf-9fee-f26a90ea3ad0",
    "createdDateTime": "2024-05-05T05:05:05Z",
    "state": "active",
    "displayName": "Contoso organization",
    "description": "Multitenant organization between Contoso, Fabrikam, and Woodgrove Bank"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  createdDateTime: 2024-05-05T05:05:05Z
  description    : Multitenant organization between Contoso, Fabrikam, and Woodgrove Bank
  displayName    : Contoso organization
  id             : c231d4a5-138f-4bdf-9fee-f26a90ea3ad0
  state          : active
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,createdDateTime,state,displayName,description
  c231d4a5-138f-4bdf-9fee-f26a90ea3ad0,2024-05-05T05:05:05Z,active,Contoso organization,"Multitenant organization between Contoso, Fabrikam, and Woodgrove Bank"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra multitenant add

  Date: 5/5/2024

  ## Contoso organization (c231d4a5-138f-4bdf-9fee-f26a90ea3ad0)

  Property | Value
  ---------|-------
  id | c231d4a5-138f-4bdf-9fee-f26a90ea3ad0
  createdDateTime | 2024-05-05T05:05:05Z
  state | active
  displayName | Contoso organization
  description | Multitenant organization between Contoso, Fabrikam, and Woodgrove Bank
  ```

  </TabItem>
</Tabs>

## More information

- Multitenant organization: https://learn.microsoft.com/entra/identity/multi-tenant-organizations/overview
