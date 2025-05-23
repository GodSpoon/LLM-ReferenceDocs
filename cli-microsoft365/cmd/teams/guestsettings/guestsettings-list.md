-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams guestsettings list

Lists guest settings for a Microsoft Teams team

## Usage

```sh
m365 teams guestsettings list [options]
```

## Options

```md definition-list
`-i, --teamId`
: The ID of the team for which to get the guest settings
```

<Global />

## Examples

Get guest settings for a Microsoft Teams team

```sh
m365 teams guestsettings list --teamId 2609af39-7775-4f94-a3dc-0dd67657e900
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "allowCreateUpdateChannels": false,
    "allowDeleteChannels": false
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  allowCreateUpdateChannels: false
  allowDeleteChannels      : false
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  allowCreateUpdateChannels,allowDeleteChannels
  ,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams guestsettings list --teamId "2609af39-7775-4f94-a3dc-0dd67657e900"

  Date: 5/7/2023

  Property | Value
  ---------|-------
  allowCreateUpdateChannels | false
  allowDeleteChannels | false
  ```

  </TabItem>
</Tabs>
