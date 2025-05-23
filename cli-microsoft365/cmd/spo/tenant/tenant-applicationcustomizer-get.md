-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo tenant applicationcustomizer get

Get an application customizer that is installed tenant-wide

## Usage

```sh
m365 spo tenant applicationcustomizer get [options]
```

## Options

```md definition-list
`-t, --title [title]`
: The title of the application customizer. Specify either `title`, `id`, or `clientSideComponentId`.

`-i, --id [id]`
: The id of the application customizer. Specify either `title`, `id`, or `clientSideComponentId`.

`-c, --clientSideComponentId  [clientSideComponentId]`
: The Client Side Component Id (GUID) of the application customizer. Specify either `title`, `id`, or `clientSideComponentId`.

`-p, --tenantWideExtensionComponentProperties`
: Only output the tenant wide extension component properties.
```

<Global />

## Examples

Retrieves an application customizer by title.

```sh
m365 spo tenant applicationcustomizer get --title "Some customizer"
```

Retrieves an application customizer by id.

```sh
m365 spo tenant applicationcustomizer get --id 3
```

Retrieves an application customizer by clientSideComponentId.

```sh
m365 spo tenant applicationcustomizer get --clientSideComponentId 7096cded-b83d-4eab-96f0-df477ed7c0bc
```

## Remarks

This command can be used for retrieving an application customizer that's installed tenant-wide. To retrieve an application customizer from a specific site, view our dedicated [spo applicationcustomizer get](../applicationcustomizer/applicationcustomizer-get.mdx) command.

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "FileSystemObjectType": 0,
    "Id": 2,
    "ServerRedirectedEmbedUri": null,
    "ServerRedirectedEmbedUrl": "",
    "ContentTypeId": "0x00DBF24546DE6018449BB43573F3581BF0",
    "Title": "HelloWorld",
    "Modified": "2024-05-16T21:59:09Z",
    "Created": "2024-05-16T21:59:09Z",
    "AuthorId": 9,
    "EditorId": 9,
    "OData__UIVersionString": "1.0",
    "Attachments": false,
    "GUID": "dfc6a646-742b-4d9d-9fcf-892a972298ff",
    "OData__ColorTag": null,
    "ComplianceAssetId": null,
    "TenantWideExtensionComponentId": "9a8b100c-246b-4592-9454-67826523e159",
    "TenantWideExtensionComponentProperties": "{\"testMessage\":\"Test message\"}",
    "TenantWideExtensionWebTemplate": null,
    "TenantWideExtensionListTemplate": 0,
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
  Created                               : 2024-05-16T21:59:09Z
  EditorId                              : 9
  FileSystemObjectType                  : 0
  GUID                                  : dfc6a646-742b-4d9d-9fcf-892a972298ff
  Id                                    : 2
  Modified                              : 2024-05-16T21:59:09Z
  OData__ColorTag                       : null
  OData__UIVersionString                : 1.0
  ServerRedirectedEmbedUri              : null
  ServerRedirectedEmbedUrl              :
  TenantWideExtensionComponentId        : 9a8b100c-246b-4592-9454-67826523e159
  TenantWideExtensionComponentProperties: {"testMessage":"Test message"}
  TenantWideExtensionDisabled           : false
  TenantWideExtensionHostProperties     : null
  TenantWideExtensionListTemplate       : 0
  TenantWideExtensionLocation           : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  TenantWideExtensionSequence           : 0
  TenantWideExtensionWebTemplate        : null
  Title                                 : HelloWorld
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  FileSystemObjectType,Id,ServerRedirectedEmbedUri,ServerRedirectedEmbedUrl,ContentTypeId,Title,Modified,Created,AuthorId,EditorId,OData__UIVersionString,Attachments,GUID,OData__ColorTag,ComplianceAssetId,TenantWideExtensionComponentId,TenantWideExtensionComponentProperties,TenantWideExtensionWebTemplate,TenantWideExtensionListTemplate,TenantWideExtensionLocation,TenantWideExtensionSequence,TenantWideExtensionHostProperties,TenantWideExtensionDisabled
  0,2,,,0x00DBF24546DE6018449BB43573F3581BF0,HelloWorld,2024-05-16T21:59:09Z,2024-05-16T21:59:09Z,9,9,1.0,,dfc6a646-742b-4d9d-9fcf-892a972298ff,,,9a8b100c-246b-4592-9454-67826523e159,"{""testMessage"":""Test message""}",,0,EXAMPLE_SECRET_VALUE_PLACEHOLDER,0,,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo tenant applicationcustomizer get --id "2"

  Date: 17/05/2024

  ## HelloWorld (2)

  Property | Value
  ---------|-------
  FileSystemObjectType | 0
  Id | 2
  ServerRedirectedEmbedUrl |
  ContentTypeId | 0x00DBF24546DE6018449BB43573F3581BF0
  Title | HelloWorld
  Modified | 2024-05-16T21:59:09Z
  Created | 2024-05-16T21:59:09Z
  AuthorId | 9
  EditorId | 9
  OData\_\_UIVersionString | 1.0
  Attachments | false
  GUID | dfc6a646-742b-4d9d-9fcf-892a972298ff
  TenantWideExtensionComponentId | 9a8b100c-246b-4592-9454-67826523e159
  TenantWideExtensionComponentProperties | {"testMessage":"Test message"}
  TenantWideExtensionListTemplate | 0
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
  # spo tenant commandset get --id "1" --tenantWideExtensionComponentProperties "true"

  Date: 16/05/2024

  Property | Value
  ---------|-------
  sampleTextOne | One item is selected in the list.
  sampleTextTwo | This command is always visible.
  ```
  
  </TabItem>
</Tabs>
