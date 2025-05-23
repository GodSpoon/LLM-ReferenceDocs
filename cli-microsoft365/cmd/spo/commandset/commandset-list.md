-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo commandset list

Get a list of ListView Command Sets that are added to a site

## Usage

```sh
m365 spo commandset list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The url of the site.

`-s, --scope [scope]`
: Scope of the ListView Command Sets. Allowed values: `Site`, `Web`, `All`. Defaults to `All`.
```

<Global />

## Remarks

This command can be used for retrieving a list of ListView Command Sets from a specific site. To retrieve a list of ListView Command Sets that are installed tenant-wide, view our dedicated [spo tenant commandset list](../tenant/tenant-commandset-list.mdx) command.

## Examples

Retrieves a list of ListView Command Sets.

```sh
m365 spo commandset list --webUrl https://contoso.sharepoint.com/sites/sales
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
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
        "High": 0,
        "Low": 0
      },
      "Scope": 3,
      "ScriptBlock": null,
      "ScriptSrc": null,
      "Sequence": 65536,
      "Title": "HelloWorld",
      "Url": null,
      "VersionOfUserCustomAction": "1.0.1.0"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Id                                    Location                                           Name                                    Scope
  ------------------------------------  -------------------------------------------------  --------------------------------------  -----
  bb26547d-c9b7-4ed1-b793-00cbe53388d6  EXAMPLE_SECRET_VALUE_PLACEHOLDER  {bb26547d-c9b7-4ed1-b793-00cbe53388d6}  3    
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
  # spo commandset list --webUrl "https://contoso.sharepoint.com/sites/Marketing"

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
