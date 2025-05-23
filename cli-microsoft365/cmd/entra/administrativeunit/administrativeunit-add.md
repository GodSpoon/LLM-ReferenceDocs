-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra administrativeunit add

Creates a new administrative unit

## Usage

```sh
m365 entra administrativeunit add [options]
```

## Options

```md definition-list
`-n, --displayname <displayName>`
: Display name for the administrative unit.

`-d, --description [description]`
: Description for the administrative unit.

`--hiddenMembership`
: Indicates whether the administrative unit and its members are hidden.
```

<Global />

## Remarks

:::info

To use this command you must be either **Global Administrator** or **Privileged Role Administrator**.

:::

## Examples

Create an administrative unit with a specific display name

```sh
m365 entra administrativeunit add --displayName 'Marketing Division'
```

Create an administrative unit with a specific display name and description

```sh
m365 entra administrativeunit add --displayName 'Marketing Division' --description 'Marketing department administration'
```

Create a hidden administrative unit with a specific display name

```sh
m365 entra administrativeunit add --displayName 'Marketing Division' --hiddenMembership
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "00b45a1b-7632-4e94-a3bd-f06aec976d31",
    "deletedDateTime": null,
    "displayName": "Marketing Division",
    "description": "Marketing department administration",
    "membershipRule": null,
    "membershipType": null,
    "membershipRuleProcessingState": null,
    "visibility": null
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  deletedDateTime              : null
  description                  : Marketing department administration
  displayName                  : Marketing Division
  id                           : 00b45a1b-7632-4e94-a3bd-f06aec976d31
  membershipRule               : null
  membershipRuleProcessingState: null
  membershipType               : null
  visibility                   : null
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,description,visibility
  00b45a1b-7632-4e94-a3bd-f06aec976d31,Marketing Division,Marketing department administration,HiddenMembership
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Date: 10/23/2023

  ## Marketing Division (00b45a1b-7632-4e94-a3bd-f06aec976d31)

  Property | Value
  ---------|-------
  id | 00b45a1b-7632-4e94-a3bd-f06aec976d31
  displayName | Marketing Division
  description | Marketing department administration
  visibility | HiddenMembership
  ```

  </TabItem>
</Tabs>

## More information

- Administrative units: https://learn.microsoft.com/entra/identity/role-based-access-control/administrative-units
