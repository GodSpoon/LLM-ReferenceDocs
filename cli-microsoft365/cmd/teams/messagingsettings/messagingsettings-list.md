-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams messagingsettings list

Lists messaging settings for a Microsoft Teams team

## Usage

```sh
m365 teams messagingsettings list [options]
```

## Options

```md definition-list
`-i, --teamId`
: The ID of the team for which to get the messaging settings.
```

<Global />

## Examples

Get messaging settings for a Microsoft Teams team.

```sh
m365 teams messagingsettings list --teamId 2609af39-7775-4f94-a3dc-0dd67657e900
```

## Response

<Tabs>
  <TabItem value="JSON">

  ``` json
  {
    "allowUserEditMessages": true,
    "allowUserDeleteMessages": true,
    "allowOwnerDeleteMessages": true,
    "allowTeamMentions": true,
    "allowChannelMentions": true
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ``` text
  allowChannelMentions    : true
  allowOwnerDeleteMessages: true
  allowTeamMentions       : true
  allowUserDeleteMessages : true
  allowUserEditMessages   : true
  ```

  </TabItem>
  <TabItem value="CSV">

  ``` text
  allowUserEditMessages,allowUserDeleteMessages,allowOwnerDeleteMessages,allowTeamMentions,allowChannelMentions
  1,1,1,1,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams messagingsettings list --teamId "2609af39-7775-4f94-a3dc-0dd67657e900"

  Date: 1/3/2023

  ## undefined (undefined)

  Property | Value
  ---------|-------
  allowUserEditMessages | true
  allowUserDeleteMessages | true
  allowOwnerDeleteMessages | true
  allowTeamMentions | true
  allowChannelMentions | true
  ```

  </TabItem>
</Tabs>
