-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp card clone

Clones a specific Microsoft Power Platform card in the specified Power Platform environment

## Usage

```sh
m365 pp card clone [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment.

`--newName <newName>`
: The name of the new card.

`-i, --id [id]`
: The id of the card. Specify either `id` or `name` but not both.

`-n, --name [name]`
: The name of the card. Specify either `id` or `name` but not both.

`--asAdmin`
: Run the command as admin for environments you do not have explicitly assigned permissions to.
```

<Global />

## Examples

Clones a specific card in a specific environment based on name.

```sh
m365 pp card clone --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "CLI 365 Card" --newName "CLI 365 new Card"
```

Clones a specific card in a specific environment based on name as admin.

```sh
m365 pp card clone --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "CLI 365 Card" --newName "CLI 365 new Card" --asAdmin 
```

Clones a specific card in a specific environment based on id.

```sh
m365 pp card clone --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --id "408e3f42-4c9e-4c93-8aaf-3cbdea9179aa" --newName "CLI 365 new Card"
```

Clones a specific card in a specific environment based on id as admin.

```sh
m365 pp card clone --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --id "408e3f42-4c9e-4c93-8aaf-3cbdea9179aa" --newName "CLI 365 new Card" --asAdmin
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "CardIdClone": "80cff342-ddf1-4633-aec1-6d3d131b29e0"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  CardIdClone: 80cff342-ddf1-4633-aec1-6d3d131b29e0
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  CardIdClone
  80cff342-ddf1-4633-aec1-6d3d131b29e0
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pp card clone --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --id "408e3f42-4c9e-4c93-8aaf-3cbdea9179aa" --newName "CLI 365 new Card"

  Date: 9/1/2023

  Property | Value
  ---------|-------
  CardIdClone | 90460614-6ede-4231-8467-ce99a6359f45
  ```

  </TabItem>
</Tabs>
