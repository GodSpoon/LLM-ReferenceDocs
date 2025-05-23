-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo tenant commandset add

Add a ListView Command Set as a tenant-wide extension

## Usage

```sh
m365 spo tenant commandset add [options]
```

## Options

```md definition-list
`-t, --title <title>`
: The title of the ListView Command Set.

`-l, --listType <listType>`
: The list or library type to register the ListView Command Set on. Allowed values `List` or `Library`.

`-i, --clientSideComponentId <clientSideComponentId>`
: The Client Side Component Id (GUID) of the ListView Command Set.

`-p, --clientSideComponentProperties [clientSideComponentProperties]`
: The Client Side Component properties of the ListView Command Set.

`-w, --webTemplate [webTemplate]`
: Optionally add a web template (e.g. STS#3, SITEPAGEPUBLISHING#0, etc) as a filter for what kind of sites the ListView Command Set is registered on.

`--location [location]`
: The location of the ListView Command Set. Allowed values `ContextMenu`, `CommandBar` or `Both`. Defaults to `CommandBar`.
```

<Global />

## Remarks

Running this command from the Windows Command Shell (cmd.exe) or PowerShell for Windows OS XP, 7, 8, 8.1 without bash installed might require additional formatting for command options that have JSON, XML, or JavaScript values because the command shell treats quotes differently. For example, this is how commandset user custom action can be created from the Windows cmd.exe:

```sh
m365 spo tenant commandset add --title "YourAppCustomizer" --clientSideComponentId b41916e7-e69d-467f-b37f-ff8ecf8f99f2 --clientSideComponentProperties '{\"testMessage\":\"Test message\"}'
```

Note, how the clientSideComponentProperties option has escaped double quotes `'{\"testMessage\":\"Test message\"}'` compared to execution from bash `'{"testMessage":"Test message"}'`.

:::warning[Escaping JSON in PowerShell]

When using the `--clientSideComponentProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

:::info

To use this command, you need to be a SharePoint Admin.

:::

This command can be used for configuring a tenant-wide ListView Command Set. To configure a ListView Command Set on a specific site, view our dedicated [spo commandset add](../commandset/commandset-add.mdx) command.

## Examples

Adds a ListView Command Set that's deployed tenant wide to CommandBars of Lists.

```sh
m365 spo tenant commandset add --title "Some customizer" --clientSideComponentId  799883f5-7962-4384-a10a-105adaec6ffc --listType List
```

Adds a ListView Command Set that is configured to the context menu of communication site libraries.

```sh
m365 spo tenant commandset  add --title "Some customizer" --clientSideComponentId  799883f5-7962-4384-a10a-105adaec6ffc --webTemplate "SITEPAGEPUBLISHING#0" --listType Library --location ContextMenu
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "FileSystemObjectType": 0,
    "Id": 4,
    "ServerRedirectedEmbedUri": null,
    "ServerRedirectedEmbedUrl": "",
    "ID": 4,
    "ContentTypeId": "0x00693E2C487575B448BD420C12CEAE7EFE",
    "Title": "Some ListView Command Set",
    "Modified": "2023-01-11T15:47:38Z",
    "Created": "2023-01-11T15:47:38Z",
    "AuthorId": 9,
    "EditorId": 9,
    "OData__UIVersionString": "1.0",
    "Attachments": false,
    "GUID": "14125658-a9bc-4ddf-9c75-1b5767c9a337",
    "ComplianceAssetId": null,
    "TenantWideExtensionComponentId": "7096cded-b83d-4eab-96f0-df477ed7c0bc",
    "TenantWideExtensionComponentProperties": "{\"testMessage\":\"Test message\"}",
    "TenantWideExtensionWebTemplate": null,
    "TenantWideExtensionListTemplate": 101,
    "TenantWideExtensionLocation": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "TenantWideExtensionSequence": 0,
    "TenantWideExtensionHostProperties": null,
    "TenantWideExtensionDisabled": false
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Attachments                           : false
  AuthorId                              : 9
  ComplianceAssetId                     : null
  ContentTypeId                         : 0x00693E2C487575B448BD420C12CEAE7EFE
  Created                               : 2023-01-11T15:47:38Z
  EditorId                              : 9
  FileSystemObjectType                  : 0
  GUID                                  : 14125658-a9bc-4ddf-9c75-1b5767c9a337
  Id                                    : 4
  ID                                    : 4
  Modified                              : 2023-01-11T15:47:38Z
  OData__UIVersionString                : 1.0
  ServerRedirectedEmbedUri              : null
  ServerRedirectedEmbedUrl              :
  TenantWideExtensionComponentId        : 7096cded-b83d-4eab-96f0-df477ed7c0bc
  TenantWideExtensionComponentProperties: {"testMessage":"Test message"}
  TenantWideExtensionDisabled           : false
  TenantWideExtensionHostProperties     : null
  TenantWideExtensionListTemplate       : 101
  TenantWideExtensionLocation           : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  TenantWideExtensionSequence           : 0
  TenantWideExtensionWebTemplate        : null
  Title                                 : Some ListView Command Set
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  FileSystemObjectType,Id,ServerRedirectedEmbedUri,ServerRedirectedEmbedUrl,ID,ContentTypeId,Title,Modified,Created,AuthorId,EditorId,OData__UIVersionString,Attachments,GUID,ComplianceAssetId,TenantWideExtensionComponentId,TenantWideExtensionComponentProperties,TenantWideExtensionWebTemplate,TenantWideExtensionListTemplate,TenantWideExtensionLocation,TenantWideExtensionSequence,TenantWideExtensionHostProperties,TenantWideExtensionDisabled
  0,4,,,4,0x00693E2C487575B448BD420C12CEAE7EFE,Some ListView Command Set,2023-01-11T15:47:38Z,2023-01-11T15:47:38Z,9,9,1.0,,14125658-a9bc-4ddf-9c75-1b5767c9a337,,7096cded-b83d-4eab-96f0-df477ed7c0bc,"{""testMessage"":""Test message""}",,101,EXAMPLE_SECRET_VALUE_PLACEHOLDER,0,,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo listitem add --webUrl "https://contoso.sharepoint.com/sites/appcatalog" --listUrl "/sites/appcatalog/Lists/TenantWideExtensions" --Title "Some ListView Command Set" --TenantWideExtensionComponentId "7096cded-b83d-4eab-96f0-df477ed7c0bc" --TenantWideExtensionLocation "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --TenantWideExtensionSequence "0" --TenantWideExtensionListTemplate "101" --TenantWideExtensionComponentProperties "{"testMessage":"Test message"}" --TenantWideExtensionWebTemplate "" --TenantWideExtensionDisabled "false" --verbose "false" --debug "false" --_ ""

  Date: 1/13/2023

  ## Some ListView Command Set (4)

  Property | Value
  ---------|-------
  FileSystemObjectType | 0
  Id | 4
  ServerRedirectedEmbedUri | null
  ServerRedirectedEmbedUrl |
  ID | 4
  ContentTypeId | 0x00693E2C487575B448BD420C12CEAE7EFE
  Title | Some customizer
  Modified | 2023-01-11T15:47:38Z
  Created | 2023-01-11T15:47:38Z
  AuthorId | 9
  EditorId | 9
  OData\_\_UIVersionString | 1.0
  Attachments | false
  GUID | 14125658-a9bc-4ddf-9c75-1b5767c9a337
  ComplianceAssetId | null
  TenantWideExtensionComponentId | 7096cded-b83d-4eab-96f0-df477ed7c0bc
  TenantWideExtensionWebTemplate | null
  TenantWideExtensionListTemplate | 101
  TenantWideExtensionLocation | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  TenantWideExtensionSequence | 0
  TenantWideExtensionHostProperties | null
  TenantWideExtensionDisabled | false
  ```

  </TabItem>
</Tabs>
