-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo contenttype add

Adds a new list or site content type

## Usage

```sh
m365 spo contenttype add [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Absolute URL of the site where the content type should be created.

`-l, --listTitle [listTitle]`
: Title of the list (if it is a list content type). Specify either `listTitle`, `listId` or `listUrl`.

`--listId [listId]`
: ID of the list (if it is a list content type). Specify either `listTitle`, `listId` or `listUrl`.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list (if it is a list content type). Specify either `listTitle`, `listId` or `listUrl`.

`-i, --id <id>`
: The ID of the content type. Determines the parent content type.

`-n, --name <name>`
: The name of the content type.

`-d, --description [description]`
: The description of the content type.

`-g, --group [group]`
: The group with which the content type should be associated.
```

<Global />

## Remarks

If the specified content type already exists, you will get a _A duplicate content type "Your Content Type" was found._ error.

The ID of the content type specifies the parent content type from which this content type inherits.

## Examples

Create a site content type that inherits from the List item content type.

```sh
m365 spo contenttype add --webUrl https://contoso.sharepoint.com/sites/contoso-sales --name 'PnP Alert' --id 0x01007926A45D687BA842B947286090B8F67D --group 'PnP Content Types'
```

Create a list (retrieved by Title) content type that inherits from the List item content type.

```sh
m365 spo contenttype add --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listTitle Alerts --name 'PnP Alert' --id 0x01007926A45D687BA842B947286090B8F67D
```

Create a list (retrieved by ID) content type that inherits from the List item content type.

```sh
m365 spo contenttype add --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listId '8c7a0fcd-9d64-4634-85ea-ce2b37b2ec0c' --name 'PnP Alert' --id 0x01007926A45D687BA842B947286090B8F67D
```

Create a list (retrieved by URL) content type that inherits from the List item content type.

```sh
m365 spo contenttype add --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listUrl '/Shared Documents' --name 'PnP Alert' --id 0x01007926A45D687BA842B947286090B8F67D
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
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
    "Group": "PnP Content Types",
    "Hidden": false,
    "Id": {
      "StringValue": "0x01007926A45D687BA842B947286090B8F67D"
    },
    "JSLink": "",
    "MobileDisplayFormUrl": "",
    "MobileEditFormUrl": "",
    "MobileNewFormUrl": "",
    "Name": "PnP Alert",
    "NewFormClientSideComponentId": null,
    "NewFormClientSideComponentProperties": "",
    "NewFormTarget": 0,
    "NewFormTemplateName": "ListForm",
    "NewFormUrl": "",
    "ReadOnly": false,
    "SchemaXml": "<ContentType ID=\"0x01007926A45D687BA842B947286090B8F67D\" Name=\"PnP Alert\" Group=\"PnP Content Types\" Description=\"Create a new list item.\" Version=\"0\"><Folder TargetName=\"_cts/PnP Alert\" /><Fields><Field ID=\"{c042a256-787d-4a6f-8a8a-cf6ab767f12d}\" Name=\"ContentType\" SourceID=\"http://schemas.microsoft.com/sharepoint/v3\" StaticName=\"ContentType\" Group=\"_Hidden\" Type=\"Computed\" DisplayName=\"Content Type\" Sealed=\"TRUE\" Sortable=\"FALSE\" RenderXMLUsingPattern=\"TRUE\" PITarget=\"MicrosoftWindowsSharePointServices\" PIAttribute=\"ContentTypeID\" DelayActivateTemplateBinding=\"GROUP,SPSPERS,SITEPAGEPUBLISHING\" Customization=\"\"><FieldRefs><FieldRef ID=\"{03e45e84-1992-4d42-9116-26f756012634}\" Name=\"ContentTypeId\" /></FieldRefs><DisplayPattern><MapToContentType><Column Name=\"ContentTypeId\" /></MapToContentType></DisplayPattern></Field><Field ID=\"{fa564e0f-0c70-4ab9-b863-0177e6ddd247}\" Name=\"Title\" SourceID=\"http://schemas.microsoft.com/sharepoint/v3\" StaticName=\"Title\" Group=\"_Hidden\" Type=\"Text\" DisplayName=\"Title\" Required=\"TRUE\" FromBaseType=\"TRUE\" DelayActivateTemplateBinding=\"GROUP,SPSPERS,SITEPAGEPUBLISHING\" Customization=\"\" ShowInNewForm=\"TRUE\" ShowInEditForm=\"TRUE\"></Field></Fields><XmlDocuments><XmlDocument NamespaceURI=\"http://schemas.microsoft.com/sharepoint/v3/contenttype/forms\"><FormTemplates xmlns=\"http://schemas.microsoft.com/sharepoint/v3/contenttype/forms\"><Display>ListForm</Display><Edit>ListForm</Edit><New>ListForm</New></FormTemplates></XmlDocument></XmlDocuments></ContentType>",
    "Scope": "/sites/contoso-sales",
    "Sealed": false,
    "StringId": "0x01007926A45D687BA842B947286090B8F67D"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  ClientFormCustomFormatter               :
  Description                             : Create a new list item.
  DisplayFormClientSideComponentId        :
  EXAMPLE_SECRET_VALUE_PLACEHOLDER:
  DisplayFormTarget                       : 0
  DisplayFormTemplateName                 : ListForm
  DisplayFormUrl                          :
  DocumentTemplate                        :
  DocumentTemplateUrl                     :
  EditFormClientSideComponentId           :
  EditFormClientSideComponentProperties   :
  EditFormTarget                          : 0
  EditFormTemplateName                    : ListForm
  EditFormUrl                             :
  Group                                   : PnP Content Types
  Hidden                                  : false
  Id                                      : {"StringValue":"0x01007926A45D687BA842B947286090B8F67D"}
  JSLink                                  :
  MobileDisplayFormUrl                    :
  MobileEditFormUrl                       :
  MobileNewFormUrl                        :
  Name                                    : PnP Alert
  NewFormClientSideComponentId            : null
  NewFormClientSideComponentProperties    :
  NewFormTarget                           : 0
  NewFormTemplateName                     : ListForm
  NewFormUrl                              :
  ReadOnly                                : false
  SchemaXml                               : <ContentType ID="0x01007926A45D687BA842B947286090B8F67D" Name="PnP Alert" Group="PnP Content Types" Description="Create a new list item." Version="0"><Folder TargetName="_cts/PnP Alert" /><Fields><Field ID="{c042a256-787d-4a6f-8a8a-cf6ab767f12d}" Name="ContentType" SourceID="http://schemas.microsoft.com/sharepoint/v3" StaticName="ContentType" Group="_Hidden" Type="Computed" DisplayName="Content Type" Sealed="TRUE" Sortable="FALSE" RenderXMLUsingPattern="TRUE" PITarget="MicrosoftWindowsSharePointServices" PIAttribute="ContentTypeID" DelayActivateTemplateBinding="GROUP,SPSPERS,SITEPAGEPUBLISHING" Customization=""><FieldRefs><FieldRef ID="{03e45e84-1992-4d42-9116-26f756012634}" Name="ContentTypeId" /></FieldRefs><DisplayPattern><MapToContentType><Column Name="ContentTypeId" /></MapToContentType></DisplayPattern></Field><Field ID="{fa564e0f-0c70-4ab9-b863-0177e6ddd247}" Name="Title" SourceID="http://schemas.microsoft.com/sharepoint/v3" StaticName="Title" Group="_Hidden" Type="Text" DisplayName="Title" Required="TRUE" FromBaseType="TRUE" DelayActivateTemplateBinding="GROUP,SPSPERS,SITEPAGEPUBLISHING" Customization="" ShowInNewForm="TRUE" ShowInEditForm="TRUE"></Field></Fields><XmlDocuments><XmlDocument NamespaceURI="http://schemas.microsoft.com/sharepoint/v3/contenttype/forms"><FormTemplates xmlns="http://schemas.microsoft.com/sharepoint/v3/contenttype/forms"><Display>ListForm</Display><Edit>ListForm</Edit><New>ListForm</New></FormTemplates></XmlDocument></XmlDocuments></ContentType>
  Scope                                   : /sites/contoso-sales
  Sealed                                  : false
  StringId                                : 0x01007926A45D687BA842B947286090B8F67D
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ClientFormCustomFormatter,Description,DisplayFormClientSideComponentId,EXAMPLE_SECRET_VALUE_PLACEHOLDER,DisplayFormTarget,DisplayFormTemplateName,DisplayFormUrl,DocumentTemplate,DocumentTemplateUrl,EditFormClientSideComponentId,EditFormClientSideComponentProperties,EditFormTarget,EditFormTemplateName,EditFormUrl,Group,Hidden,JSLink,MobileDisplayFormUrl,MobileEditFormUrl,MobileNewFormUrl,Name,NewFormClientSideComponentProperties,NewFormTarget,NewFormTemplateName,NewFormUrl,ReadOnly,SchemaXml,Scope,Sealed,StringId
  ,Create a new list item.,,,0,ListForm,,,,,,0,ListForm,,PnP Content Types,,,,,,PnP Alert,,0,ListForm,,,"<ContentType ID=""0x01007926A45D687BA842B947286090B8F67D"" Name=""PnP Alert"" Group=""PnP Content Types"" Description=""Create a new list item."" Version=""0""><Folder TargetName=""_cts/PnP Alert"" /><Fields><Field ID=""{c042a256-787d-4a6f-8a8a-cf6ab767f12d}"" Name=""ContentType"" SourceID=""http://schemas.microsoft.com/sharepoint/v3"" StaticName=""ContentType"" Group=""_Hidden"" Type=""Computed"" DisplayName=""Content Type"" Sealed=""TRUE"" Sortable=""FALSE"" RenderXMLUsingPattern=""TRUE"" PITarget=""MicrosoftWindowsSharePointServices"" PIAttribute=""ContentTypeID"" DelayActivateTemplateBinding=""GROUP,SPSPERS,SITEPAGEPUBLISHING"" Customization=""""><FieldRefs><FieldRef ID=""{03e45e84-1992-4d42-9116-26f756012634}"" Name=""ContentTypeId"" /></FieldRefs><DisplayPattern><MapToContentType><Column Name=""ContentTypeId"" /></MapToContentType></DisplayPattern></Field><Field ID=""{fa564e0f-0c70-4ab9-b863-0177e6ddd247}"" Name=""Title"" SourceID=""http://schemas.microsoft.com/sharepoint/v3"" StaticName=""Title"" Group=""_Hidden"" Type=""Text"" DisplayName=""Title"" Required=""TRUE"" FromBaseType=""TRUE"" DelayActivateTemplateBinding=""GROUP,SPSPERS,SITEPAGEPUBLISHING"" Customization="""" ShowInNewForm=""TRUE"" ShowInEditForm=""TRUE""></Field></Fields><XmlDocuments><XmlDocument NamespaceURI=""http://schemas.microsoft.com/sharepoint/v3/contenttype/forms""><FormTemplates xmlns=""http://schemas.microsoft.com/sharepoint/v3/contenttype/forms""><Display>ListForm</Display><Edit>ListForm</Edit><New>ListForm</New></FormTemplates></XmlDocument></XmlDocuments></ContentType>",/sites/contoso-sales,,0x01007926A45D687BA842B947286090B8F67D
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo contenttype add --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --name "PnP Alert" --id "0x01007926A45D687BA842B947286090B8F67D" --group "PnP Content Types"

  Date: 10/2/2023

  ## PnP Alert ([object Object])

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
  Group | PnP Content Types
  Hidden | false
  JSLink |
  MobileDisplayFormUrl |
  MobileEditFormUrl |
  MobileNewFormUrl |
  Name | PnP Alert
  NewFormClientSideComponentProperties |
  NewFormTarget | 0
  NewFormTemplateName | ListForm
  NewFormUrl |
  ReadOnly | false
  SchemaXml | <ContentType ID="0x01007926A45D687BA842B947286090B8F67D" Name="PnP Alert" Group="PnP Content Types" Description="Create a new list item." Version="0"><Folder TargetName="\_cts/PnP Alert" /><Fields><Field ID="{c042a256-787d-4a6f-8a8a-cf6ab767f12d}" Name="ContentType" SourceID="http://schemas.microsoft.com/sharepoint/v3" StaticName="ContentType" Group="\_Hidden" Type="Computed" DisplayName="Content Type" Sealed="TRUE" Sortable="FALSE" RenderXMLUsingPattern="TRUE" PITarget="MicrosoftWindowsSharePointServices" PIAttribute="ContentTypeID" DelayActivateTemplateBinding="GROUP,SPSPERS,SITEPAGEPUBLISHING" Customization=""><FieldRefs><FieldRef ID="{03e45e84-1992-4d42-9116-26f756012634}" Name="ContentTypeId" /></FieldRefs><DisplayPattern><MapToContentType><Column Name="ContentTypeId" /></MapToContentType></DisplayPattern></Field><Field ID="{fa564e0f-0c70-4ab9-b863-0177e6ddd247}" Name="Title" SourceID="http://schemas.microsoft.com/sharepoint/v3" StaticName="Title" Group="\_Hidden" Type="Text" DisplayName="Title" Required="TRUE" FromBaseType="TRUE" DelayActivateTemplateBinding="GROUP,SPSPERS,SITEPAGEPUBLISHING" Customization="" ShowInNewForm="TRUE" ShowInEditForm="TRUE"></Field></Fields><XmlDocuments><XmlDocument NamespaceURI="http://schemas.microsoft.com/sharepoint/v3/contenttype/forms"><FormTemplates xmlns="http://schemas.microsoft.com/sharepoint/v3/contenttype/forms"><Display>ListForm</Display><Edit>ListForm</Edit><New>ListForm</New></FormTemplates></XmlDocument></XmlDocuments></ContentType>
  Scope | /sites/contoso-sales
  Sealed | false
  StringId | 0x01007926A45D687BA842B947286090B8F67D
  ```

  </TabItem>
</Tabs>

## More information

- Content Type IDs: [https://learn.microsoft.com/previous-versions/office/developer/sharepoint-2010/aa543822(v%3Doffice.14)](https://learn.microsoft.com/previous-versions/office/developer/sharepoint-2010/aa543822(v%3Doffice.14))
