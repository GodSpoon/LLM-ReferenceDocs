-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra administrativeunit list

Retrieves a list of administrative units

## Usage

```sh
m365 entra administrativeunit list [options]
```

## Options

```md definition-list
`-p, --properties [properties]`
: Comma-separated list of properties to retrieve.
```

<Global />

## Remarks

Using the `--properties` option, you can specify a comma-separated list of administrative unit properties to retrieve from the Microsoft Graph. If you don't specify any properties, the command will output the default properties returned by Graph.

## Examples

Retrieve a list of administrative units.

```sh
m365 entra administrativeunit list
```

Retrieve a list of administrative units with specified properties.

```sh
m365 entra administrativeunit list --properties "id,displayName"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "0a22c83d-c4ac-43e2-bb5e-87af3015d49f",
      "deletedDateTime": null,
      "displayName": "Marketing Department",
      "description": "Marketing Department Administration",
      "membershipRule": null,
      "membershipType": null,
      "membershipRuleProcessingState": null,
      "visibility": "HiddenMembership"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  displayName: 0a22c83d-c4ac-43e2-bb5e-87af3015d49f
  id         : Marketing Department
  visibility : HiddenMembership
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,description,visibility
  0a22c83d-c4ac-43e2-bb5e-87af3015d49f,Marketing Department,Marketing Department Administration,HiddenMembership
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra administrativeunit list

  Date: 2023-10-16

  ## Marketing Department (0a22c83d-c4ac-43e2-bb5e-87af3015d49f)

  Property | Value
  ---------|-------
  id | 0a22c83d-c4ac-43e2-bb5e-87af3015d49f
  displayName | Marketing Department
  description | Marketing Department Administration
  visibility | HiddenMembership
  ```

  </TabItem>
</Tabs>

## More information

- Administrative units: https://learn.microsoft.com/entra/identity/role-based-access-control/administrative-units
