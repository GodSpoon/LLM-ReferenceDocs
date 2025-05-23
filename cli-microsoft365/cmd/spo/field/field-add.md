-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo field add

Adds a new list or site column using the CAML field definition

## Usage

```sh
m365 spo field add [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Absolute URL of the site where the field should be created.

`-l, --listTitle [listTitle]`
: Title of the list where the field should be created (if it should be created as a list column). Specify either `listTitle`, `listId` or `listUrl`.

`--listId [listId]`
: ID of the list where the field should be created (if it should be created as a list column). Specify either `listTitle`, `listId` or `listUrl`.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list where the field should be created (if it should be created as a list column). Specify either `listTitle`, `listId` or `listUrl`.

`-x, --xml <xml>`
: CAML field definition.

`--options [options]`
: The options to use to add to the field. Allowed values: `DefaultValue`,`AddToDefaultContentType`, `AddToNoContentType`, `AddToAllContentTypes`, `AddFieldInternalNameHint`, `AddFieldToDefaultView`, `AddFieldCheckDisplayName`.
```

<Global />

## Remarks

If the specified field already exists, you will get a _A duplicate field name "your-field" was found._ error.

## Examples

Create a date time site column.

```sh
m365 spo field add --webUrl https://contoso.sharepoint.com/sites/contoso-sales --xml '`<Field Type="DateTime" DisplayName="Start date-time" Required="FALSE" EnforceUniqueValues="FALSE" Indexed="FALSE" Format="DateTime" Group="PnP Columns" FriendlyDisplayFormat="Disabled" ID="{5ee2dd25-d941-455a-9bdb-7f2c54aed11b}" SourceID="{4f118c69-66e0-497c-96ff-d7855ce0713d}" StaticName="PnPAlertStartDateTime" Name="PnPAlertStartDateTime"><Default>[today]</Default></Field>`'
```

Create a URL list column to a list retrieved by Title.

```sh
m365 spo field add --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listTitle Events --xml '`<Field Type="URL" DisplayName="More information link" Required="FALSE" EnforceUniqueValues="FALSE" Indexed="FALSE" Format="Hyperlink" Group="PnP Columns" ID="{6085e32a-339b-4da7-ab6d-c1e013e5ab27}" SourceID="{4f118c69-66e0-497c-96ff-d7855ce0713d}" StaticName="PnPAlertMoreInformation" Name="PnPAlertMoreInformation"></Field>`'
```

Create a URL list column and add it to all content types.

```sh
m365 spo field add --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listTitle Events --xml '`<Field Type="URL" DisplayName="More information link" Required="FALSE" EnforceUniqueValues="FALSE" Indexed="FALSE" Format="Hyperlink" Group="PnP Columns" ID="{6085e32a-339b-4da7-ab6d-c1e013e5ab27}" SourceID="{4f118c69-66e0-497c-96ff-d7855ce0713d}" StaticName="PnPAlertMoreInformation" Name="PnPAlertMoreInformation"></Field>`' --options AddToAllContentTypes
```

Create a URL list column to a list retrieved by ID.

```sh
m365 spo field add --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listId e785fe80-2ca1-409e-b9d1-19055a85cd38 --xml '`<Field Type="URL" DisplayName="More information link" Required="FALSE" EnforceUniqueValues="FALSE" Indexed="FALSE" Format="Hyperlink" Group="PnP Columns" ID="{6085e32a-339b-4da7-ab6d-c1e013e5ab27}" SourceID="{4f118c69-66e0-497c-96ff-d7855ce0713d}" StaticName="PnPAlertMoreInformation" Name="PnPAlertMoreInformation"></Field>`'
```

Create a date time list column to a list retrieved by URL.

```sh
m365 spo field add --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listUrl /sites/contoso-sales/lists/Events --xml '`<Field Type="DateTime" DisplayName="Start date-time" Required="FALSE" EnforceUniqueValues="FALSE" Indexed="FALSE" Format="DateTime" Group="PnP Columns" FriendlyDisplayFormat="Disabled" ID="{5ee2dd25-d941-455a-9bdb-7f2c54aed11b}" SourceID="{4f118c69-66e0-497c-96ff-d7855ce0713d}" StaticName="PnPAlertStartDateTime" Name="PnPAlertStartDateTime"><Default>[today]</Default></Field>`'
```

## More information

- AddFieldOptions enumeration: [https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER](https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER)

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "AutoIndexed": false,
    "CanBeDeleted": true,
    "ClientSideComponentId": "00000000-0000-0000-0000-000000000000",
    "ClientSideComponentProperties": null,
    "ClientValidationFormula": null,
    "ClientValidationMessage": null,
    "CustomFormatter": null,
    "DefaultFormula": null,
    "DefaultValue": "[today]",
    "Description": "",
    "Direction": "none",
    "EnforceUniqueValues": false,
    "EntityPropertyName": "PnPAlertStartDateTime",
    "Filterable": true,
    "FromBaseType": false,
    "Group": "PnP Columns",
    "Hidden": false,
    "Id": "5ee2dd25-d941-455a-9bdb-7f2c54aed11b",
    "Indexed": false,
    "IndexStatus": 0,
    "InternalName": "PnPAlertStartDateTime",
    "IsModern": false,
    "JSLink": "clienttemplates.js",
    "PinnedToFiltersPane": false,
    "ReadOnlyField": false,
    "Required": false,
    "SchemaXml": "<Field Type=\"DateTime\" DisplayName=\"Start date-time\" Required=\"FALSE\" EnforceUniqueValues=\"FALSE\" Indexed=\"FALSE\" Format=\"DateTime\" Group=\"PnP Columns\" FriendlyDisplayFormat=\"Disabled\" ID=\"{5ee2dd25-d941-455a-9bdb-7f2c54aed11b}\" SourceID=\"{4f118c69-66e0-497c-96ff-d7855ce0713d}\" StaticName=\"PnPAlertStartDateTime\" Name=\"PnPAlertStartDateTime\" Version=\"1\"><Default>[today]</Default></Field>",
    "Scope": "/sites/SPDemo",
    "Sealed": false,
    "ShowInFiltersPane": 0,
    "Sortable": true,
    "StaticName": "PnPAlertStartDateTime",
    "Title": "Start date-time",
    "FieldTypeKind": 4,
    "TypeAsString": "DateTime",
    "TypeDisplayName": "Date and Time",
    "TypeShortDescription": "Date and Time",
    "ValidationFormula": null,
    "ValidationMessage": null,
    "DateTimeCalendarType": 0,
    "DateFormat": null,
    "DisplayFormat": 1,
    "FriendlyDisplayFormat": 1,
    "TimeFormat": null
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  AutoIndexed                  : false
  CanBeDeleted                 : true
  ClientSideComponentId        : 00000000-0000-0000-0000-000000000000
  ClientSideComponentProperties: null
  ClientValidationFormula      : null
  ClientValidationMessage      : null
  CustomFormatter              : null
  DateFormat                   : null
  DateTimeCalendarType         : 0
  DefaultFormula               : null
  DefaultValue                 : [today]
  Description                  :
  Direction                    : none
  DisplayFormat                : 1
  EnforceUniqueValues          : false
  EntityPropertyName           : PnPAlertStartDateTime
  FieldTypeKind                : 4
  Filterable                   : true
  FriendlyDisplayFormat        : 1
  FromBaseType                 : false
  Group                        : PnP Columns
  Hidden                       : false
  Id                           : 5ee2dd25-d941-455a-9bdb-7f2c54aed11b
  IndexStatus                  : 0
  Indexed                      : false
  InternalName                 : PnPAlertStartDateTime
  IsModern                     : false
  JSLink                       : clienttemplates.js
  PinnedToFiltersPane          : false
  ReadOnlyField                : false
  Required                     : false
  SchemaXml                    : <Field Type="DateTime" DisplayName="Start date-time" Required="FALSE" EnforceUniqueValues="FALSE" Indexed="FALSE" Format="DateTime" Group="PnP Columns" FriendlyDisplayFormat="Disabled" ID="{5ee2dd25-d941-455a-9bdb-7f2c54aed11b}" SourceID="{4f118c69-66e0-497c-96ff-d7855ce0713d}" StaticName="PnPAlertStartDateTime" Name="PnPAlertStartDateTime" Version="1"><Default>[today]</Default></Field>
  Scope                        : /sites/SPDemo
  Sealed                       : false
  ShowInFiltersPane            : 0
  Sortable                     : true
  StaticName                   : PnPAlertStartDateTime
  TimeFormat                   : null
  Title                        : Start date-time
  TypeAsString                 : DateTime
  TypeDisplayName              : Date and Time
  TypeShortDescription         : Date and Time
  ValidationFormula            : null
  ValidationMessage            : null
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  AutoIndexed,CanBeDeleted,ClientSideComponentId,DefaultValue,Description,Direction,EnforceUniqueValues,EntityPropertyName,Filterable,FromBaseType,Group,Hidden,Id,Indexed,IndexStatus,InternalName,IsModern,JSLink,PinnedToFiltersPane,ReadOnlyField,Required,SchemaXml,Scope,Sealed,ShowInFiltersPane,Sortable,StaticName,Title,FieldTypeKind,TypeAsString,TypeDisplayName,TypeShortDescription,DateTimeCalendarType,DisplayFormat,FriendlyDisplayFormat
  ,1,00000000-0000-0000-0000-000000000000,[today],,none,,PnPAlertStartDateTime,1,,PnP Columns,,5ee2dd25-d941-455a-9bdb-7f2c54aed11b,,0,PnPAlertStartDateTime,,clienttemplates.js,,,,"<Field Type=""DateTime"" DisplayName=""Start date-time"" Required=""FALSE"" EnforceUniqueValues=""FALSE"" Indexed=""FALSE"" Format=""DateTime"" Group=""PnP Columns"" FriendlyDisplayFormat=""Disabled"" ID=""{5ee2dd25-d941-455a-9bdb-7f2c54aed11b}"" SourceID=""{4f118c69-66e0-497c-96ff-d7855ce0713d}"" StaticName=""PnPAlertStartDateTime"" Name=""PnPAlertStartDateTime"" Version=""1""><Default>[today]</Default></Field>",/sites/SPDemo,,0,1,PnPAlertStartDateTime,Start date-time,4,DateTime,Date and Time,Date and Time,0,1,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo field add --webUrl "https://nachan365.sharepoint.com/sites/SPDemo" --xml "<Field Type='DateTime' DisplayName='Start date-time' Required='FALSE' EnforceUniqueValues='FALSE' Indexed='FALSE' Format='DateTime' Group='PnP Columns' FriendlyDisplayFormat='Disabled' ID='{5ee2dd25-d941-455a-9bdb-7f2c54aed11b}' SourceID='{4f118c69-66e0-497c-96ff-d7855ce0713d}' StaticName='PnPAlertStartDateTime' Name='PnPAlertStartDateTime'><Default>[today]</Default></Field>"

  Date: 10/3/2023

  ## Start date-time (5ee2dd25-d941-455a-9bdb-7f2c54aed11b)

  Property | Value
  ---------|-------
  AutoIndexed | false
  CanBeDeleted | true
  ClientSideComponentId | 00000000-0000-0000-0000-000000000000
  DefaultValue | [today]
  Description |
  Direction | none
  EnforceUniqueValues | false
  EntityPropertyName | PnPAlertStartDateTime
  Filterable | true
  FromBaseType | false
  Group | PnP Columns
  Hidden | false
  Id | 5ee2dd25-d941-455a-9bdb-7f2c54aed11b
  Indexed | false
  IndexStatus | 0
  InternalName | PnPAlertStartDateTime
  IsModern | false
  JSLink | clienttemplates.js
  PinnedToFiltersPane | false
  ReadOnlyField | false
  Required | false
  SchemaXml | <Field Type="DateTime" DisplayName="Start date-time" Required="FALSE" EnforceUniqueValues="FALSE" Indexed="FALSE" Format="DateTime" Group="PnP Columns" FriendlyDisplayFormat="Disabled" ID="{5ee2dd25-d941-455a-9bdb-7f2c54aed11b}" SourceID="{4f118c69-66e0-497c-96ff-d7855ce0713d}" StaticName="PnPAlertStartDateTime" Name="PnPAlertStartDateTime" Version="1"><Default>[today]</Default></Field>
  Scope | /sites/SPDemo
  Sealed | false
  ShowInFiltersPane | 0
  Sortable | true
  StaticName | PnPAlertStartDateTime
  Title | Start date-time
  FieldTypeKind | 4
  TypeAsString | DateTime
  TypeDisplayName | Date and Time
  TypeShortDescription | Date and Time
  DateTimeCalendarType | 0
  DisplayFormat | 1
  FriendlyDisplayFormat | 1
  ```

  </TabItem>
</Tabs>
