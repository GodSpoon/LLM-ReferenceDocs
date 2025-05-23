-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# tenant people profilecardproperty add

Adds an additional attribute to the profile card properties

## Usage

```sh
m365 tenant people profilecardproperty add [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The name of the property to add. Allowed values: `UserPrincipalName`, `Fax`, `StreetAddress`, `PostalCode`, `StateOrProvince`, `Alias`, `customAttribute1`, `customAttribute2`, `customAttribute3`, `customAttribute4`, `customAttribute5`, `customAttribute6`, `customAttribute7`, `customAttribute8`, `customAttribute9`, `customAttribute10`, `customAttribute11`, `customAttribute12`, `customAttribute13`, `customAttribute14`, `customAttribute15`.

`-d, --displayName [displayName]`
: The display name of a property, only use this together with a custom extension attribute.
```

<Global />

## Remarks

:::info

To use this command you must be either **Tenant Administrator** or **Global Administrator**.

:::

:::info

You can specify localized values for the `displayName` as well. These can be entered by suffixing the displayName option with a language code: `--displayName-nl-NL "Kostencentrum"`, `--displayName-de "Kostenstelle"`.

:::

:::warning

When adding an attribute to a profile card, it takes up to 24 hours for the addition to be displayed.

:::

## Examples

Add the UPN as a profile property to the profile cards properties

```sh
m365 tenant people profilecardproperty add --name UserPrincipalName
```

Add a custom extension attribute _Cost Center_ as a profile property to the profile cards properties

```sh
m365 tenant people profilecardproperty add --name customAttribute1 --displayName 'Cost Center'
```

Add a custom extension attribute _Cost Center_ as a profile property to the profile cards properties with a Dutch localization

```sh
m365 tenant people profilecardproperty add --name customAttribute1 --displayName 'Cost Center' --displayName-nl-NL 'Kostencentrum'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "directoryPropertyName": "customAttribute1",
    "annotations": [
      {
        "displayName": "Cost center",
        "localizations": [
          {
            "languageTag": "nl-NL",
            "displayName": "Kostenplaats"
          }
        ]
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  directoryPropertyName: customAttribute1
  displayName          : Cost center
  displayName nl-NL    : Kostenplaats
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  directoryPropertyName,displayName,displayName nl-NL
  customAttribute1,Cost center,Kostenplaats
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # tenant people profilecardproperty add --name 'customAttribute1' --displayName 'Cost center' --displayName-nl-NL 'Kostenplaats'

  Date: 11/2/2023

  Property | Value
  ---------|-------
  directoryPropertyName | customAttribute1
  displayName           | Cost center
  displayName nl-NL     | Kostenplaats
  ```

  </TabItem>
</Tabs>

## More information

- https://learn.microsoft.com/graph/add-properties-profilecard
