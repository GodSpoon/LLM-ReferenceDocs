-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo folder add

Creates a folder within a parent folder

## Usage

```sh
m365 spo folder add [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the folder will be created.

`-p, --parentFolderUrl <parentFolderUrl>`
: The server- or site-relative decoded URL of the parent folder.

`-n, --name <name>`
: Name of the new folder to be created.

`--color [color]`
: Visual color of the folder. Valid values are a color name or a number. Check remarks for more info.

`--ensureParentFolders [ensureParentFolders]`
: Ensure that the parent folder path is available. Any missing folders will be created recursively.
```

<Global />

## Remarks

When you specify a value for `color`, consider the following:

| Color        | Number value | String value |
|--------------|--------------|--------------|
| Yellow       | 0            | yellow       |
| Dark red     | 1            | darkRed      |
| Dark orange  | 2            | darkOrange   |
| Dark green   | 3            | darkGreen    |
| Dark teal    | 4            | darkTeal     |
| Dark blue    | 5            | darkBlue     |
| Dark purple  | 6            | darkPurple   |
| Dark pink    | 7            | darkPink     |
| Grey         | 8            | grey         |
| Light red    | 9            | lightRed     |
| Light orange | 10           | lightOrange  |
| Light green  | 11           | lightGreen   |
| Light teal   | 12           | lightTeal    |
| Light blue   | 13           | lightBlue    |
| Light purple | 14           | lightPurple  |
| Light pink   | 15           | lightPink    |

## Examples

Creates folder in a specific library within the site.

```sh
m365 spo folder add --webUrl https://contoso.sharepoint.com/sites/project-x --parentFolderUrl '/Shared Documents' --name 'My Folder Name'
```

Creates folder in a specific folder within the site.

```sh
m365 spo folder add --webUrl https://contoso.sharepoint.com/sites/project-x --parentFolderUrl '/sites/project-x/Shared Documents/Reports' --name 'Financial reports'
```

Create a folder with a dark blue look

```sh
m365 spo folder add --webUrl https://contoso.sharepoint.com --parentFolder '/ProjectFiles' --name 'Project-x' --color 5
```

Create a folder with a light teal look

```sh
m365 spo folder add --webUrl https://contoso.sharepoint.com --url '/ProjectFiles/Project-x' --color lightTeal
```

Create a folder and make sure that any missing folders specified as parent folders are created.

```sh
m365 spo folder add --webUrl https://contoso.sharepoint.com/sites/project-x --parentFolderUrl '/Projects/2024/Q1/Reports' --name Financial --ensureParentFolders
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Exists": true,
    "ExistsAllowThrowForPolicyFailures": true,
    "IsWOPIEnabled": false,
    "ItemCount": 0,
    "Name": "My new folder",
    "ProgID": null,
    "ServerRelativeUrl": "/sites/project-x/Shared Documents/My new folder",
    "TimeCreated": "2023-07-20T19:29:16Z",
    "TimeLastModified": "2023-07-20T19:29:16Z",
    "UniqueId": "94a9aa56-f0b5-4268-941f-737c841ba7c7",
    "WelcomePage": ""
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Exists                           : true
  ExistsAllowThrowForPolicyFailures: true
  IsWOPIEnabled                    : false
  ItemCount                        : 0
  Name                             : My new folder
  ProgID                           : null
  ServerRelativeUrl                : /sites/project-x/Shared Documents/My new folder
  TimeCreated                      : 2023-07-20T19:29:16Z
  TimeLastModified                 : 2023-07-20T19:29:16Z
  UniqueId                         : 94a9aa56-f0b5-4268-941f-737c841ba7c7
  WelcomePage                      :
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Exists,ExistsAllowThrowForPolicyFailures,IsWOPIEnabled,ItemCount,Name,ServerRelativeUrl,TimeCreated,TimeLastModified,UniqueId,WelcomePage
  1,1,,0,My new folder,/sites/project-x/Shared Documents/My new folder,2023-07-20T19:29:16Z,2023-07-20T19:29:16Z,94a9aa56-f0b5-4268-941f-737c841ba7c7,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo folder add --webUrl "https://contoso.sharepoint.com/sites/project-x" --parentFolderUrl "/sites/project-x/Shared Documents" --name "My new folder"

  Date: 20/7/2023

  ## My new folder (94a9aa56-f0b5-4268-941f-737c841ba7c7)

  Property | Value
  ---------|-------
  Exists | true
  ExistsAllowThrowForPolicyFailures | true
  IsWOPIEnabled | false
  ItemCount | 0
  Name | My new folder
  ServerRelativeUrl | /sites/project-x/Shared Documents/My new folder
  TimeCreated | 2023-07-20T19:29:16Z
  TimeLastModified | 2023-07-20T19:29:16Z
  UniqueId | 94a9aa56-f0b5-4268-941f-737c841ba7c7
  WelcomePage |
  ```

  </TabItem>
</Tabs>
