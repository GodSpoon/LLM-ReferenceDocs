-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# onenote notebook list

Retrieve a list of notebooks.

## Usage

```sh
m365 onenote notebook list [options]
```

## Options

```md definition-list
`--userId [userId]`
: Id of the user. Use either userId or userName, but not both.

`--userName [userName]`
: Name of the user. Use either userId or userName, but not both.

`--groupId [groupId]`
: Id of the SharePoint group. Use either groupName or groupId, but not both

`--groupName [groupName]`
: Name of the SharePoint group. Use either groupName or groupId, but not both.

`-u, --webUrl [webUrl]`
: URL of the SharePoint site.
```

<Global />

## Examples

List Microsoft OneNote notebooks for the currently logged in user

```sh
m365 onenote notebook list
```

List Microsoft OneNote notebooks in group 233e43d0-dc6a-482e-9b4e-0de7a7bce9b4

```sh
m365 onenote notebook list --groupId 233e43d0-dc6a-482e-9b4e-0de7a7bce9b4
```

List Microsoft OneNote notebooks in group My Group

```sh
m365 onenote notebook list --groupName "MyGroup"
```

List Microsoft OneNote notebooks from a user by user name

```sh
m365 onenote notebook list --userName user1@contoso.onmicrosoft.com
```

List Microsoft OneNote notebooks for user 2609af39-7775-4f94-a3dc-0dd67657e900

```sh
m365 onenote notebook list --userId 2609af39-7775-4f94-a3dc-0dd67657e900
```

List Microsoft OneNote notebooks for site https://contoso.sharepoint.com/sites/testsite

```sh
m365 onenote notebook list --webUrl https://contoso.sharepoint.com/sites/testsite
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "1-9cf762f6-b931-4035-8bf3-67c710887c5a",
      "self": "https://graph.microsoft.com/v1.0/users/0649d0bd-53dc-4e1d-a357-76f1d92d447b/onenote/notebooks/1-9cf762f6-b931-4035-8bf3-67c710887c5a",
      "createdDateTime": "2018-11-17T13:06:42Z",
      "displayName": "TeamsNotebook(Shared)",
      "lastModifiedDateTime": "2018-11-17T13:06:42Z",
      "isDefault": false,
      "userRole": "Owner",
      "isShared": false,
      "sectionsUrl": "https://graph.microsoft.com/v1.0/users/0649d0bd-53dc-4e1d-a357-76f1d92d447b/onenote/notebooks/1-9cf762f6-b931-4035-8bf3-67c710887c5a/sections",
      "sectionGroupsUrl": "https://graph.microsoft.com/v1.0/users/0649d0bd-53dc-4e1d-a357-76f1d92d447b/onenote/notebooks/1-9cf762f6-b931-4035-8bf3-67c710887c5a/sectionGroups",
      "createdBy": {
        "user": {
          "id": "0649d0bd-53dc-4e1d-a357-76f1d92d447b",
          "displayName": "John"
        }
      },
      "lastModifiedBy": {
        "user": {
          "id": "0649d0bd-53dc-4e1d-a357-76f1d92d447b",
          "displayName": "John"
        }
      },
      "links": {
        "oneNoteClientUrl": {
          "href": "onenote:https://contoso-my.sharepoint.com/personal/john_contoso_onmicrosoft_com/Documents/Notebooks/TeamsNotebook(Shared)"
        },
        "oneNoteWebUrl": {
          "href": "https://contoso-my.sharepoint.com/personal/john_contoso_onmicrosoft_com/Documents/Notebooks/TeamsNotebook(Shared)"
        }
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  createdDateTime: 2018-11-17T13:06:42Z
  displayName    : TeamsNotebook(Shared)
  id             : 1-9cf762f6-b931-4035-8bf3-67c710887c5a
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,self,createdDateTime,displayName,lastModifiedDateTime,isDefault,userRole,isShared,sectionsUrl,sectionGroupsUrl
  1-9cf762f6-b931-4035-8bf3-67c710887c5a,https://graph.microsoft.com/v1.0/users/0649d0bd-53dc-4e1d-a357-76f1d92d447b/onenote/notebooks/1-9cf762f6-b931-4035-8bf3-67c710887c5a,2018-11-17T13:06:42Z,TeamsNotebook(Shared),2018-11-17T13:06:42Z,,Owner,,https://graph.microsoft.com/v1.0/users/0649d0bd-53dc-4e1d-a357-76f1d92d447b/onenote/notebooks/1-9cf762f6-b931-4035-8bf3-67c710887c5a/sections,https://graph.microsoft.com/v1.0/users/0649d0bd-53dc-4e1d-a357-76f1d92d447b/onenote/notebooks/1-9cf762f6-b931-4035-8bf3-67c710887c5a/sectionGroups
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # onenote notebook list

  Date: 2023-05-22

  ## TeamsNotebook(Shared) (1-9cf762f6-b931-4035-8bf3-67c710887c5a)

  Property | Value
  ---------|-------
  id | 1-9cf762f6-b931-4035-8bf3-67c710887c5a
  self | https://graph.microsoft.com/v1.0/users/0649d0bd-53dc-4e1d-a357-76f1d92d447b/onenote/notebooks/1-9cf762f6-b931-4035-8bf3-67c710887c5a
  createdDateTime | 2018-11-17T13:06:42Z
  displayName | TeamsNotebook(Shared)
  lastModifiedDateTime | 2018-11-17T13:06:42Z
  isDefault | false
  userRole | Owner
  isShared | false
  sectionsUrl | https://graph.microsoft.com/v1.0/users/0649d0bd-53dc-4e1d-a357-76f1d92d447b/onenote/notebooks/1-9cf762f6-b931-4035-8bf3-67c710887c5a/sections
  sectionGroupsUrl | https://graph.microsoft.com/v1.0/users/0649d0bd-53dc-4e1d-a357-76f1d92d447b/onenote/notebooks/1-9cf762f6-b931-4035-8bf3-67c710887c5a/sectionGroups
  ```

  </TabItem>
</Tabs>

## More information

- List notebooks (MS Graph docs): [https://learn.microsoft.com/graph/api/onenote-list-notebooks?view=graph-rest-1.0&tabs=http](https://learn.microsoft.com/graph/api/onenote-list-notebooks?view=graph-rest-1.0&tabs=http)
