-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo tenant applicationcustomizer list

Retrieves a list of application customizers that are installed tenant-wide

## Usage

```sh
m365 spo tenant applicationcustomizer list [options]
```

## Options

<Global />

## Remarks

This command can be used for retrieving a list of tenant-wide installed application customizers. To retrieve a list of application customizers from a specific site, view our dedicated [spo applicationcustomizer list](../applicationcustomizer/applicationcustomizer-list.mdx) command.

## Examples

Retrieves a list of application customizers.

```sh
m365 spo tenant applicationcustomizer list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
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
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  TenantWideExtensionComponentId        TenantWideExtensionWebTemplate  Title
  ------------------------------------  ------------------------------  ----------
  9a8b100c-246b-4592-9454-67826523e159  null                            HelloWorld
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
  # spo tenant applicationcustomizer list

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
