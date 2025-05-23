-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo commandset get

Get a ListView Command Set that is added to a site

## Usage

```sh
m365 spo commandset get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Url of the site.

`-t, --title [title]`
: The title of the ListView Command Set. Specify either `title`, `id` or `clientSideComponentId`.

`-i, --id [id]`
: The id of the ListView Command Set. Specify either `title`, `id` or `clientSideComponentId`.

`-c, --clientSideComponentId [clientSideComponentId]`
: The id of the ListView Command Set. Specify either `title`, `id` or `clientSideComponentId`.

`-s, --scope [scope]`
: Scope of the ListView Command Set. Allowed values: `Site`, `Web`, `All`. Defaults to `All`.

`-p, --clientSideComponentProperties`
: Only output the client-side component properties.
```

<Global />

## Remarks

If the command finds multiple command sets with the specified title, it will prompt you to disambiguate which command set it should use, listing the discovered IDs.

This command can be used for retrieving a ListView Command Set from a specific site. To retrieve a ListView Command Set that's installed tenant-wide, view our dedicated [spo tenant commandset get](../tenant/tenant-commandset-get.mdx) command.

## Examples

Retrieves a ListView Command Set by title.

```sh
m365 spo commandset get --title "Some customizer" --webUrl https://contoso.sharepoint.com/sites/sales
```

Retrieves a ListView Command Set by id with scope 'Web'.

```sh
m365 spo commandset get --id 14125658-a9bc-4ddf-9c75-1b5767c9a337 --webUrl https://contoso.sharepoint.com/sites/sales --scope Web
```

Retrieves a ListView Command Set by clientSideComponentId with scope 'Site'.

```sh
m365 spo commandset get --clientSideComponentId c1cbd896-5140-428d-8b0c-4873be19f5ac --webUrl https://contoso.sharepoint.com/sites/sales --scope Site
```

Retrieves the client-side component properties of a ListView Command Set.

```sh
m365 spo commandset get --id 14125658-a9bc-4ddf-9c75-1b5767c9a337 --webUrl https://contoso.sharepoint.com/sites/sales --clientSideComponentProperties
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "ClientSideComponentId": "53dd6a38-1461-44e0-9bf0-14883316a316",
    "ClientSideComponentProperties": "{\"sampleTextOne\":\"One item is selected in the list.\", \"sampleTextTwo\":\"This command is always visible.\"}",
    "CommandUIExtension": null,
    "Description": null,
    "Group": null,
    "HostProperties": "",
    "Id": "bb26547d-c9b7-4ed1-b793-00cbe53388d6",
    "ImageUrl": null,
    "Location": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "Name": "{bb26547d-c9b7-4ed1-b793-00cbe53388d6}",
    "RegistrationId": "100",
    "RegistrationType": 1,
    "Rights": {
      "High": "0",
      "Low": "0"
    },
    "Scope": 3,
    "ScriptBlock": null,
    "ScriptSrc": null,
    "Sequence": 65536,
    "Title": "HelloWorld",
    "Url": null,
    "VersionOfUserCustomAction": "1.0.1.0"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  ClientSideComponentId        : 53dd6a38-1461-44e0-9bf0-14883316a316
  ClientSideComponentProperties: {"sampleTextOne":"One item is selected in the list.", "sampleTextTwo":"This command is always visible."}
  CommandUIExtension           : null
  Description                  : null
  Group                        : null
  HostProperties               :
  Id                           : bb26547d-c9b7-4ed1-b793-00cbe53388d6
  ImageUrl                     : null
  Location                     : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  Name                         : {bb26547d-c9b7-4ed1-b793-00cbe53388d6}
  RegistrationId               : 100
  RegistrationType             : 1
  Rights                       : {"High":"0","Low":"0"}
  Scope                        : 3
  ScriptBlock                  : null
  ScriptSrc                    : null
  Sequence                     : 65536
  Title                        : HelloWorld
  Url                          : null
  VersionOfUserCustomAction    : 1.0.1.0
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ClientSideComponentId,ClientSideComponentProperties,CommandUIExtension,Description,Group,HostProperties,Id,ImageUrl,Location,Name,RegistrationId,RegistrationType,Scope,ScriptBlock,ScriptSrc,Sequence,Title,Url,VersionOfUserCustomAction
  53dd6a38-1461-44e0-9bf0-14883316a316,"{""sampleTextOne"":""One item is selected in the list."", ""sampleTextTwo"":""This command is always visible.""}",,,,,bb26547d-c9b7-4ed1-b793-00cbe53388d6,,EXAMPLE_SECRET_VALUE_PLACEHOLDER,{bb26547d-c9b7-4ed1-b793-00cbe53388d6},100,1,3,,,65536,HelloWorld,,1.0.1.0
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo commandset get --webUrl "https://contoso.sharepoint.com/sites/sales" --id "bb26547d-c9b7-4ed1-b793-00cbe53388d6"

  Date: 16/05/2024

  ## HelloWorld (bb26547d-c9b7-4ed1-b793-00cbe53388d6)

  Property | Value
  ---------|-------
  ClientSideComponentId | 53dd6a38-1461-44e0-9bf0-14883316a316
  ClientSideComponentProperties | {"sampleTextOne":"One item is selected in the list.", "sampleTextTwo":"This command is always visible."}
  HostProperties |
  Id | bb26547d-c9b7-4ed1-b793-00cbe53388d6
  Location | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  Name | {bb26547d-c9b7-4ed1-b793-00cbe53388d6}
  RegistrationId | 100
  RegistrationType | 1
  Scope | 3
  Sequence | 65536
  Title | HelloWorld
  VersionOfUserCustomAction | 1.0.1.0
  ```

  </TabItem>
</Tabs>

### `clientSideComponentProperties` response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "sampleTextOne": "One item is selected in the list.",
    "sampleTextTwo": "This command is always visible."
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  sampleTextOne: One item is selected in the list.
  sampleTextTwo: This command is always visible.
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  sampleTextOne,sampleTextTwo
  One item is selected in the list.,This command is always visible.
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo commandset get --webUrl "https://contoso.sharepoint.com/sites/sales" --id "9a0674de-2f3d-4a26-ba79-62b460ddd327" --clientSideComponentProperties "true"

  Date: 15/05/2024

  Property | Value
  ---------|-------
  sampleTextOne | One item is selected in the list.
  sampleTextTwo | This command is always visible.
  ```

  </TabItem>
</Tabs>
