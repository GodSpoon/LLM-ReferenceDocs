-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams team list

Lists Microsoft Teams teams in the current tenant

## Usage

```sh
m365 teams team list [options]
```

## Options

```md definition-list
`-j, --joined`
: Show only teams that the user is a direct member of. Specify either `joined` or `associated` but not both.

`-a, --associated`
: Show only teams that the user is associated with. This includes teams with direct membership and shared channels. Specify either `joined` or `associated` but not both.

`--userId [userId]`
: The ID of the user. Specify either `userId` or `userName` but not both. Specify only when using `joined` or `associated` options.

`--userName [userName]`
: The user principal name of the user. Specify either `userId` or `userName` but not both. Specify only when using `joined` or `associated` options.
```

<Global />

## Remarks

:::note

To list `joined` or `associated` teams of another user, you have to be a Teams Administrator or use application permissions.

:::

You can only see the details or archived status of the Microsoft Teams you are a member of.

## Examples

List all Microsoft Teams in the tenant

```sh
m365 teams team list
```

List all Microsoft Teams teams you are a direct member of

```sh
m365 teams team list --joined
```

List all Microsoft Teams teams you are a direct member of or are associated with via a shared channel

```sh
m365 teams team list --associated
```

List all Microsoft Teams teams another user is member of

```sh
m365 teams team list --joined --userName john.doe@contoso.com
```

List all Microsoft Teams teams where another user is a direct member of or is associated with via a shared channel

```sh
m365 teams team list --associated --userId e3aca2a8-625a-449b-bb86-cfa84c5d08de
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "5dc7ba76-b9aa-4fdd-9e91-9fe7d0e8dca3",
      "createdDateTime": "2022-12-08T09:17:55.039Z",
      "displayName": "Architecture",
      "description": "Architecture Discussion",
      "internalId": "19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@thread.tacv2",
      "classification": null,
      "specialization": "none",
      "visibility": "public",
      "webUrl": "https://teams.microsoft.com/l/team/19:a5c6eccad3fb401997756a1501d561aa%40thread.skype/conversations?groupId=8090c93e-ba7c-433e-9f39-08c7ba07c0b3&tenantId=dcd219dd-bc68-4b9b-bf0b-4a33a796be35",
      "isArchived": false,
      "isMembershipLimitedToOwners": false,
      "discoverySettings": {
        "showInTeamsSearchAndSuggestions": true
      },
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
        "allowUserEditMessages": false,
        "allowUserDeleteMessages": false,
        "allowOwnerDeleteMessages": false,
        "allowTeamMentions": true,
        "allowChannelMentions": true
      },
      "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": false
      },
      "summary": {
        "ownersCount": 1,
        "membersCount": 1,
        "guestsCount": 0
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    displayName   isArchived  description
  ------------------------------------  ------------  ----------  -----------------------
  5dc7ba76-b9aa-4fdd-9e91-9fe7d0e8dca3  Architecture  false       Architecture Discussion
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,createdDateTime,displayName,description,internalId,specialization,visibility,webUrl,isArchived,isMembershipLimitedToOwners
  5dc7ba76-b9aa-4fdd-9e91-9fe7d0e8dca3,2022-12-08T09:17:55.039Z,Architecture,Architecture Discussion,19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@thread.tacv2,none,public,https://teams.microsoft.com/l/team/19:a5c6eccad3fb401997756a1501d561aa%40thread.skype/conversations?groupId=8090c93e-ba7c-433e-9f39-08c7ba07c0b3&tenantId=dcd219dd-bc68-4b9b-bf0b-4a33a796be35,,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams team list --joined "true"

  Date: 1/3/2023

  ## Architecture (5dc7ba76-b9aa-4fdd-9e91-9fe7d0e8dca3)

  Property | Value
  ---------|-------
  id | 5dc7ba76-b9aa-4fdd-9e91-9fe7d0e8dca3
  createdDateTime | 2022-12-08T09:17:55.039Z
  displayName | Architecture
  description | Architecture Discussion
  internalId | 19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@thread.tacv2
  specialization | none
  visibility | public
  webUrl | https://teams.microsoft.com/l/team/19:a5c6eccad3fb401997756a1501d561aa%40thread.skype/conversations?groupId=8090c93e-ba7c-433e-9f39-08c7ba07c0b3&tenantId=dcd219dd-bc68-4b9b-bf0b-4a33a796be35
  isArchived | false
  isMembershipLimitedToOwners | false
  ```

  </TabItem>
</Tabs>
