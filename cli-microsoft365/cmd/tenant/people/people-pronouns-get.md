-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# tenant people pronouns get

Retrieves information about pronouns settings for an organization

## Usage

```sh
m365 tenant people pronouns get [options]
```

## Options

<Global />

## Examples

Retrieve information about pronouns settings

```sh
m365 tenant people pronouns get
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "isEnabledInOrganization": true
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  isEnabledInOrganization: true
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  isEnabledInOrganization
  1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # tenant people pronouns get

  Date: 12/5/2024

  Property | Value
  ---------|-------
  isEnabledInOrganization | true
  ```

  </TabItem>
</Tabs>

## More information

- https://learn.microsoft.com/graph/api/peopleadminsettings-list-pronouns
