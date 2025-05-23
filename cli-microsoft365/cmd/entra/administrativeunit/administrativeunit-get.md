-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra administrativeunit get

Gets information about a specific administrative unit

## Usage

```sh
m365 entra administrativeunit get [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The id of the administrative unit. Specify either `id` or `displayName` but not both.

`-n, --displayName [displayName]`
: The display name of the administrative unit. Specify either `id` or `displayName` but not both.

`-p, --properties [properties]`
: Comma-separated list of properties to retrieve.
```

<Global />

## Remarks

Using the `--properties` option, you can specify a comma-separated list of administrative unit properties to retrieve from the Microsoft Graph. If you don't specify any properties, the command will output the default properties returned by Graph.

## Examples

Get information about the administrative unit by its id.

```sh
m365 entra administrativeunit get --id 03c4c9dc-6f0c-4c4f-a4e6-0c9ed80f54c7
```

Get information about the administrative unit by its display name with specified properties.

```sh
m365 entra administrativeunit get --displayName "Marketing Division" --properties "id,displayName"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "0a22c83d-c4ac-43e2-bb5e-87af3015d49f",
    "deletedDateTime": null,
    "displayName": "Marketing Division",
    "description": "Marketing Department Administration",
    "membershipRule": null,
    "membershipType": null,
    "membershipRuleProcessingState": null,
    "visibility": "HiddenMembership"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  deletedDateTime              : null
  description                  : Marketing Department Administration
  displayName                  : Marketing Division
  id                           : 0a22c83d-c4ac-43e2-bb5e-87af3015d49f
  membershipRule               : null
  membershipRuleProcessingState: null
  membershipType               : null
  visibility                   : HiddenMembership
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,description,visibility
  0a22c83d-c4ac-43e2-bb5e-87af3015d49f,Marketing Division,Marketing Department Administration,HiddenMembership
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Date: 10/23/2023

  ## Marketing Division (0a22c83d-c4ac-43e2-bb5e-87af3015d49f)

  Property | Value
  ---------|-------
  id | 0a22c83d-c4ac-43e2-bb5e-87af3015d49f
  displayName | Marketing Division
  description | Marketing Department Administration
  visibility | HiddenMembership
  ```

  </TabItem>
</Tabs>

## More information

- Administrative units: https://learn.microsoft.com/entra/identity/role-based-access-control/administrative-units
