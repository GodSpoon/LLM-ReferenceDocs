-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo navigation node list

Lists nodes from the specified site navigation

## Usage

```sh
m365 spo navigation node list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Absolute URL of the site for which to retrieve navigation.

`-l, --location <location>`
: Navigation type to retrieve. Available options: `QuickLaunch`, `TopNavigationBar`.
```

<Global />

## Examples

Retrieve nodes from the top navigation.

```sh
m365 spo navigation node list --webUrl https://contoso.sharepoint.com/sites/team-a --location TopNavigationBar
```

Retrieve nodes from the quick launch.

```sh
m365 spo navigation node list --webUrl https://contoso.sharepoint.com/sites/team-a --location QuickLaunch
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "AudienceIds": [
        "5786b8e8-c495-4734-b345-756733960730"
      ],
      "CurrentLCID": 1033,
      "Id": 2032,
      "IsDocLib": true,
      "IsExternal": true,
      "IsVisible": true,
      "ListTemplateType": 0,
      "Title": "Navigation Link",
      "Url": "https://contoso.sharepoint.com"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Id    Title            Url
  ----  ---------------  ------------------------------
  2032  Navigation Link  https://contoso.sharepoint.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Id,Title,Url
  2032,Navigation Link,https://contoso.sharepoint.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo navigation node list --webUrl "https://contoso.sharepoint.com" --location "QuickLaunch"

  Date: 27/1/2023

  ## Home (1031)

  Property | Value
  ---------|-------
  CurrentLCID | 1033
  Id | 2032
  IsDocLib | true
  IsExternal | false
  IsVisible | true
  ListTemplateType | 0
  Title | Navigation Link
  Url | https://contoso.sharepoint.com
  ```

  </TabItem>
</Tabs>
