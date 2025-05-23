-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams app list

Lists apps from the Microsoft Teams app catalog

## Usage

```sh
m365 teams app list [options]
```

## Options

```md definition-list
`--distributionMethod [distributionMethod]`
: The distribution method. Allowed values `store`, `organization`, `sideloaded`.
```

<Global />

## Examples

List all apps from the Microsoft Teams app catalog

```sh
m365 teams app list
```

List all apps from the Microsoft Teams app catalog according to a given distribution method

```sh
m365 teams app list --distributionMethod 'store'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "ffdb7239-3b58-46ba-b108-7f90a6d8799b",
      "externalId": null,
      "displayName": "Contoso App",
      "distributionMethod": "store"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                                        displayName                       distributionMethod
  --------------------------------------------------------  --------------------------------  ------------------
  ffdb7239-3b58-46ba-b108-7f90a6d8799b                      Contoso App                       store
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,distributionMethod
  ffdb7239-3b58-46ba-b108-7f90a6d8799b,Contoso App,store
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams app list

  Date: 4/3/2023

  ## Contoso App (ffdb7239-3b58-46ba-b108-7f90a6d8799b)

  Property | Value
  ---------|-------
  id | ffdb7239-3b58-46ba-b108-7f90a6d8799b
  externalId | null
  displayName | Contoso App
  distributionMethod | store
  ```

  </TabItem>
</Tabs>
