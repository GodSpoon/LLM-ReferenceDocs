-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# tenant people profilecardproperty list

Lists all profile card properties

## Usage

```sh
m365 tenant people profilecardproperty list [options]
```

## Options

<Global />

## Remarks

:::info

To use this command you must be either **Tenant Administrator** or **Global Administrator**.

:::

## Examples

Lists all profile card properties

```sh
m365 tenant people profilecardproperty list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "directoryPropertyName": "customAttribute1",
      "annotations": [
        {
          "displayName": "Cost center",
          "localizations": [
            {
              "languageTag": "de",
              "displayName": "Kostenstelle"
            }
          ]
        }
      ]
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  directoryPropertyName  displayName     displayName de
  ---------------------  --------------  --------------
  customAttribute1       Cost center     Kostenstelle
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  directoryPropertyName,displayName,displayName de
  customAttribute1,Cost center,Kostenstelle
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # tenant people profilecardproperty list

  Date: 11/4/2023

  ## Cost center

  Property | Value
  ---------|-------
  directoryPropertyName | customAttribute1
  displayName | Cost center
  displayName de | Kostenstelle
  ```

  </TabItem>
</Tabs>

## More information

- https://learn.microsoft.com/graph/add-properties-profilecard
