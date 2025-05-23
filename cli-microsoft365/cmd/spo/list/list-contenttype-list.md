-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo list contenttype list

Lists content types configured on the list

## Usage

```sh
m365 spo list contenttype list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list is located.

`-l, --listId [listId]`
: ID of the list. Specify either `listTitle`, `listId`, or `listUrl`.

`-t, --listTitle [listTitle]`
: Title of the list. Specify either `listTitle`, `listId`, or `listUrl`.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listTitle`, `listId`, or `listUrl`.
```

<Global />

## Examples

List all content types configured on a specific list retrieved by id in a specific site.

```sh
m365 spo list contenttype list --webUrl https://contoso.sharepoint.com/sites/project-x --listId 0cd891ef-afce-4e55-b836-fce03286cccf
```

List all content types configured on a specific list retrieved by title in a specific site.

```sh
m365 spo list contenttype list --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle Documents
```

List all content types configured on a specific list retrieved by server relative URL in a specific site.

```sh
m365 spo list contenttype list --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl 'sites/project-x/Documents'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "ClientFormCustomFormatter": "",
      "Description": "Create a new list item.",
      "DisplayFormClientSideComponentId": "",
      "EXAMPLE_SECRET_VALUE_PLACEHOLDER": "",
      "DisplayFormTarget": 0,
      "DisplayFormTemplateName": "ListForm",
      "DisplayFormUrl": "",
      "DocumentTemplate": "",
      "DocumentTemplateUrl": "",
      "EditFormClientSideComponentId": "",
      "EditFormClientSideComponentProperties": "",
      "EditFormTarget": 0,
      "EditFormTemplateName": "ListForm",
      "EditFormUrl": "",
      "Group": "List Content Types",
      "Hidden": false,
      "Id": {
        "StringValue": "0x01000B1208C5D23DF44B9F1AEE7373DE9D5E"
      },
      "JSLink": "",
      "MobileDisplayFormUrl": "",
      "MobileEditFormUrl": "",
      "MobileNewFormUrl": "",
      "Name": "Item",
      "NewFormClientSideComponentId": null,
      "NewFormClientSideComponentProperties": "",
      "NewFormTarget": 0,
      "NewFormTemplateName": "ListForm",
      "NewFormUrl": "",
      "Parent": {
        "StringId": "0x01000B1208C5D23DF",
        "Name": "Item",
        "Group": "List items",
        "Id": { "StringId": "0x01000B1208C5D23DF" }
      },
      "ReadOnly": false,
      "SchemaXml": "<ContentType ID=\"0x01000B1208C5D23DF44B9F1AEE7373DE9D5E\" Name=\"Item\" Group=\"List Content Types\" Description=\"Create a new list item.\" Version=\"0\" FeatureId=\"{695b6570-a48b-4a8e-8ea5-26ea7fc1d162}\" FeatureIds=\"{695b6570-a48b-4a8e-8ea5-26ea7fc1d162};{c94c1702-30a7-454c-be15-5a895223428d}\"><Folder TargetName=\"Item\"/><Fields><Field ID=\"{c042a256-787d-4a6f-8a8a-cf6ab767f12d}\" Type=\"Computed\" DisplayName=\"Content Type\" Name=\"ContentType\" DisplaceOnUpgrade=\"TRUE\" RenderXMLUsingPattern=\"TRUE\" Sortable=\"FALSE\" SourceID=\"http://schemas.microsoft.com/sharepoint/v3\" StaticName=\"ContentType\" Group=\"_Hidden\" PITarget=\"MicrosoftWindowsSharePointServices\" PIAttribute=\"ContentTypeID\" FromBaseType=\"TRUE\"><FieldRefs><FieldRef Name=\"ContentTypeId\"/></FieldRefs><DisplayPattern><MapToContentType><Column Name=\"ContentTypeId\"/></MapToContentType></DisplayPattern></Field><Field ID=\"{fa564e0f-0c70-4ab9-b863-0177e6ddd247}\" Type=\"Text\" Name=\"Title\" DisplayName=\"Title\" Required=\"TRUE\" SourceID=\"http://schemas.microsoft.com/sharepoint/v3\" StaticName=\"Title\" FromBaseType=\"TRUE\" ColName=\"nvarchar1\" ShowInNewForm=\"TRUE\" ShowInEditForm=\"TRUE\"/></Fields><XmlDocuments><XmlDocument NamespaceURI=\"http://schemas.microsoft.com/sharepoint/v3/contenttype/forms\"><FormTemplates xmlns=\"http://schemas.microsoft.com/sharepoint/v3/contenttype/forms\"><Display>ListForm</Display><Edit>ListForm</Edit><New>ListForm</New></FormTemplates></XmlDocument></XmlDocuments></ContentType>",
      "Scope": "/Lists/Test",
      "Sealed": false,
      "StringId": "0x01000B1208C5D23DF44B9F1AEE7373DE9D5E"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  StringId                                Name  Hidden  ReadOnly  Sealed
  --------------------------------------  ----  ------  --------  ------
  0x01000B1208C5D23DF44B9F1AEE7373DE9D5E  Item  false   false     false
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  StringId,Name,Hidden,ReadOnly,Sealed
  0x01000B1208C5D23DF44B9F1AEE7373DE9D5E,Item,,,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo list contenttype list --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "Documents"

  Date: 2/20/2023

  ## Document (0x01000B1208C5D23DF44B9F1AEE7373DE9D5E)

  Property | Value
  ---------|-------
  ClientFormCustomFormatter |
  Description | Create a new list item.
  DisplayFormClientSideComponentId |
  EXAMPLE_SECRET_VALUE_PLACEHOLDER |
  DisplayFormTarget | 0
  DisplayFormTemplateName | ListForm
  DisplayFormUrl |
  DocumentTemplate | 
  DocumentTemplateUrl | 
  EditFormClientSideComponentId |
  EditFormClientSideComponentProperties |
  EditFormTarget | 0
  EditFormTemplateName | ListForm
  EditFormUrl |
  Group | List Content Types
  Hidden | false
  JSLink |
  MobileDisplayFormUrl |
  MobileEditFormUrl |
  MobileNewFormUrl |
  Name | Item
  NewFormClientSideComponentId | null
  NewFormClientSideComponentProperties |
  NewFormTarget | 0
  NewFormTemplateName | ListForm
  NewFormUrl |
  ReadOnly | false
  SchemaXml | <ContentType ID="0x01000B1208C5D23DF44B9F1AEE7373DE9D5E" Name="Item" Group="List Content Types" Description="Create a new list item." Version="0" FeatureId="{695b6570-a48b-4a8e-8ea5-26ea7fc1d162}" FeatureIds="{695b6570-a48b-4a8e-8ea5-26ea7fc1d162};{c94c1702-30a7-454c-be15-5a895223428d}"><Folder TargetName="Item"/><Fields><Field ID="{c042a256-787d-4a6f-8a8a-cf6ab767f12d}" Type="Computed" DisplayName="Content Type" Name="ContentType" DisplaceOnUpgrade="TRUE" RenderXMLUsingPattern="TRUE" Sortable="FALSE" SourceID="http://schemas.microsoft.com/sharepoint/v3" StaticName="ContentType" Group="_Hidden" PITarget="MicrosoftWindowsSharePointServices" PIAttribute="ContentTypeID" FromBaseType="TRUE"><FieldRefs><FieldRef Name="ContentTypeId"/></FieldRefs><DisplayPattern><MapToContentType><Column Name="ContentTypeId"/></MapToContentType></DisplayPattern></Field><Field ID="{fa564e0f-0c70-4ab9-b863-0177e6ddd247}" Type="Text" Name="Title" DisplayName="Title" Required="TRUE" SourceID="http://schemas.microsoft.com/sharepoint/v3" StaticName="Title" FromBaseType="TRUE" ColName="nvarchar1" ShowInNewForm="TRUE" ShowInEditForm="TRUE"/></Fields><XmlDocuments><XmlDocument NamespaceURI="http://schemas.microsoft.com/sharepoint/v3/contenttype/forms"><FormTemplates xmlns="http://schemas.microsoft.com/sharepoint/v3/contenttype/forms"><Display>ListForm</Display><Edit>ListForm</Edit><New>ListForm</New></FormTemplates></XmlDocument></XmlDocuments></ContentType>
  Scope | /Lists/Test
  Sealed | false
  StringId | 0x01000B1208C5D23DF44B9F1AEE7373DE9D5E
  ```

  </TabItem>
</Tabs>
