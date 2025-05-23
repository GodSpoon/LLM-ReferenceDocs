-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# tenant people profilecardproperty remove

Removes an additional attribute from the profile card properties

## Usage

```sh
m365 tenant people profilecardproperty remove [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The name of the property to remove. Allowed values: `UserPrincipalName`, `Fax`, `StreetAddress`, `PostalCode`, `StateOrProvince`, `Alias`, `customAttribute1`, `customAttribute2`, `customAttribute3`, `customAttribute4`, `customAttribute5`, `customAttribute6`, `customAttribute7`, `customAttribute8`, `customAttribute9`, `customAttribute10`, `customAttribute11`, `customAttribute12`, `customAttribute13`, `customAttribute14`, `customAttribute15`.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::info

To use this command you must be either **Tenant Administrator** or **Global Administrator**.

:::

:::warning

When removing an attribute from a profile card, it takes up to 24 hours for the change to be displayed.

:::

## Examples

Removes the UPN as a profile property from the profile cards

```sh
m365 tenant people profilecardproperty remove --name UserPrincipalName
```

Removes the UPN as a profile property from the profile cards, without showing a confirmation prompt

```sh
m365 tenant people profilecardproperty remove --name UserPrincipalName --force
```

## Response

The command won't return a response on success.

## More information

- https://learn.microsoft.com/graph/add-properties-profilecard
