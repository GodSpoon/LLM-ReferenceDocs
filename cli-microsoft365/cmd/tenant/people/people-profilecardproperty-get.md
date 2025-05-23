-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# tenant people profilecardproperty get

Retrieves information about a specific profile card property

## Usage

```sh
m365 tenant people profilecardproperty get [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The name of the property to retrieve. Allowed values: `UserPrincipalName`, `Fax`, `StreetAddress`, `PostalCode`, `StateOrProvince`, `Alias`, `customAttribute1`, `customAttribute2`, `customAttribute3`, `customAttribute4`, `customAttribute5`, `customAttribute6`, `customAttribute7`, `customAttribute8`, `customAttribute9`, `customAttribute10`, `customAttribute11`, `customAttribute12`, `customAttribute13`, `customAttribute14`, `customAttribute15`.
```

<Global />

## Remarks

:::info

To use this command you must be either **Tenant Administrator** or **Global Administrator**.

:::

## Examples

Retrieve information about a specific profile card property

```sh
m365 tenant people profilecardproperty get --name customAttribute1
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
            "displayName": "Kostencentrum"
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
  displayName nl-NL    : Kostencentrum
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  directoryPropertyName,displayName,displayName nl-NL
  customAttribute1,Cost center,Kostencentrum
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # tenant people profilecardproperty get --name "customAttribute1"

  Date: 3/11/2023

  ## Cost center

  Property | Value
  ---------|-------
  directoryPropertyName | customAttribute1
  displayName | Cost center
  displayName nl-NL | Kostencentrum
  ```

  </TabItem>
</Tabs>

## More information

- https://learn.microsoft.com/graph/add-properties-profilecard
