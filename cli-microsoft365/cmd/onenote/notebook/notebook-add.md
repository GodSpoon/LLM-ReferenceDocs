-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# onenote notebook add

Create a new OneNote notebook.

## Usage

```sh
m365 onenote notebook add [options]
```

## Options

```md definition-list
`-n, --name <name>`
: Name of the notebook. Notebook names must be unique. The name cannot contain more than 128 characters or contain the following characters: `?*/:<>`

`--userId [userId]`
: Id of the user. Specify either `userId`, `userName`, `groupId`, `groupName` or `webUrl`, but not multiple.

`--userName [userName]`
: Name of the user. Specify either `userId`, `userName`, `groupId`, `groupName` or `webUrl`, but not multiple.

`--groupId [groupId]`
: Id of the SharePoint group. Specify either `userId`, `userName`, `groupId`, `groupName` or `webUrl`, but not multiple.

`--groupName [groupName]`
: Name of the SharePoint group. Specify either `userId`, `userName`, `groupId`, `groupName` or `webUrl`, but not multiple.

`-u, --webUrl [webUrl]`
: URL of the SharePoint site. Specify either `userId`, `userName`, `groupId`, `groupName` or `webUrl`, but not multiple.
```

<Global />

## Examples

Create a Microsoft OneNote notebook for the currently logged in user

```sh
m365 onenote notebook add --name "Private Notebook"
```

Create a Microsoft OneNote notebook in a group specified by id.

```sh
m365 onenote notebook add --name "Private Notebook" --groupId 233e43d0-dc6a-482e-9b4e-0de7a7bce9b4
```

Create a Microsoft OneNote notebook in a group specified by displayName.

```sh
m365 onenote notebook add --name "Private Notebook" --groupName "MyGroup"
```

Create a Microsoft OneNote notebook for a user specified by name

```sh
m365 onenote notebook add --name "Private Notebook" --userName user1@contoso.onmicrosoft.com
```

Create a Microsoft OneNote notebook for a user specified by id

```sh
m365 onenote notebook add --name "Private Notebook" --userId 2609af39-7775-4f94-a3dc-0dd67657e900
```

Creates a Microsoft OneNote notebooks for a site

```sh
 m365 onenote notebook add --name "Private Notebook" --webUrl https://contoso.sharepoint.com/sites/testsite
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "1-08554ffd-b769-4a4a-9563-faaa3191f253",
    "self": "https://graph.microsoft.com/v1.0/users/fe36f75e-c103-410b-a18a-2bf6df06ac3a/onenote/notebooks/1-08554ffd-b769-4a4a-9563-faaa3191f253",
    "createdDateTime": "2024-04-05T17:58:27Z",
    "displayName": "Private Notebook",
    "lastModifiedDateTime": "2024-04-05T17:58:27Z",
    "isDefault": false,
    "userRole": "Owner",
    "isShared": false,
    "sectionsUrl": "https://graph.microsoft.com/v1.0/users/fe36f75e-c103-410b-a18a-2bf6df06ac3a/onenote/notebooks/1-08554ffd-b769-4a4a-9563-faaa3191f253/sections",
    "sectionGroupsUrl": "https://graph.microsoft.com/v1.0/users/fe36f75e-c103-410b-a18a-2bf6df06ac3a/onenote/notebooks/1-08554ffd-b769-4a4a-9563-faaa3191f253/sectionGroups",
    "createdBy": {
      "user": {
        "id": "fe36f75e-c103-410b-a18a-2bf6df06ac3a",
        "displayName": "John Doe"
      }
    },
    "lastModifiedBy": {
      "user": {
        "id": "fe36f75e-c103-410b-a18a-2bf6df06ac3a",
        "displayName": "John Doe"
      }
    },
    "links": {
      "oneNoteClientUrl": {
        "href": "onenote:https://contoso-my.sharepoint.com/personal/john_contoso_onmicrosoft_com/Documents/Notebooks/Private Notebook"
      },
      "oneNoteWebUrl": {
        "href": "https://contoso-my.sharepoint.com/personal/john_contoso_onmicrosoft_com/Documents/Notebooks/Private Notebook"
      }
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  createdBy           : {"user":{"id":"fe36f75e-c103-410b-a18a-2bf6df06ac3a","displayName":"John Doe"}}
  createdDateTime     : 2024-04-05T17:58:36Z
  displayName         : Private Notebook
  id                  : 1-f4bba32b-9b3e-4892-8df4-931a15f7eb6f
  isDefault           : false
  isShared            : false
  lastModifiedBy      : {"user":{"id":"fe36f75e-c103-410b-a18a-2bf6df06ac3a","displayName":"John Doe"}}
  lastModifiedDateTime: 2024-04-05T17:58:36Z
  links               : {"oneNoteClientUrl":{"href":"onenote:https://contoso-my.sharepoint.com/personal/john_contoso_onmicrosoft_com/Documents/Notebooks/Private Notebook"},"oneNoteWebUrl":{"href":"https://contoso-my.sharepoint.com/personal/john_contoso_onmicrosoft_com/Documents/Notebooks/Private Notebook"}}
  sectionGroupsUrl    : https://graph.microsoft.com/v1.0/users/fe36f75e-c103-410b-a18a-2bf6df06ac3a/onenote/notebooks/1-f4bba32b-9b3e-4892-8df4-931a15f7eb6f/sectionGroups
  sectionsUrl         : https://graph.microsoft.com/v1.0/users/fe36f75e-c103-410b-a18a-2bf6df06ac3a/onenote/notebooks/1-f4bba32b-9b3e-4892-8df4-931a15f7eb6f/sections
  self                : https://graph.microsoft.com/v1.0/users/fe36f75e-c103-410b-a18a-2bf6df06ac3a/onenote/notebooks/1-f4bba32b-9b3e-4892-8df4-931a15f7eb6f
  userRole            : Owner
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,self,createdDateTime,displayName,lastModifiedDateTime,isDefault,userRole,isShared,sectionsUrl,sectionGroupsUrl
  1-272a5791-2c95-45cf-b27d-7f68e07f6149,https://graph.microsoft.com/v1.0/users/fe36f75e-c103-410b-a18a-2bf6df06ac3a/onenote/notebooks/1-272a5791-2c95-45cf-b27d-7f68e07f6149,2024-04-05T18:00:28Z,Private Notebook,2024-04-05T18:00:28Z,,Owner,,https://graph.microsoft.com/v1.0/users/fe36f75e-c103-410b-a18a-2bf6df06ac3a/onenote/notebooks/1-272a5791-2c95-45cf-b27d-7f68e07f6149/sections,https://graph.microsoft.com/v1.0/users/fe36f75e-c103-410b-a18a-2bf6df06ac3a/onenote/notebooks/1-272a5791-2c95-45cf-b27d-7f68e07f6149/sectionGroups
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # onenote notebook add --name "Private Notebook"

  Date: 05/04/2024

  ## Private Notebook (1-fa279d79-4701-43a2-9593-c2abfbe6999f)

  Property | Value
  ---------|-------
  id | 1-fa279d79-4701-43a2-9593-c2abfbe6999f
  self | https://graph.microsoft.com/v1.0/users/fe36f75e-c103-410b-a18a-2bf6df06ac3a/onenote/notebooks/1-fa279d79-4701-43a2-9593-c2abfbe6999f
  createdDateTime | 2024-04-05T18:00:58Z
  displayName | Private Notebook
  lastModifiedDateTime | 2024-04-05T18:00:58Z
  isDefault | false
  userRole | Owner
  isShared | false
  sectionsUrl | https://graph.microsoft.com/v1.0/users/fe36f75e-c103-410b-a18a-2bf6df06ac3a/onenote/notebooks/1-fa279d79-4701-43a2-9593-c2abfbe6999f/sections
  sectionGroupsUrl | https://graph.microsoft.com/v1.0/users/fe36f75e-c103-410b-a18a-2bf6df06ac3a/onenote/notebooks/1-fa279d79-4701-43a2-9593-c2abfbe6999f/sectionGroups
  ```

  </TabItem>
</Tabs>
