-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo sitescript add

Adds site script for use with site designs

## Usage

```sh
m365 spo sitescript add [options]
```

## Options

```md definition-list
`-t, --title <title>`
: Site script title

`-c, --content <content>`
: JSON string containing the site script

`-d, --description [description]`
: Site script description
```

<Global />

## Remarks

Each time you execute the `spo sitescript add` command, it will create a new site script with a unique ID. Before creating a site script, be sure that another script with the same name doesn't already exist.

## Examples

Create new site script for use with site designs. Script contents are stored in the `$script` variable

```sh
m365 spo sitescript add --title "Contoso" --description "Contoso theme script" --content $script
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Content": null,
    "ContentByteArray": null,
    "Description": "Contoso site script",
    "Id": "43d4ffa0-c7ee-4a97-91d7-db27e5b62de5",
    "IsSiteScriptPackage": false,
    "Title": "Contoso",
    "Version": 0
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Content            : null
  ContentByteArray   : null
  Description        : Contoso site script
  Id                 : 43d4ffa0-c7ee-4a97-91d7-db27e5b62de5
  IsSiteScriptPackage: false
  Title              : Contoso
  Version            : 0
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Description,Id,IsSiteScriptPackage,Title,Version
  Contoso site script,eeee7706-f8af-4ac0-b629-bcee87260c80,,Contoso,0
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo sitescript add --title "Contoso" --description "Contoso site script" --content "{
    "$schema": "https://developer.microsoft.com/json-schemas/sp/site-design-script-actions.schema.json",
    "actions": [
      {
        "verb": "activateSPFeature",
        "name": "SiteNotebook feature",
        "title": "SiteNotebook feature",
        "featureId": "43d4ffa0-c7ee-4a97-91d7-db27e5b62de5",
        "scope": "web"
      }
    ],
    "bindata": {},
    "version": 1
  }"

  Date: 2023-06-22

  ## Contoso (43d4ffa0-c7ee-4a97-91d7-db27e5b62de5)

  Property | Value
  ---------|-------
  Description | Contoso site script
  Id | 43d4ffa0-c7ee-4a97-91d7-db27e5b62de5
  IsSiteScriptPackage | false
  Title | Contoso
  Version | 0
  ```

  </TabItem>
</Tabs>

## More information

- SharePoint site design and site script overview: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)
