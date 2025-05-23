-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams tab get

Gets information about the specified Microsoft Teams tab

## Usage

```sh
m365 teams tab get [options]
```

## Options

```md definition-list
`--teamId [teamId]`
: The ID of the Microsoft Teams team where the tab is located. Specify either teamId or teamName but not both.

`--teamName [teamName]`
: The display name of the Microsoft Teams team where the tab is located. Specify either teamId or teamName but not both.

`--channelId [channelId]`
: The ID of the Microsoft Teams channel where the tab is located. Specify either channelId or channelName but not both.

`--channelName [channelName]`
: The display name of the Microsoft Teams channel where the tab is located. Specify either channelId or channelName but not both.

`-i, --id [id]`
: The ID of the Microsoft Teams tab. Specify either `id` or `name` but not both.

`-n, --name [name]`
: The display name of the Microsoft Teams tab. Specify either `id` or `name` but not both.
```

<Global />

## Remarks

You can only retrieve tabs for teams of which you are a member.

## Examples

Get a Microsoft Teams Tab with the specified ID.

```sh
m365 teams tab get --teamId 00000000-0000-0000-0000-000000000000 --channelId 19:00000000000000000000000000000000@thread.skype --id 1432c9da-8b9c-4602-9248-e0800f3e3f07
```

Get a Microsoft Teams Tab with the specified name.

```sh
m365 teams tab get --teamName "Team Name" --channelName "Channel Name" --name "Tab Name"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ``` json
  {
    "id": "34991fbf-59f4-48d9-b094-b9d64d550e23",
    "displayName": "SharePoint",
    "webUrl": "https://teams.microsoft.com/l/entity/1542629c-01b3-4a6d-8f76-1938b779e48d/EXAMPLE_SECRET_VALUE_PLACEHOLDER?webUrl=https%3a%2f%2fteams.contoso.ai%2fmsteams%2fcontent%2ftab%2fteam%3ftheme%3d%7btheme%7d&label=My%20Contoso%20Tab&context=%7b%0d%0a++%22canvasUrl%22%3a+%22https%3a%2f%2fteams.contoso.ai%2fmsteams%2fcontent%2ftab%2fteam%3ftheme%3d%7btheme%7d%22%2c%0d%0a++%22channelId%22%3a+%2219%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.tacv2%22%2c%0d%0a++%22subEntityId%22%3a+null%0d%0a%7d&groupId=aee5a2c9-b1df-45ac-9964-c708e760a045&tenantId=92e59666-257b-49c3-b1fa-1bae8107f6ba",
    "configuration": {
      "entityId": "sharepointtab_0.9493973734805403",
      "contentUrl": "https://contoso.sharepoint.com/sites/EmergencyResponse/_layouts/15/filebrowser.aspx?app=teamsfile&scenario=teamsPage&fileBrowser=%7B%22sdk%22%3A%221.0%22%2C%22entry%22%3A%7B%22sharePoint%22%3A%7B%22byPath%22%3A%7B%22folder%22%3A%22%2Fsites%2FEmergencyResponse%2FShared+Documents%22%7D%7D%2C%22view%22%3A%7B%22id%22%3A%223fed0165-c65f-4633-96d8-78aa513733ea%22%7D%7D%7D&theme={theme}",
      "removeUrl": null,
      "websiteUrl": "https://contoso.sharepoint.com/sites/EmergencyResponse/Shared Documents/Forms/AllItems.aspx",
      "dateAdded": "2022-10-31T12:17:58.632Z"
    },
    "teamsApp": {
      "id": "1542629c-01b3-4a6d-8f76-1938b779e48d",
      "externalId": null,
      "displayName": "SharePoint",
      "distributionMethod": "store"
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ``` text
  configuration: {"entityId":"sharepointtab_0.9493973734805403","contentUrl":"https://contoso.sharepoint.com/sites/EmergencyResponse/_layouts/15/filebrowser.aspx?app=teamsfile&scenario=teamsPage&fileBrowser=%7B%22sdk%22%3A%221.0%22%2C%22entry%22%3A%7B%22sharePoint%22%3A%7B%22byPath%22%3A%7B%22folder%22%3A%22%2Fsites%2FEmergencyResponse%2FShared+Documents%22%7D%7D%2C%22view%22%3A%7B%22id%22%3A%223fed0165-c65f-4633-96d8-78aa513733ea%22%7D%7D%7D&theme={theme}","removeUrl":null,"websiteUrl":"https://contoso.sharepoint.com/sites/EmergencyResponse/Shared Documents/Forms/AllItems.aspx","dateAdded":"2022-10-31T12:17:58.632Z"}
  displayName  : SharePoint
  id           : 34991fbf-59f4-48d9-b094-b9d64d550e23
  teamsApp     : {"id":"1542629c-01b3-4a6d-8f76-1938b779e48d","externalId":null,"displayName":"SharePoint","distributionMethod":"store"}
  webUrl       : https://teams.microsoft.com/l/entity/1542629c-01b3-4a6d-8f76-1938b779e48d/EXAMPLE_SECRET_VALUE_PLACEHOLDER?webUrl=https%3a%2f%2fteams.contoso.ai%2fmsteams%2fcontent%2ftab%2fteam%3ftheme%3d%7btheme%7d&label=My%20Contoso%20Tab&context=%7b%0d%0a++%22canvasUrl%22%3a+%22https%3a%2f%2fteams.contoso.ai%2fmsteams%2fcontent%2ftab%2fteam%3ftheme%3d%7btheme%7d%22%2c%0d%0a++%22channelId%22%3a+%2219%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.tacv2%22%2c%0d%0a++%22subEntityId%22%3a+null%0d%0a%7d&groupId=aee5a2c9-b1df-45ac-9964-c708e760a045&tenantId=92e59666-257b-49c3-b1fa-1bae8107f6ba
  ```

  </TabItem>
  <TabItem value="CSV">

  ``` text
  id,displayName,webUrl
  34991fbf-59f4-48d9-b094-b9d64d550e23,1542629c-01b3-4a6d-8f76-1938b779e48d,SharePoint,https://teams.microsoft.com/l/entity/1542629c-01b3-4a6d-8f76-1938b779e48d/EXAMPLE_SECRET_VALUE_PLACEHOLDER?webUrl=https%3a%2f%2fteams.contoso.ai%2fmsteams%2fcontent%2ftab%2fteam%3ftheme%3d%7btheme%7d&label=My%20Contoso%20Tab&context=%7b%0d%0a++%22canvasUrl%22%3a+%22https%3a%2f%2fteams.contoso.ai%2fmsteams%2fcontent%2ftab%2fteam%3ftheme%3d%7btheme%7d%22%2c%0d%0a++%22channelId%22%3a+%2219%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.tacv2%22%2c%0d%0a++%22subEntityId%22%3a+null%0d%0a%7d&groupId=aee5a2c9-b1df-45ac-9964-c708e760a045&tenantId=92e59666-257b-49c3-b1fa-1bae8107f6ba
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams tab get --teamId "aee5a2c9-b1df-45ac-9964-c708e760a045" --channelId "19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@thread.tacv2" --id "34991fbf-59f4-48d9-b094-b9d64d550e23"

  Date: 1/3/2023

  ## SharePoint (34991fbf-59f4-48d9-b094-b9d64d550e23)

  Property | Value
  ---------|-------
  id | 34991fbf-59f4-48d9-b094-b9d64d550e23
  displayName | SharePoint
  webUrl | https://teams.microsoft.com/l/entity/1542629c-01b3-4a6d-8f76-1938b779e48d/EXAMPLE_SECRET_VALUE_PLACEHOLDER?webUrl=https%3a%2f%2fteams.contoso.ai%2fmsteams%2fcontent%2ftab%2fteam%3ftheme%3d%7btheme%7d&label=My%20Contoso%20Tab&context=%7b%0d%0a++%22canvasUrl%22%3a+%22https%3a%2f%2fteams.contoso.ai%2fmsteams%2fcontent%2ftab%2fteam%3ftheme%3d%7btheme%7d%22%2c%0d%0a++%22channelId%22%3a+%2219%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.tacv2%22%2c%0d%0a++%22subEntityId%22%3a+null%0d%0a%7d&groupId=aee5a2c9-b1df-45ac-9964-c708e760a045&tenantId=92e59666-257b-49c3-b1fa-1bae8107f6ba
  ```

  </TabItem>
</Tabs>
