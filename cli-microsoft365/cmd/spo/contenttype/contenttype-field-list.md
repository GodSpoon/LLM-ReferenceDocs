-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo contenttype field list

Lists fields for a given site or list content type

## Usage

```sh
m365 spo contenttype field list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Absolute URL of the site where the content type is located.  

`-i, --contentTypeId [contentTypeId]`  
: The ID of the content type for which to list fields. Specify either `contentTypeId` or `contentTypeName`.  

`-n, --contentTypeName [contentTypeName]`  
: The name of the content type for which to list fields. Specify either `contentTypeId` or `contentTypeName`.  

`-l, --listTitle [listTitle]`
: Optional title of the list where the content type is located. Specify either `listTitle`, `listId` or `listUrl`.

`--listId [listId]`
: Optional ID of the list where the content type is located. Specify either `listTitle`, `listId` or `listUrl`.

`--listUrl [listUrl]`
: Optional server- or web-relative URL of the list where the content type is located. Specify either `listTitle`, `listId` or `listUrl`.  

`-p, --properties [properties]`
: Comma-separated list of properties to retrieve. Will retrieve all properties if not specified.
```

<Global />

## Examples

Retrieves fields for the specified site content type.  

```sh
m365 spo contenttype field list --webUrl https://contoso.sharepoint.com/sites/contoso-sales --contentTypeId "0x01"
```

Retrieves fields for the specified list content type in the Documents library.  

```sh
m365 spo contenttype field list --webUrl https://contoso.sharepoint.com/sites/contoso-sales --contentTypeName "Document" --listTitle "Documents"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "AutoIndexed": false,
      "CanBeDeleted": false,
      "ClientSideComponentId": "00000000-0000-0000-0000-000000000000",
      "ClientSideComponentProperties": null,
      "ClientValidationFormula": null,
      "ClientValidationMessage": null,
      "CustomFormatter": null,
      "DefaultFormula": null,
      "DefaultValue": null,
      "Description": "",
      "Direction": "none",
      "EnforceUniqueValues": false,
      "EntityPropertyName": "Title",
      "Filterable": true,
      "FromBaseType": true,
      "Group": "_Hidden",
      "Hidden": false,
      "Id": "fa564e0f-0c70-4ab9-b863-0177e6ddd247",
      "Indexed": false,
      "IndexStatus": 0,
      "InternalName": "Title",
      "IsModern": false,
      "JSLink": "clienttemplates.js",
      "PinnedToFiltersPane": false,
      "ReadOnlyField": false,
      "Required": true,
      "SchemaXml": "<Field ID=\"{fa564e0f-0c70-4ab9-b863-0177e6ddd247}\" Name=\"Title\" SourceID=\"http://schemas.microsoft.com/sharepoint/v3\" StaticName=\"Title\" Group=\"_Hidden\" Type=\"Text\" DisplayName=\"Title\" Required=\"TRUE\" FromBaseType=\"TRUE\" DelayActivateTemplateBinding=\"GROUP,SPSPERS,SITEPAGEPUBLISHING\" Customization=\"\" ShowInNewForm=\"TRUE\" ShowInEditForm=\"TRUE\"></Field>",
      "Scope": "/",
      "Sealed": false,
      "ShowInFiltersPane": 0,
      "Sortable": true,
      "StaticName": "Title",
      "Title": "Title",
      "FieldTypeKind": 2,
      "TypeAsString": "Text",
      "TypeDisplayName": "Single line of text",
      "TypeShortDescription": "Single line of text",
      "ValidationFormula": null,
      "ValidationMessage": null,
      "MaxLength": 255
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Id                                    Title   InternalName  Hidden
  ------------------------------------  ------  ------------  ------
  5ee2dd25-d941-455a-9bdb-7f2c54aed11b  Title   Title         false
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  AutoIndexed,CanBeDeleted,ClientSideComponentId,ClientSideComponentProperties,ClientValidationFormula,ClientValidationMessage,CustomFormatter,DefaultFormula,DefaultValue,Description,Direction,EnforceUniqueValues,EntityPropertyName,Filterable,FromBaseType,Group,Hidden,Id,Indexed,IndexStatus,InternalName,IsModern,JSLink,PinnedToFiltersPane,ReadOnlyField,Required,SchemaXml,Scope,Sealed,ShowInFiltersPane,Sortable,StaticName,Title,FieldTypeKind,TypeAsString,TypeDisplayName,TypeShortDescription,ValidationFormula,ValidationMessage,EnableLookup
  ,,00000000-0000-0000-0000-000000000000,,,,,,,,none,,ContentType,1,,_Hidden,,c042a256-787d-4a6f-8a8a-cf6ab767f12d,,0,ContentType,,,,,,"<Field ID=""{c042a256-787d-4a6f-8a8a-cf6ab767f12d}"" Name=""ContentType"" SourceID=""http://schemas.microsoft.com/sharepoint/v3"" StaticName=""ContentType"" Group=""_Hidden"" Type=""Computed"" DisplayName=""Content Type"" Sealed=""TRUE"" Sortable=""FALSE"" RenderXMLUsingPattern=""TRUE"" PITarget=""MicrosoftWindowsSharePointServices"" PIAttribute=""ContentTypeID"" DelayActivateTemplateBinding=""GROUP,SPSPERS,SITEPAGEPUBLISHING"" Customization=""""><FieldRefs><FieldRef ID=""{03e45e84-1992-4d42-9116-26f756012634}"" Name=""ContentTypeId"" /></FieldRefs><DisplayPattern><MapToContentType><Column Name=""ContentTypeId"" /></MapToContentType></DisplayPattern></Field>",/,1,0,,ContentType,Content Type,12,Computed,Computed,Computed,,,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo contenttype field list --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --contentTypeId "0x01"

  Date: 10/04/2024

  ## Title (fa564e0f-0c70-4ab9-b863-0177e6ddd247)

  Property | Value
  ---------|-------
  AutoIndexed | false
  CanBeDeleted | false
  ClientSideComponentId | 00000000-0000-0000-0000-000000000000
  Description |
  Direction | none
  EnforceUniqueValues | false
  EntityPropertyName | Title
  Filterable | true
  FromBaseType | true
  Group | \_Hidden
  Hidden | false
  Id | fa564e0f-0c70-4ab9-b863-0177e6ddd247
  Indexed | false
  IndexStatus | 0
  InternalName | Title
  IsModern | false
  JSLink | clienttemplates.js
  PinnedToFiltersPane | false
  ReadOnlyField | false
  Required | true
  SchemaXml | <Field ID="{fa564e0f-0c70-4ab9-b863-0177e6ddd247}" Name="Title" SourceID="http://schemas.microsoft.com/sharepoint/v3" StaticName="Title" Group="\_Hidden" Type="Text" DisplayName="Title" Required="TRUE" FromBaseType="TRUE" DelayActivateTemplateBinding="GROUP,SPSPERS,SITEPAGEPUBLISHING" Customization="" ShowInNewForm="TRUE" ShowInEditForm="TRUE"></Field>
  Scope | /
  Sealed | false
  ShowInFiltersPane | 0
  Sortable | true
  StaticName | Title
  Title | Title
  FieldTypeKind | 2
  TypeAsString | Text
  TypeDisplayName | Single line of text
  TypeShortDescription | Single line of text
  MaxLength | 255
  ```

  </TabItem>
</Tabs>
