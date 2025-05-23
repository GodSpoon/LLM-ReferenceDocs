-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# onenote page list

Retrieve a list of OneNote pages.

## Usage

```sh
m365 onenote page list [options]
```

## Options

```md definition-list
`--userId [userId]`
: Id of the user. Use either `userId`, `userName`, `groupId`, `groupName` or `webUrl` but not multiple.

`--userName [userName]`
: Name of the user. Use either `userId`, `userName`, `groupId`, `groupName` or `webUrl` but not multiple.

`--groupId [groupId]`
: Id of the SharePoint group. Use either `userId`, `userName`, `groupId`, `groupName` or `webUrl` but not multiple.

`--groupName [groupName]`
: Name of the SharePoint group. Use either `userId`, `userName`, `groupId`, `groupName` or `webUrl` but not multiple.

`-u, --webUrl [webUrl]`
: URL of the SharePoint site. Use either `userId`, `userName`, `groupId`, `groupName` or `webUrl` but not multiple.
```

<Global />

## Remarks

When we don't specify either `userId`, `userName`, `groupId`, `groupName` or `webUrl`, the OneNote pages will be retrieved of the currently logged in user.

## Examples

List Microsoft OneNote pages for the currently logged in user.

```sh
m365 onenote page list
```

List Microsoft OneNote pages in a specific group specified by id.

```sh
m365 onenote page list --groupId 233e43d0-dc6a-482e-9b4e-0de7a7bce9b4
```

List Microsoft OneNote pages in a specific group specified by name.

```sh
m365 onenote page list --groupName "MyGroup"
```

List Microsoft OneNote pages for a specific user specified by name.

```sh
m365 onenote page list --userName user1@contoso.onmicrosoft.com
```

List Microsoft OneNote pages for a specific user specified by id.

```sh
m365 onenote page list --userId 2609af39-7775-4f94-a3dc-0dd67657e900
```

List Microsoft OneNote pages for a specific site.

```sh
m365 onenote page list --webUrl https://contoso.sharepoint.com/sites/testsite
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "1-a26aaec43ed348bd82edf4eb44e73d6c!68-3eb21088-b613-4698-98df-92a7d34e0678",
      "self": "https://graph.microsoft.com/v1.0/users/john@contoso.com/onenote/pages/1-a26aaec43ed348bd82edf4eb44e73d6c!68-3eb21088-b613-4698-98df-92a7d34e0678",
      "createdDateTime": "2023-01-07T10:57:15Z",
      "title": "Page B",
      "createdByAppId": "",
      "contentUrl": "https://graph.microsoft.com/v1.0/users/john@contoso.com/onenote/pages/1-a26aaec43ed348bd82edf4eb44e73d6c!68-3eb21088-b613-4698-98df-92a7d34e0678/content",
      "lastModifiedDateTime": "2023-01-07T10:57:17Z",
      "links": {
        "oneNoteClientUrl": {
          "href": "onenote:https://contoso-my.sharepoint.com/personal/john_contoso_com/Documents/Notitieblokken/My%20OneNote/Test.one#Page%20B&section-id=94cacaca-d6b5-428d-b967-d3cf01b95c28&page-id=46a1b220-7ffd-4512-a571-55322097c08d&end"
        },
        "oneNoteWebUrl": {
          "href": "https://contoso-my.sharepoint.com/personal/john_contoso_com/Documents/Notitieblokken/My%20OneNote?wd=target%28Test.one%7C94cacaca-d6b5-428d-b967-d3cf01b95c28%2FPage%20B%7C46a1b220-7ffd-4512-a571-55322097c08d%2F%29"
        }
      },
      "parentSection": {
        "id": "1-3eb21088-b613-4698-98df-92a7d34e0678",
        "displayName": "Test",
        "self": "https://graph.microsoft.com/v1.0/users/john@contoso.com/onenote/sections/1-3eb21088-b613-4698-98df-92a7d34e0678"
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  createdDateTime       title   id
  --------------------  ------  --------------------------------------------------------------------------
  2023-01-07T10:57:15Z  Page B  1-a26aaec43ed348bd82edf4eb44e73d6c!68-3eb21088-b613-4698-98df-92a7d34e0678
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  createdDateTime,title,id
  2023-01-07T10:57:15Z,Page B,1-a26aaec43ed348bd82edf4eb44e73d6c!68-3eb21088-b613-4698-98df-92a7d34e0678
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # onenote page list --userName "john.doe@contoso.onmicrosoft.com"

  Date: 07/01/2023

  ## Page A (1-a26aaec43ed348bd82edf4eb44e73d6c!14-3eb21088-b613-4698-98df-92a7d34e0678)

  ## Page B (1-a26aaec43ed348bd82edf4eb44e73d6c!68-3eb21088-b613-4698-98df-92a7d34e0678)

  Property | Value
  ---------|-------
  id | 1-a26aaec43ed348bd82edf4eb44e73d6c!68-3eb21088-b613-4698-98df-92a7d34e0678
  self | https://graph.microsoft.com/v1.0/users/john@contoso.com/onenote/pages/1-a26aaec43ed348bd82edf4eb44e73d6c!68-3eb21088-b613-4698-98df-92a7d34e0678
  createdDateTime | 2023-01-07T10:57:15Z
  title | Page B
  createdByAppId |
  contentUrl | https://graph.microsoft.com/v1.0/users/john@contoso.com/onenote/pages/1-a26aaec43ed348bd82edf4eb44e73d6c!68-3eb21088-b613-4698-98df-92a7d34e0678/content
  lastModifiedDateTime | 2023-01-07T10:57:17Z
  ```

  </TabItem>
</Tabs>
