-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams team get

Gets information about the specified Microsoft Teams team

## Usage

```sh
m365 teams team get
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the Microsoft Teams team to retrieve information for. Specify either `id` or `name` but not both.

`-n, --name [name]`
: The display name of the Microsoft Teams team to retrieve information for. Specify either `id` or `name` but not both.
```

<Global />

## Examples

Get information about the Microsoft Teams team by id.

```sh
m365 teams team get --id 2eaf7dcd-7e83-4c3a-94f7-932a1299c844
```

Get information about Microsoft Teams team by name.

```sh
m365 teams team get --name "Team Name"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ``` json
  {
    "id": "2eaf7dcd-7e83-4c3a-94f7-932a1299c844",
    "createdDateTime": "2022-10-31T12:50:42.819Z",
    "displayName": "Team Name",
    "description": "Team Name Discussion",
    "internalId": "19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@thread.tacv2",
    "classification": null,
    "specialization": "none",
    "visibility": "public",
    "webUrl": "https://teams.microsoft.com/l/team/19%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.tacv2/conversations?groupId=2eaf7dcd-7e83-4c3a-94f7-932a1299c844&tenantId=92e59666-257b-49c3-b1fa-1bae8107f6ba",
    "isArchived": false,
    "isMembershipLimitedToOwners": false,
    "discoverySettings": {
      "showInTeamsSearchAndSuggestions": true
    },
    "summary": null,
    "memberSettings": {
      "allowCreateUpdateChannels": true,
      "allowCreatePrivateChannels": true,
      "allowDeleteChannels": true,
      "allowAddRemoveApps": true,
      "allowCreateUpdateRemoveTabs": true,
      "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": {
      "allowCreateUpdateChannels": false,
      "allowDeleteChannels": false
    },
    "messagingSettings": {
      "allowUserEditMessages": true,
      "allowUserDeleteMessages": true,
      "allowOwnerDeleteMessages": true,
      "allowTeamMentions": true,
      "allowChannelMentions": true
    },
    "funSettings": {
      "allowGiphy": true,
      "giphyContentRating": "moderate",
      "allowStickersAndMemes": true,
      "allowCustomMemes": true
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ``` text
  classification             : null
  createdDateTime            : 2022-10-31T12:50:42.819Z
  description                : Team Name Discussion
  discoverySettings          : {"showInTeamsSearchAndSuggestions":true}
  displayName                : Team Name
  funSettings                : {"allowGiphy":true,"giphyContentRating":"moderate","allowStickersAndMemes":true,"allowCustomMemes":true}
  guestSettings              : {"allowCreateUpdateChannels":false,"allowDeleteChannels":false}
  id                         : 2eaf7dcd-7e83-4c3a-94f7-932a1299c844
  internalId                 : 19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@thread.tacv2
  isArchived                 : false
  isMembershipLimitedToOwners: false
  memberSettings             : {"allowCreateUpdateChannels":true,"allowCreatePrivateChannels":true,"allowDeleteChannels":true,"allowAddRemoveApps":true,"allowCreateUpdateRemoveTabs":true,"allowCreateUpdateRemoveConnectors":true}
  messagingSettings          : {"allowUserEditMessages":true,"allowUserDeleteMessages":true,"allowOwnerDeleteMessages":true,"allowTeamMentions":true,"allowChannelMentions":true}
  specialization             : none
  summary                    : null
  visibility                 : public
  webUrl                     : https://teams.microsoft.com/l/team/19%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.tacv2/conversations?groupId=2eaf7dcd-7e83-4c3a-94f7-932a1299c844&tenantId=92e59666-257b-49c3-b1fa-1bae8107f6ba
  ```

  </TabItem>
  <TabItem value="CSV">

  ``` text
  id,createdDateTime,displayName,description,internalId,classification,specialization,visibility,webUrl,isArchived,isMembershipLimitedToOwners,discoverySettings,summary,memberSettings,guestSettings,messagingSettings,funSettings
  2eaf7dcd-7e83-4c3a-94f7-932a1299c844,2022-10-31T12:50:42.819Z,Team Name,Team Name Discussion,19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@thread.tacv2,,none,public,https://teams.microsoft.com/l/team/19%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.tacv2/conversations?groupId=2eaf7dcd-7e83-4c3a-94f7-932a1299c844&tenantId=92e59666-257b-49c3-b1fa-1bae8107f6ba,,,"{""showInTeamsSearchAndSuggestions"":true}",,"{""allowCreateUpdateChannels"":true,""allowCreatePrivateChannels"":true,""allowDeleteChannels"":true,""allowAddRemoveApps"":true,""allowCreateUpdateRemoveTabs"":true,""allowCreateUpdateRemoveConnectors"":true}","{""allowCreateUpdateChannels"":false,""allowDeleteChannels"":false}","{""allowUserEditMessages"":true,""allowUserDeleteMessages"":true,""allowOwnerDeleteMessages"":true,""allowTeamMentions"":true,""allowChannelMentions"":true}","{""allowGiphy"":true,""giphyContentRating"":""moderate"",""allowStickersAndMemes"":true,""allowCustomMemes"":true}"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams team get --name "Team Name"

  Date: 1/3/2023

  ## Team Name (2eaf7dcd-7e83-4c3a-94f7-932a1299c844)

  Property | Value
  ---------|-------
  id | 2eaf7dcd-7e83-4c3a-94f7-932a1299c844
  createdDateTime | 2022-06-17T08:49:40.953Z
  displayName | Team Name
  description | Team Name Discussion
  internalId | 19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@thread.tacv2
  classification | null
  specialization | none
  visibility | public
  webUrl | https://teams.microsoft.com/l/team/19%EXAMPLE_SECRET_VALUE_PLACEHOLDER%40thread.tacv2/conversations?groupId=2eaf7dcd-7e83-4c3a-94f7-932a1299c844&tenantId=92e59666-257b-49c3-b1fa-1bae8107f6ba
  isArchived | false
  isMembershipLimitedToOwners | false
  summary | null
  ```

  </TabItem>
</Tabs>
