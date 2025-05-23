-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo field list

Retrieves columns for the specified list or site

## Usage

```sh
m365 spo field list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Absolute URL of the site where fields are located.

`-t, --listTitle [listTitle]`
: Title of the list where fields are located. Specify either `listTitle`, `listId` or `listUrl`.

`-i --listId [listId]`
: ID of the list where fields are located. Specify either `listTitle`, `listId` or `listUrl`.

`--listUrl [listUrl]`
: Server- or web-relative URL of the list where fields are located. Specify either `listTitle`, `listId` or `listUrl`.
```

<Global />

## Examples

Retrieves site columns for the specified site.

```sh
m365 spo field list --webUrl https://contoso.sharepoint.com/sites/contoso-sales
```

Retrieves list columns for list _Events_ in the specified site.

```sh
m365 spo field list --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listTitle Events
```

Retrieves list columns for the specified list in the specified site.

```sh
m365 spo field list --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listId '202b8199-b9de-43fd-9737-7f213f51c991'
```

Retrieves list columns for the specified list in the specified site.

```sh
m365 spo field list --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listUrl '/sites/contoso-sales/lists/Events'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
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
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Id                                    Title            InternalName           Hidden
  ------------------------------------  ---------------  ---------------------  ------
  5ee2dd25-d941-455a-9bdb-7f2c54aed11b  Start date-time  PnPAlertStartDateTime  false
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  AutoIndexed,CanBeDeleted,ClientSideComponentId,Description,Direction,EnforceUniqueValues,EntityPropertyName,Filterable,FromBaseType,Group,Hidden,Id,Indexed,IndexStatus,InternalName,IsModern,JSLink,PinnedToFiltersPane,ReadOnlyField,Required,SchemaXml,Scope,Sealed,ShowInFiltersPane,Sortable,StaticName,Title,FieldTypeKind,TypeAsString,TypeDisplayName,TypeShortDescription,MaxLength
  ,1,00000000-0000-0000-0000-000000000000,,none,,PnPAlertStartDateTime,1,,PnP Columns,,5ee2dd25-d941-455a-9bdb-7f2c54aed11b,,0,PnPAlertStartDateTime,,clienttemplates.js,,,,"<Field Type=""DateTime"" DisplayName=""Start date-time"" Required=""FALSE"" EnforceUniqueValues=""FALSE"" Indexed=""FALSE"" Format=""DateTime"" Group=""PnP Columns"" FriendlyDisplayFormat=""Disabled"" ID=""{5ee2dd25-d941-455a-9bdb-7f2c54aed11b}"" SourceID=""{4f118c69-66e0-497c-96ff-d7855ce0713d}"" StaticName=""PnPAlertStartDateTime"" Name=""PnPAlertStartDateTime"" Version=""1""><Default>[today]</Default></Field>",/sites/SPDemo,,0,1,PnPAlertStartDateTime,Start date-time,4,DateTime,Date and Time,Date and Time,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo field list --webUrl "https://nachan365.sharepoint.com/sites/SPDemo"

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
