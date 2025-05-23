-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo tenant commandset get

Get a ListView Command Set that is installed tenant-wide

## Usage

```sh
m365 spo tenant commandset get [options]
```

## Options

```md definition-list
`-t, --title [title]`
: The title of the ListView Command Set. Specify either `title`, `id`, or `clientSideComponentId`.

`-i, --id [id]`
: The id of the ListView Command Set. Specify either `title`, `id`, or `clientSideComponentId`.

`-c, --clientSideComponentId  [clientSideComponentId]`
: The Client Side Component Id (GUID) of the ListView Command Set. Specify either `title`, `id`, or `clientSideComponentId`.

`-p, --tenantWideExtensionComponentProperties`
: Only output the tenant wide extension component properties.
```

<Global />

## Remarks

This command can be used for retrieving a ListView Command Set that's installed tenant-wide. To retrieve a ListView Command Set from a specific site, view our dedicated [spo commandset get](../commandset/commandset-get.mdx) command.

## Examples

Retrieves a ListView Command Set by title.

```sh
m365 spo tenant commandset get --title "Some customizer"
```

Retrieves a ListView Command Set by id.

```sh
m365 spo tenant commandset get --id 3
```

Retrieves a ListView Command Set by clientSideComponentId.

```sh
m365 spo tenant commandset get --clientSideComponentId 7096cded-b83d-4eab-96f0-df477ed7c0bc
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "FileSystemObjectType": 0,
    "Id": 1,
    "ServerRedirectedEmbedUri": null,
    "ServerRedirectedEmbedUrl": "",
    "ContentTypeId": "0x00DBF24546DE6018449BB43573F3581BF0",
    "Title": "HelloWorld",
    "Modified": "2024-05-16T21:28:51Z",
    "Created": "2024-05-16T21:28:51Z",
    "AuthorId": 9,
    "EditorId": 9,
    "OData__UIVersionString": "1.0",
    "Attachments": false,
    "GUID": "bd123dcd-37b8-4981-aa4e-1aab50a66688",
    "OData__ColorTag": null,
    "ComplianceAssetId": null,
    "TenantWideExtensionComponentId": "53dd6a38-1461-44e0-9bf0-14883316a316",
    "TenantWideExtensionComponentProperties": "{\"sampleTextOne\":\"One item is selected in the list.\", \"sampleTextTwo\":\"This command is always visible.\"}",
    "TenantWideExtensionWebTemplate": null,
    "TenantWideExtensionListTemplate": 100,
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
  ContentTypeId                         : 0x00DBF24546DE6018449BB43573F3581BF0
  Created                               : 2024-05-16T21:28:51Z
  EditorId                              : 9
  FileSystemObjectType                  : 0
  GUID                                  : bd123dcd-37b8-4981-aa4e-1aab50a66688
  Id                                    : 1
  Modified                              : 2024-05-16T21:28:51Z
  OData__ColorTag                       : null
  OData__UIVersionString                : 1.0
  ServerRedirectedEmbedUri              : null
  ServerRedirectedEmbedUrl              :
  TenantWideExtensionComponentId        : 53dd6a38-1461-44e0-9bf0-14883316a316
  TenantWideExtensionComponentProperties: {"sampleTextOne":"One item is selected in the list.", "sampleTextTwo":"This command is always visible."}
  TenantWideExtensionDisabled           : false
  TenantWideExtensionHostProperties     : null
  TenantWideExtensionListTemplate       : 100
  TenantWideExtensionLocation           : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  TenantWideExtensionSequence           : 0
  TenantWideExtensionWebTemplate        : null
  Title                                 : HelloWorld
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  FileSystemObjectType,Id,ServerRedirectedEmbedUri,ServerRedirectedEmbedUrl,ContentTypeId,Title,Modified,Created,AuthorId,EditorId,OData__UIVersionString,Attachments,GUID,OData__ColorTag,ComplianceAssetId,TenantWideExtensionComponentId,TenantWideExtensionComponentProperties,TenantWideExtensionWebTemplate,TenantWideExtensionListTemplate,TenantWideExtensionLocation,TenantWideExtensionSequence,TenantWideExtensionHostProperties,TenantWideExtensionDisabled
  0,1,,,0x00DBF24546DE6018449BB43573F3581BF0,HelloWorld,2024-05-16T21:28:51Z,2024-05-16T21:28:51Z,9,9,1.0,,bd123dcd-37b8-4981-aa4e-1aab50a66688,,,53dd6a38-1461-44e0-9bf0-14883316a316,"{""sampleTextOne"":""One item is selected in the list."", ""sampleTextTwo"":""This command is always visible.""}",,100,EXAMPLE_SECRET_VALUE_PLACEHOLDER,0,,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo tenant commandset get --id "1"

  Date: 16/05/2024

  ## HelloWorld (1)

  Property | Value
  ---------|-------
  FileSystemObjectType | 0
  Id | 1
  ServerRedirectedEmbedUrl |
  ContentTypeId | 0x00DBF24546DE6018449BB43573F3581BF0
  Title | HelloWorld
  Modified | 2024-05-16T21:28:51Z
  Created | 2024-05-16T21:28:51Z
  AuthorId | 9
  EditorId | 9
  OData\_\_UIVersionString | 1.0
  Attachments | false
  GUID | bd123dcd-37b8-4981-aa4e-1aab50a66688
  TenantWideExtensionComponentId | 53dd6a38-1461-44e0-9bf0-14883316a316
  TenantWideExtensionComponentProperties | {"sampleTextOne":"One item is selected in the list.", "sampleTextTwo":"This command is always visible."}
  TenantWideExtensionListTemplate | 100
  TenantWideExtensionLocation | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  TenantWideExtensionSequence | 0
  TenantWideExtensionDisabled | false
  ```

  </TabItem>
</Tabs>

### `tenantWideExtensionComponentProperties` response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "testMessage": "Test message"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  testMessage: Test message
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  testMessage
  Test message
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo tenant applicationcustomizer get --id "2" --tenantWideExtensionComponentProperties "true"

  Date: 17/05/2024

  Property | Value
  ---------|-------
  testMessage | Test message
  ```
  
  </TabItem>
</Tabs>
