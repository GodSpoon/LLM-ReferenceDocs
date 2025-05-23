-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo navigation node get

Gets information about a specific navigation node.

## Usage

```sh
m365 spo navigation node get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Absolute URL of the site.

`--id <id>`
: Id of the navigation node.
```

<Global />

## Examples

Retrieve information for a specific navigation node.

```sh
m365 spo navigation node get --webUrl https://contoso.sharepoint.com/sites/team-a --id 2209
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "AudienceIds": [
      "0d718612-8407-4d6b-833c-6891a553354f",
      "f864446f-b4d7-475a-a2ba-1080c6474020"
    ],
    "CurrentLCID": 1033,
    "Id": 2209,
    "IsDocLib": true,
    "IsExternal": false,
    "IsVisible": true,
    "ListTemplateType": 100,
    "Title": "Work Status",
    "Url": "/sites/team-a/Lists/Work Status/AllItems.aspx"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  AudienceIds     : ["0d718612-8407-4d6b-833c-6891a553354f", "f864446f-b4d7-475a-a2ba-1080c6474020"]
  CurrentLCID     : 1033
  Id              : 2209
  IsDocLib        : true
  IsExternal      : false
  IsVisible       : true
  ListTemplateType: 100
  Title           : Work Status
  Url             : /sites/team-a/Lists/Work Status/AllItems.aspx
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  AudienceIds,CurrentLCID,Id,IsDocLib,IsExternal,IsVisible,ListTemplateType,Title,Url
  [""0d718612-8407-4d6b-833c-6891a553354f"", ""f864446f-b4d7-475a-a2ba-1080c6474020""],1033,2209,1,,1,100,Work Status,/sites/team-a/Lists/Work Status/AllItems.aspx
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo navigation node get --webUrl "https://contoso.sharepoint.com/sites/team-a" --id "2209"

  Date: 1/29/2023

  ## Work Status (2209)

  Property | Value
  ---------|-------
  CurrentLCID | 1033
  Id | 2209
  IsDocLib | true
  IsExternal | false
  IsVisible | true
  ListTemplateType | 100
  Title | Work Status
  Url | /sites/team-a/Lists/Work Status/AllItems.aspx
  ```

  </TabItem>
</Tabs>
