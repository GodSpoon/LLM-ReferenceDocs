-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# flow owner list

Lists all owners of a Power Automate flow

## Usage

```sh
m365 flow owner list [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment.

`--flowName <flowName>`
: The name of the Power Automate flow.

`--asAdmin`
: Run the command as admin.
```

<Global />

## Examples

Gets the owners by the name of the Power Automate flow within a specified environment.

```sh
m365 flow owner list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 72f2be4a-78c1-4220-a048-dbf557296a72
```

Gets the owners by the name of the Power Automate flow within a specified environment with admin privileges.

```sh
m365 flow owner list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 72f2be4a-78c1-4220-a048-dbf557296a72 --asAdmin
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "name": "fe36f75e-c103-410b-a18a-2bf6df06ac3a",
      "id": "/providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/flows/72f2be4a-78c1-4220-a048-dbf557296a72/permissions/fe36f75e-c103-410b-a18a-2bf6df06ac3a",
      "type": "/providers/Microsoft.ProcessSimple/environments/flows/permissions",
      "properties": {
        "roleName": "Owner",
        "permissionType": "Principal",
        "principal": {
          "id": "fe36f75e-c103-410b-a18a-2bf6df06ac3a",
          "type": "User"
        }
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  roleName  id                                    type
  --------  ------------------------------------  ----
  Owner     fe36f75e-c103-410b-a18a-2bf6df06ac3a  User
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  roleName,id,type
  Owner,fe36f75e-c103-410b-a18a-2bf6df06ac3a,User
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # flow owner list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --flowName "72f2be4a-78c1-4220-a048-dbf557296a72"

  Date: 25/02/2023

  ## fe36f75e-c103-410b-a18a-2bf6df06ac3a (/providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/flows/72f2be4a-78c1-4220-a048-dbf557296a72/permissions/fe36f75e-c103-410b-a18a-2bf6df06ac3a)

  Property | Value
  ---------|-------
  name | fe36f75e-c103-410b-a18a-2bf6df06ac3a
  id | /providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER/flows/72f2be4a-78c1-4220-a048-dbf557296a72/permissions/fe36f75e-c103-410b-a18a-2bf6df06ac3a
  type | /providers/Microsoft.ProcessSimple/environments/flows/permissions
  ```

  </TabItem>
</Tabs>
