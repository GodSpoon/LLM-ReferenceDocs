-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams membersettings list

Lists member settings for a Microsoft Teams team

## Usage

```sh
m365 teams membersettings list [options]
```

## Options

```md definition-list
`-i, --teamId`
: The ID of the team for which to get the member settings
```

<Global />

## Examples

Get member settings for a Microsoft Teams team

```sh
m365 teams membersettings list --teamId 2609af39-7775-4f94-a3dc-0dd67657e900
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "allowCreateUpdateChannels": true,
    "allowCreatePrivateChannels": true,
    "allowDeleteChannels": true,
    "allowAddRemoveApps": true,
    "allowCreateUpdateRemoveTabs": true,
    "allowCreateUpdateRemoveConnectors": true
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  allowAddRemoveApps               : true
  allowCreatePrivateChannels       : true
  allowCreateUpdateChannels        : true
  allowCreateUpdateRemoveConnectors: true
  allowCreateUpdateRemoveTabs      : true
  allowDeleteChannels              : true
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  allowCreateUpdateChannels,allowCreatePrivateChannels,allowDeleteChannels,allowAddRemoveApps,allowCreateUpdateRemoveTabs,allowCreateUpdateRemoveConnectors
  1,1,1,1,1,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams membersettings list --teamId "2609af39-7775-4f94-a3dc-0dd67657e900"

  Date: 5/7/2023

  Property | Value
  ---------|-------
  allowCreateUpdateChannels | true
  allowCreatePrivateChannels | true
  allowDeleteChannels | true
  allowAddRemoveApps | true
  allowCreateUpdateRemoveTabs | true
  allowCreateUpdateRemoveConnectors | true
  ```

  </TabItem>
</Tabs>
