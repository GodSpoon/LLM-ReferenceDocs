-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams tab list

Lists tabs in the specified Microsoft Teams channel

## Usage

```sh
m365 teams tab list [options]
```

## Options

```md definition-list
`-i, --teamId <teamId>`
: The ID of the Microsoft Teams team where the channel is located.

`-c, --channelId <channelId>`
: The ID of the channel for which to list tabs.
```

<Global />

## Remarks

You can only retrieve tabs for teams of which you are a member.

Tabs _Conversations_ and _Files_ are present in every team and therefore not included in the list of available tabs.

## Examples
  
List all tabs in a Microsoft Teams channel.

```sh
m365 teams tab list --teamId 00000000-0000-0000-0000-000000000000 --channelId 19:00000000000000000000000000000000@thread.skype
```

Include all the values from the tab configuration and associated teams app.

```sh
m365 teams tab list --teamId 00000000-0000-0000-0000-000000000000 --channelId 19:00000000000000000000000000000000@thread.skype --output json
```

## Response

<Tabs>
  <TabItem value="JSON">

  ``` json
  [
    {
      "id": "34991fbf-59f4-48d9-b094-b9d64d550e23",
      "displayName": "My Contoso Tab",
      "webUrl": "https://teams.microsoft.com/l/entity/1542629c-01b3-4a6d-8f76-1938b779e48d/EXAMPLE_SECRET_VALUE_PLACEHOLDER?webUrl=https%3a%2f%2fteams.contoso.ai%2fmsteams%2fcontent%2ftab%2fteam%3ftheme%3d%7btheme%7d&label=My%20Contoso%20Tab&context=%7b%0d%0a++%22canvasUrl%22%3a+%22https%3a%2f%2fteams.contoso.ai%2fmsteams%2fcontent%2ftab%2fteam%3ftheme%3d%7btheme%7d%22%2c%0d%0a++%22channelId%22%3a+%2219%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.tacv2%22%2c%0d%0a++%22subEntityId%22%3a+null%0d%0a%7d&groupId=aee5a2c9-b1df-45ac-9964-c708e760a045&tenantId=92e59666-257b-49c3-b1fa-1bae8107f6ba",
      "configuration": {
        "entityId": "surveys_list:19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@thread.tacv2:ps67c9jyf3a30j2j5eum72",
        "contentUrl": "https://teams.contoso.ai/msteams/content/tab/team?theme={theme}",
        "removeUrl": "https://teams.contoso.ai/msteams/content/tabdelete?theme={theme}",
        "websiteUrl": "https://teams.contoso.ai/msteams/content/tab/team?theme={theme}",
        "dateAdded": "2022-10-31T12:17:58.632Z"
      },
      "teamsApp": {
        "id": "1542629c-01b3-4a6d-8f76-1938b779e48d",
        "externalId": null,
        "displayName": "My Contoso Tab",
        "distributionMethod": "store"
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ``` text
  displayName  : My Contoso Tab
  id           : 34991fbf-59f4-48d9-b094-b9d64d550e23
  teamsAppTabId: 1542629c-01b3-4a6d-8f76-1938b779e48d
  ```

  </TabItem>
  <TabItem value="CSV">

  ``` text
  id,displayName,teamsAppTabId
  34991fbf-59f4-48d9-b094-b9d64d550e23,My Contoso Tab,1542629c-01b3-4a6d-8f76-1938b779e48d
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams tab list --teamId "aee5a2c9-b1df-45ac-9964-c708e760a045" --channelId "19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@thread.tacv2"

  Date: 1/3/2023

  ## Wiki (34991fbf-59f4-48d9-b094-b9d64d550e23)

  Property | Value
  ---------|-------
  id | 34991fbf-59f4-48d9-b094-b9d64d550e23
  displayName | My Contoso Tab
  webUrl | https://teams.microsoft.com/l/entity/1542629c-01b3-4a6d-8f76-1938b779e48d/EXAMPLE_SECRET_VALUE_PLACEHOLDER?webUrl=https%3a%2f%2fteams.contoso.ai%2fmsteams%2fcontent%2ftab%2fteam%3ftheme%3d%7btheme%7d&label=My%20Contoso%20Tab&context=%7b%0d%0a++%22canvasUrl%22%3a+%22https%3a%2f%2fteams.contoso.ai%2fmsteams%2fcontent%2ftab%2fteam%3ftheme%3d%7btheme%7d%22%2c%0d%0a++%22channelId%22%3a+%2219%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.tacv2%22%2c%0d%0a++%22subEntityId%22%3a+null%0d%0a%7d&groupId=aee5a2c9-b1df-45ac-9964-c708e760a045&tenantId=92e59666-257b-49c3-b1fa-1bae8107f6ba
  teamsAppTabId | 1542629c-01b3-4a6d-8f76-1938b779e48d
  ```

  </TabItem>
</Tabs>
