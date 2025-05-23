-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage community list

Lists all Viva Engage communities

## Usage

```sh
m365 viva engage community list [options]
```

## Options

<Global />

## Examples

Lists all Viva Engage communities

```sh
m365 viva engage community list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "displayName": "All Company",
      "description": "This is the default group for everyone in the network",
      "privacy": "public",
      "groupId": "7c99afd7-9f3a-49e2-b105-4ee36314350c"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                                displayName  privacy
  ------------------------------------------------  -----------  -------
  EXAMPLE_SECRET_VALUE_PLACEHOLDER  All Company  public
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,description,privacy,groupId
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,All Company,This is the default group for everyone in the network,public,7c99afd7-9f3a-49e2-b105-4ee36314350c
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # viva engage community list

  Date: 8/29/2024

  ## All Company (EXAMPLE_SECRET_VALUE_PLACEHOLDER)

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  displayName | All Company
  description | This is the default group for everyone in the network
  privacy | public
  groupId | 7c99afd7-9f3a-49e2-b105-4ee36314350c
  ```
  
  </TabItem>
</Tabs>
