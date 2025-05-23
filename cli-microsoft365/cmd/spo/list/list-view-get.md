-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo list view get

Gets information about specific list view

## Usage

```sh
m365 spo list view get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list is located.

`--listId [listId]`
: ID of the list where the view is located. Specify only one of `listTitle`, `listId` or `listUrl`.

`--listTitle [listTitle]`
: Title of the list where the view is located. Specify only one of `listTitle`, `listId` or `listUrl`.

`--listUrl [listUrl]`
: Server- or web-relative URL of the list where the view is located. Specify only one of `listTitle`, `listId` or `listUrl`.

`--id [id]`
: ID of the view to get. Specify `title` or `id` but not both.

`--title [title]`
: Title of the view to get. Specify `title` or `id` but not both.
```

<Global />

## Examples

Gets a list view by name from a list located in the specified site.

```sh
m365 spo list view get --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'My List' --title 'All Items'
```

Gets a list view by ID from a list located in the specified site.

```sh
m365 spo list view get --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl 'Lists/My List' --id 330f29c5-5c4c-465f-9f4b-7903020ae1ce
```

Gets a list view by name from a list located in the specified site. Retrieve the list by its ID

```sh
m365 spo list view get --webUrl https://contoso.sharepoint.com/sites/project-x --listId 330f29c5-5c4c-465f-9f4b-7903020ae1c1 --title 'All Items'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Aggregations": null,
    "AggregationsStatus": null,
    "AssociatedContentTypeId": null,
    "BaseViewId": "1",
    "CalendarViewStyles": null,
    "ColumnWidth": null,
    "ContentTypeId": {
      "StringValue": "0x"
    },
    "CustomFormatter": null,
    "CustomOrder": null,
    "DefaultView": false,
    "DefaultViewForContentType": false,
    "EditorModified": false,
    "Formats": null,
    "GridLayout": null,
    "Hidden": false,
    "HtmlSchemaXml": "<View Name=\"{3CD2E934-F482-4D4A-A9B8-A13B49B3D226}\" Type=\"HTML\" DisplayName=\"All events\" Url=\"/Lists/Test/All events.aspx\" Level=\"1\" BaseViewID=\"1\" ContentTypeID=\"0x\" ImageUrl=\"/_layouts/15/images/generic.png?rev=47\"><ViewFields><FieldRef Name=\"Title\" /></ViewFields><Query><OrderBy><FieldRef Name=\"Created\" Ascending=\"FALSE\" /></OrderBy><Where><Eq><FieldRef Name=\"TextFieldName\" /><Value Type=\"Text\">Field value</Value></Eq></Where></Query><RowLimit Paged=\"TRUE\">30</RowLimit><XslLink Default=\"TRUE\">main.xsl</XslLink><JSLink>clienttemplates.js</JSLink><Toolbar Type=\"Standard\" /><ParameterBindings><ParameterBinding Name=\"NoAnnouncements\" Location=\"Resource(wss,noXinviewofY_LIST)\" /><ParameterBinding Name=\"NoAnnouncementsHowTo\" Location=\"Resource(wss,noXinviewofY_DEFAULT)\" /></ParameterBindings></View>",
    "Id": "3cd2e934-f482-4d4a-a9b8-a13b49b3d226",
    "ImageUrl": "/_layouts/15/images/generic.png?rev=47",
    "IncludeRootFolder": false,
    "ViewJoins": null,
    "JSLink": "clienttemplates.js",
    "ListViewXml": "<View Name=\"{3CD2E934-F482-4D4A-A9B8-A13B49B3D226}\" Type=\"HTML\" DisplayName=\"All events\" Url=\"/Lists/Test/All events.aspx\" Level=\"1\" BaseViewID=\"1\" ContentTypeID=\"0x\" ImageUrl=\"/_layouts/15/images/generic.png?rev=47\" ><Query><OrderBy><FieldRef Name=\"Created\" Ascending=\"FALSE\" /></OrderBy><Where><Eq><FieldRef Name=\"TextFieldName\" /><Value Type=\"Text\">Field value</Value></Eq></Where></Query><ViewFields><FieldRef Name=\"Title\" /></ViewFields><RowLimit Paged=\"TRUE\">30</RowLimit><JSLink>clienttemplates.js</JSLink><XslLink Default=\"TRUE\">main.xsl</XslLink><Toolbar Type=\"Standard\"/></View>",
    "Method": null,
    "MobileDefaultView": false,
    "MobileView": false,
    "ModerationType": null,
    "NewDocumentTemplates": null,
    "OrderedView": false,
    "Paged": true,
    "PersonalView": false,
    "ViewProjectedFields": null,
    "ViewQuery": "<OrderBy><FieldRef Name=\"Created\" Ascending=\"FALSE\" /></OrderBy><Where><Eq><FieldRef Name=\"TextFieldName\" /><Value Type=\"Text\">Field value</Value></Eq></Where>",
    "ReadOnlyView": false,
    "RequiresClientIntegration": false,
    "RowLimit": 30,
    "Scope": 0,
    "ServerRelativePath": {
      "DecodedUrl": "/Lists/Test/All events.aspx"
    },
    "ServerRelativeUrl": "/Lists/Test/All events.aspx",
    "StyleId": null,
    "TabularView": true,
    "Threaded": false,
    "Title": "All events",
    "Toolbar": "",
    "ToolbarTemplateName": null,
    "ViewType": "HTML",
    "ViewData": null,
    "ViewType2": null,
    "VisualizationInfo": null
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Aggregations             : null
  AggregationsStatus       : null
  AssociatedContentTypeId  : null
  BaseViewId               : 1
  CalendarViewStyles       : null
  ColumnWidth              : null
  ContentTypeId            : {"StringValue":"0x"}
  CustomFormatter          : null
  CustomOrder              : null
  DefaultView              : false
  DefaultViewForContentType: false
  EditorModified           : false
  Formats                  : null
  GridLayout               : null
  Hidden                   : false
  HtmlSchemaXml            : <View Name="{3CD2E934-F482-4D4A-A9B8-A13B49B3D226}" Type="HTML" DisplayName="All events" Url="/Lists/Test/All events.aspx" Level="1" BaseViewID="1" ContentTypeID="0x" ImageUrl="/_layouts/15/images/generic.png?rev=47"><ViewFields><FieldRef Name="Title" /></ViewFields><Query><OrderBy><FieldRef Name="Created" Ascending="FALSE" /></OrderBy><Where><Eq><FieldRef Name="TextFieldName" /><Value Type="Text">Field value</Value></Eq></Where></Query><RowLimit Paged="TRUE">30</RowLimit><XslLink Default="TRUE">main.xsl</XslLink><JSLink>clienttemplates.js</JSLink><Toolbar Type="Standard" /><ParameterBindings><ParameterBinding Name="NoAnnouncements" Location="Resource(wss,noXinviewofY_LIST)" /><ParameterBinding Name="NoAnnouncementsHowTo" Location="Resource(wss,noXinviewofY_DEFAULT)" /></ParameterBindings></View>
  Id                       : 3cd2e934-f482-4d4a-a9b8-a13b49b3d226
  ImageUrl                 : /_layouts/15/images/generic.png?rev=47
  IncludeRootFolder        : false
  JSLink                   : clienttemplates.js
  ListViewXml              : <View Name="{3CD2E934-F482-4D4A-A9B8-A13B49B3D226}" Type="HTML" DisplayName="All events" Url="/Lists/Test/All events.aspx" Level="1" BaseViewID="1" ContentTypeID="0x" ImageUrl="/_layouts/15/images/generic.png?rev=47" ><Query><OrderBy><FieldRef Name="Created" Ascending="FALSE" /></OrderBy><Where><Eq><FieldRef Name="TextFieldName" /><Value Type="Text">Field value</Value></Eq></Where></Query><ViewFields><FieldRef Name="Title" /></ViewFields><RowLimit Paged="TRUE">30</RowLimit><JSLink>clienttemplates.js</JSLink><XslLink Default="TRUE">main.xsl</XslLink><Toolbar Type="Standard"/></View>
  Method                   : null
  MobileDefaultView        : false
  MobileView               : false
  ModerationType           : null
  NewDocumentTemplates     : null
  OrderedView              : false
  Paged                    : true
  PersonalView             : false
  ReadOnlyView             : false
  RequiresClientIntegration: false
  RowLimit                 : 30
  Scope                    : 0
  ServerRelativePath       : {"DecodedUrl":"/Lists/Test/All events.aspx"}
  ServerRelativeUrl        : /Lists/Test/All events.aspx
  StyleId                  : null
  TabularView              : true
  Threaded                 : false
  Title                    : All events
  Toolbar                  :
  ToolbarTemplateName      : null
  ViewData                 : null
  ViewJoins                : null
  ViewProjectedFields      : null
  ViewQuery                : <OrderBy><FieldRef Name="Created" Ascending="FALSE" /></OrderBy><Where><Eq><FieldRef Name="TextFieldName" /><Value Type="Text">Field value</Value></Eq></Where>
  ViewType                 : HTML
  ViewType2                : null
  VisualizationInfo        : null
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Aggregations,AggregationsStatus,AssociatedContentTypeId,BaseViewId,CalendarViewStyles,ColumnWidth,ContentTypeId,CustomFormatter,CustomOrder,DefaultView,DefaultViewForContentType,EditorModified,Formats,GridLayout,Hidden,HtmlSchemaXml,Id,ImageUrl,IncludeRootFolder,ViewJoins,JSLink,ListViewXml,Method,MobileDefaultView,MobileView,ModerationType,NewDocumentTemplates,OrderedView,Paged,PersonalView,ViewProjectedFields,ViewQuery,ReadOnlyView,RequiresClientIntegration,RowLimit,Scope,ServerRelativePath,ServerRelativeUrl,StyleId,TabularView,Threaded,Title,Toolbar,ToolbarTemplateName,ViewType,ViewData,ViewType2,VisualizationInfo
  ,,,1,,,"{""StringValue"":""0x""}",,,,,,,,,"<View Name=""{3CD2E934-F482-4D4A-A9B8-A13B49B3D226}"" Type=""HTML"" DisplayName=""All events"" Url=""/Lists/Test/All events.aspx"" Level=""1"" BaseViewID=""1"" ContentTypeID=""0x"" ImageUrl=""/_layouts/15/images/generic.png?rev=47""><ViewFields><FieldRef Name=""Title"" /></ViewFields><Query><OrderBy><FieldRef Name=""Created"" Ascending=""FALSE"" /></OrderBy><Where><Eq><FieldRef Name=""TextFieldName"" /><Value Type=""Text"">Field value</Value></Eq></Where></Query><RowLimit Paged=""TRUE"">30</RowLimit><XslLink Default=""TRUE"">main.xsl</XslLink><JSLink>clienttemplates.js</JSLink><Toolbar Type=""Standard"" /><ParameterBindings><ParameterBinding Name=""NoAnnouncements"" Location=""Resource(wss,noXinviewofY_LIST)"" /><ParameterBinding Name=""NoAnnouncementsHowTo"" Location=""Resource(wss,noXinviewofY_DEFAULT)"" /></ParameterBindings></View>",3cd2e934-f482-4d4a-a9b8-a13b49b3d226,/_layouts/15/images/generic.png?rev=47,,,clienttemplates.js,"<View Name=""{3CD2E934-F482-4D4A-A9B8-A13B49B3D226}"" Type=""HTML"" DisplayName=""All events"" Url=""/Lists/Test/All events.aspx"" Level=""1"" BaseViewID=""1"" ContentTypeID=""0x"" ImageUrl=""/_layouts/15/images/generic.png?rev=47"" ><Query><OrderBy><FieldRef Name=""Created"" Ascending=""FALSE"" /></OrderBy><Where><Eq><FieldRef Name=""TextFieldName"" /><Value Type=""Text"">Field value</Value></Eq></Where></Query><ViewFields><FieldRef Name=""Title"" /></ViewFields><RowLimit Paged=""TRUE"">30</RowLimit><JSLink>clienttemplates.js</JSLink><XslLink Default=""TRUE"">main.xsl</XslLink><Toolbar Type=""Standard""/></View>",,,,,,,1,,,"<OrderBy><FieldRef Name=""Created"" Ascending=""FALSE"" /></OrderBy><Where><Eq><FieldRef Name=""TextFieldName"" /><Value Type=""Text"">Field value</Value></Eq></Where>",,,30,0,"{""DecodedUrl"":""/Lists/Test/All events.aspx""}",/Lists/Test/All events.aspx,,1,,All events,,,HTML,,,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo list view get --webUrl "https://contoso.sharepoint.com" --listTitle "My List" --title "All Items"

  Date: 2/20/2023

  ## All Items (6275ed5c-8e4f-4e81-8060-2d9162b29952)

  Property | Value
  ---------|-------
  Aggregations | null
  AggregationsStatus | null
  AssociatedContentTypeId | null
  BaseViewId | 1
  CalendarViewStyles | null
  ColumnWidth | null
  CustomFormatter |
  CustomOrder | null
  DefaultView | true
  DefaultViewForContentType | false
  EditorModified | false
  Formats | null
  GridLayout | null
  Hidden | false
  HtmlSchemaXml | <View Name="{6275ED5C-8E4F-4E81-8060-2D9162B29952}" DefaultView="TRUE" MobileView="TRUE" MobileDefaultView="TRUE" Type="HTML" DisplayName="All Items" Url="/teams/AllStars/Lists/My List/AllItems.aspx" Level="1" BaseViewID="1" ContentTypeID="0x" ImageUrl="/\_layouts/15/images/generic.png?rev=47"><Query /><ViewFields><FieldRef Name="LinkTitle" /><FieldRef Name="FieldName1" /></ViewFields><Toolbar Type="Standard" /><CustomFormatter /><XslLink Default="TRUE">main.xsl</XslLink><JSLink>clienttemplates.js</JSLink><RowLimit Paged="TRUE">30</RowLimit><ParameterBindings><ParameterBinding Name="NoAnnouncements" Location="Resource(wss,noXinviewofY\_LIST)" /><ParameterBinding Name="NoAnnouncementsHowTo" Location="Resource(wss,noXinviewofY\_DEFAULT)" /></ParameterBindings></View>
  Id | 6275ed5c-8e4f-4e81-8060-2d9162b29952
  ImageUrl | /\_layouts/15/images/generic.png?rev=47
  IncludeRootFolder | false
  ViewJoins | null
  JSLink | clienttemplates.js
  ListViewXml | <View Name="{6275ED5C-8E4F-4E81-8060-2D9162B29952}" DefaultView="TRUE" MobileView="TRUE" MobileDefaultView="TRUE" Type="HTML" DisplayName="All Items" Url="/teams/AllStars/Lists/My List/AllItems.aspx" Level="1" BaseViewID="1" ContentTypeID="0x" ImageUrl="/\_layouts/15/images/generic.png?rev=47" ><Query /><ViewFields><FieldRef Name="LinkTitle" /><FieldRef Name="FieldName1" /></ViewFields><RowLimit Paged="TRUE">30</RowLimit><JSLink>clienttemplates.js</JSLink><XslLink Default="TRUE">main.xsl</XslLink><CustomFormatter /><Toolbar Type="Standard"/></View>
  Method | null
  MobileDefaultView | true
  MobileView | true
  ModerationType | null
  NewDocumentTemplates | null
  OrderedView | false
  Paged | true
  PersonalView | false
  ViewProjectedFields | null
  ViewQuery |
  ReadOnlyView | false
  RequiresClientIntegration | false
  RowLimit | 30
  Scope | 0
  ServerRelativeUrl | /teams/AllStars/Lists/My List/AllItems.aspx
  StyleId | null
  TabularView | true
  Threaded | false
  Title | All Items
  Toolbar |
  ToolbarTemplateName | null
  ViewType | HTML
  ViewData | null
  ViewType2 | null
  VisualizationInfo | null
  ```

  </TabItem>
</Tabs>
