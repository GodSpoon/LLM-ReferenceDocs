-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo list sitescript get

Extracts a site script from a SharePoint list

## Usage

```sh
m365 spo list sitescript get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list to extract the site script from is located.

`-l, --listId [listId]`
: ID of the list to extract the site script from. Specify either `listId`, `listTitle`, or `listUrl` but not multiple.

`-t, --listTitle [listTitle]`
: Title of the list to extract the site script from. Specify either `listId`, `listTitle`, or `listUrl` but not multiple.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listId`, `listTitle`, or `listUrl` but not multiple.
```

<Global />

## Examples

Extract a site script from an existing SharePoint list with specified title located in the specified site.

```sh
m365 spo list sitescript get --listTitle ContosoList --webUrl https://contoso.sharepoint.com/sites/project-x
```

Extract a site script from an existing SharePoint list with specified id located in the specified site.

```sh
m365 spo list sitescript get --listId cc27a922-8224-4296-90a5-ebbc54da2e85 --webUrl https://contoso.sharepoint.com/sites/project-x
```

Extract a site script from an existing SharePoint list with specified server relative url located in the specified site.

```sh
m365 spo list sitescript get --listUrl 'sites/project-x/Documents' --webUrl https://contoso.sharepoint.com/sites/project-x
```

Extract a site script from an existing SharePoint list with specified site-relative URL located in the specified site.

```sh
m365 spo list sitescript get --listUrl 'Shared Documents' --webUrl https://contoso.sharepoint.com/sites/project-x
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  "{\
  \"$schema\": \"https://developer.microsoft.com/json-schemas/sp/site-design-script-actions.schema.json\",\
  \"actions\": [\
    {\
      \"verb\": \"createSPList\",\
      \"listName\": \"Test\",\
      \"templateType\": 100,\
      \"color\": \"0\",\
      \"icon\": \"3\",\
      \"subactions\": [\
        {\
          \"verb\": \"addSPFieldXml\",\
          \"schemaXml\": \"<Field ID=\\"{fa564e0f-0c70-4ab9-b863-0177e6ddd247}\\" Type=\\"Text\\" Name=\\"Title\\" DisplayName=\\"Title\\" Required=\\"TRUE\\" SourceID=\\"http://schemas.microsoft.com/sharepoint/v3\\" StaticName=\\"Title\\" FromBaseType=\\"TRUE\\" MaxLength=\\"255\\" />\"\
        },\
        {\
          \"verb\": \"addSPFieldXml\",\
          \"schemaXml\": \"<Field ID=\\"{b77cdbcf-5dce-4937-85a7-9fc202705c91}\\" Group=\\"_Hidden\\" SourceID=\\"http://schemas.microsoft.com/sharepoint/v4\\" Name=\\"IconOverlay\\" StaticName=\\"IconOverlay\\" DisplayName=\\"IconOverlay\\" Type=\\"Text\\" Required=\\"FALSE\\" Hidden=\\"TRUE\\" />\"\
        },\
        {\
          \"verb\": \"addSPFieldXml\",\
          \"schemaXml\": \"<Field CustomFormatter=\\"{&quot;elmType&quot;:&quot;div&quot;,&quot;style&quot;:{&quot;flex-wrap&quot;:&quot;wrap&quot;,&quot;display&quot;:&quot;flex&quot;},&quot;children&quot;:[{&quot;elmType&quot;:&quot;div&quot;,&quot;style&quot;:{&quot;box-sizing&quot;:&quot;border-box&quot;,&quot;padding&quot;:&quot;4px 8px 5px 8px&quot;,&quot;overflow&quot;:&quot;hidden&quot;,&quot;text-overflow&quot;:&quot;ellipsis&quot;,&quot;display&quot;:&quot;flex&quot;,&quot;border-radius&quot;:&quot;16px&quot;,&quot;height&quot;:&quot;24px&quot;,&quot;align-items&quot;:&quot;center&quot;,&quot;white-space&quot;:&quot;nowrap&quot;,&quot;margin&quot;:&quot;4px 4px 4px 4px&quot;},&quot;attributes&quot;:{&quot;class&quot;:{&quot;operator&quot;:&quot;:&quot;,&quot;operands&quot;:[{&quot;operator&quot;:&quot;==&quot;,&quot;operands&quot;:[&quot;@currentField&quot;,&quot;Choice 1&quot;]},&quot;sp-css-backgroundColor-BgCornflowerBlue sp-field-fontSizeSmall sp-css-color-CornflowerBlueFont&quot;,{&quot;operator&quot;:&quot;:&quot;,&quot;operands&quot;:[{&quot;operator&quot;:&quot;==&quot;,&quot;operands&quot;:[&quot;@currentField&quot;,&quot;Choice 2&quot;]},&quot;sp-css-backgroundColor-BgMintGreen sp-field-fontSizeSmall sp-css-color-MintGreenFont&quot;,{&quot;operator&quot;:&quot;:&quot;,&quot;operands&quot;:[{&quot;operator&quot;:&quot;==&quot;,&quot;operands&quot;:[&quot;@currentField&quot;,&quot;Keuze 3&quot;]},&quot;sp-css-backgroundColor-BgGold sp-field-fontSizeSmall sp-css-color-GoldFont&quot;,{&quot;operator&quot;:&quot;:&quot;,&quot;operands&quot;:[{&quot;operator&quot;:&quot;==&quot;,&quot;operands&quot;:[&quot;@currentField&quot;,&quot;&quot;]},&quot;&quot;,&quot;sp-field-borderAllRegular sp-field-borderAllSolid sp-css-borderColor-neutralSecondary&quot;]}]}]}]}},&quot;txtContent&quot;:&quot;@currentField&quot;}],&quot;templateId&quot;:&quot;BgColorChoicePill&quot;}\\" DisplayName=\\"SingleChoiceField\\" FillInChoice=\\"FALSE\\" Format=\\"Dropdown\\" IsModern=\\"TRUE\\" Name=\\"SingleChoiceField\\" Title=\\"SingleChoiceField\\" Type=\\"Choice\\" ID=\\"{9a802215-bf97-4a0d-8268-45785f054711}\\" StaticName=\\"SingleChoiceField\\"><CHOICES><CHOICE>Choice 1</CHOICE><CHOICE>Choice 2</CHOICE><CHOICE>Keuze 3</CHOICE></CHOICES></Field>\"\
        },\
        {\
          \"verb\": \"addSPFieldXml\",\
          \"schemaXml\": \"<Field CustomFormatter=\\"{&quot;elmType&quot;:&quot;div&quot;,&quot;style&quot;:{&quot;flex-wrap&quot;:&quot;wrap&quot;,&quot;display&quot;:&quot;flex&quot;},&quot;children&quot;:[{&quot;forEach&quot;:&quot;__INTERNAL__ in @currentField&quot;,&quot;elmType&quot;:&quot;div&quot;,&quot;style&quot;:{&quot;box-sizing&quot;:&quot;border-box&quot;,&quot;padding&quot;:&quot;4px 8px 5px 8px&quot;,&quot;overflow&quot;:&quot;hidden&quot;,&quot;text-overflow&quot;:&quot;ellipsis&quot;,&quot;display&quot;:&quot;flex&quot;,&quot;border-radius&quot;:&quot;16px&quot;,&quot;height&quot;:&quot;24px&quot;,&quot;align-items&quot;:&quot;center&quot;,&quot;white-space&quot;:&quot;nowrap&quot;,&quot;margin&quot;:&quot;4px 4px 4px 4px&quot;},&quot;attributes&quot;:{&quot;class&quot;:{&quot;operator&quot;:&quot;:&quot;,&quot;operands&quot;:[{&quot;operator&quot;:&quot;==&quot;,&quot;operands&quot;:[&quot;[$__INTERNAL__]&quot;,&quot;Choice 1&quot;]},&quot;sp-css-backgroundColor-BgCornflowerBlue sp-css-color-CornflowerBlueFont&quot;,{&quot;operator&quot;:&quot;:&quot;,&quot;operands&quot;:[{&quot;operator&quot;:&quot;==&quot;,&quot;operands&quot;:[&quot;[$__INTERNAL__]&quot;,&quot;Choice 2&quot;]},&quot;sp-css-backgroundColor-BgMintGreen sp-css-color-MintGreenFont&quot;,{&quot;operator&quot;:&quot;:&quot;,&quot;operands&quot;:[{&quot;operator&quot;:&quot;==&quot;,&quot;operands&quot;:[&quot;[$__INTERNAL__]&quot;,&quot;Keuze 3&quot;]},&quot;sp-css-backgroundColor-BgGold sp-css-color-GoldFont&quot;,&quot;sp-field-borderAllRegular sp-field-borderAllSolid sp-css-borderColor-neutralSecondary&quot;]}]}]}},&quot;txtContent&quot;:&quot;[$__INTERNAL__]&quot;}],&quot;templateId&quot;:&quot;BgColorChoicePill&quot;}\\" DisplayName=\\"MultiChoiceField\\" FillInChoice=\\"FALSE\\" Format=\\"Dropdown\\" IsModern=\\"TRUE\\" Name=\\"MultiChoiceField\\" Title=\\"MultiChoiceField\\" Type=\\"MultiChoice\\" ID=\\"{c4d18d33-4785-4e28-8fe4-fca269d7318d}\\" StaticName=\\"MultiChoiceField\\"><CHOICES><CHOICE>Choice 1</CHOICE><CHOICE>Choice 2</CHOICE><CHOICE>Keuze 3</CHOICE></CHOICES></Field>\"\
        },\
        {\
          \"verb\": \"addSPFieldXml\",\
          \"schemaXml\": \"<Field Type=\\"TaxonomyFieldType\\" DisplayName=\\"SingleMetadataField\\" ShowField=\\"Term1033\\" ID=\\"{29b00c9c-acd6-4ef4-b1b8-84e4e557092b}\\" StaticName=\\"SingleMetadataField\\" Name=\\"SingleMetadataField\\" CustomFormatter=\\"\\" EnforceUniqueValues=\\"FALSE\\" Required=\\"FALSE\\" Group=\\"\\" Hidden=\\"FALSE\\" ReadOnly=\\"FALSE\\" PITarget=\\"\\" PrimaryPITarget=\\"\\" PIAttribute=\\"\\" PrimaryPIAttribute=\\"\\" Aggregation=\\"\\" Node=\\"\\"><Default /><Customization><ArrayOfProperty><Property><Name>SspId</Name><Value xmlns:q1=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q1:string\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">5eb73991-e926-4819-84e6-7c41b553137f</Value></Property><Property><Name>GroupId</Name></Property><Property><Name>TermSetId</Name><Value xmlns:q2=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q2:string\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">8ed8c9ea-7052-4c1d-a4d7-b9c10bffea6f</Value></Property><Property><Name>AnchorId</Name><Value xmlns:q3=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q3:string\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">00000000-0000-0000-0000-000000000000</Value></Property><Property><Name>UserCreated</Name><Value xmlns:q4=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q4:boolean\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">false</Value></Property><Property><Name>Open</Name><Value xmlns:q5=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q5:boolean\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">true</Value></Property><Property><Name>IsPathRendered</Name><Value xmlns:q7=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q7:boolean\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">false</Value></Property><Property><Name>IsKeyword</Name><Value xmlns:q8=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q8:boolean\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">false</Value></Property><Property><Name>TargetTemplate</Name></Property><Property><Name>CreateValuesInEditForm</Name><Value xmlns:q9=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q9:boolean\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">false</Value></Property><Property><Name>IsDocTagsEnabled</Name></Property><Property><Name>FilterAssemblyStrongName</Name><Value xmlns:q10=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q10:string\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">Microsoft.SharePoint.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c</Value></Property><Property><Name>FilterClassName</Name><Value xmlns:q11=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q11:string\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">EXAMPLE_SECRET_VALUE_PLACEHOLDER</Value></Property><Property><Name>FilterMethodName</Name><Value xmlns:q12=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q12:string\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">GetFilteringHtml</Value></Property><Property><Name>FilterJavascriptProperty</Name><Value xmlns:q13=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q13:string\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">FilteringJavascript</Value></Property></ArrayOfProperty></Customization></Field>\"\
        },\
        {\
          \"verb\": \"addSPFieldXml\",\
          \"schemaXml\": \"<Field Type=\\"TaxonomyFieldTypeMulti\\" DisplayName=\\"MultiMetadataField\\" ShowField=\\"Term1033\\" ID=\\"{b1841001-0027-4934-899c-d69a928f35f6}\\" StaticName=\\"MultiMetadataField\\" Name=\\"MultiMetadataField\\" CustomFormatter=\\"\\" EnforceUniqueValues=\\"FALSE\\" Required=\\"FALSE\\" Mult=\\"TRUE\\" Sortable=\\"FALSE\\"><Default /><Customization><ArrayOfProperty><Property><Name>SspId</Name><Value xmlns:q1=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q1:string\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">5eb73991-e926-4819-84e6-7c41b553137f</Value></Property><Property><Name>GroupId</Name></Property><Property><Name>TermSetId</Name><Value xmlns:q2=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q2:string\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">8ed8c9ea-7052-4c1d-a4d7-b9c10bffea6f</Value></Property><Property><Name>AnchorId</Name><Value xmlns:q3=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q3:string\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">00000000-0000-0000-0000-000000000000</Value></Property><Property><Name>UserCreated</Name><Value xmlns:q4=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q4:boolean\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">false</Value></Property><Property><Name>Open</Name><Value xmlns:q5=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q5:boolean\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">true</Value></Property><Property><Name>IsPathRendered</Name><Value xmlns:q7=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q7:boolean\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">false</Value></Property><Property><Name>IsKeyword</Name><Value xmlns:q8=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q8:boolean\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">false</Value></Property><Property><Name>TargetTemplate</Name></Property><Property><Name>CreateValuesInEditForm</Name><Value xmlns:q9=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q9:boolean\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">false</Value></Property><Property><Name>IsDocTagsEnabled</Name></Property><Property><Name>FilterAssemblyStrongName</Name><Value xmlns:q10=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q10:string\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">Microsoft.SharePoint.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c</Value></Property><Property><Name>FilterClassName</Name><Value xmlns:q11=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q11:string\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">EXAMPLE_SECRET_VALUE_PLACEHOLDER</Value></Property><Property><Name>FilterMethodName</Name><Value xmlns:q12=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q12:string\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">GetFilteringHtml</Value></Property><Property><Name>FilterJavascriptProperty</Name><Value xmlns:q13=\\"http://www.w3.org/2001/XMLSchema\\" p4:type=\\"q13:string\\" xmlns:p4=\\"http://www.w3.org/2001/XMLSchema-instance\\">FilteringJavascript</Value></Property></ArrayOfProperty></Customization></Field>\"\
        },\
        {\
          \"verb\": \"addSPFieldXml\",\
          \"schemaXml\": \"<Field DisplayName=\\"SinglePeopleField\\" Format=\\"Dropdown\\" IsModern=\\"TRUE\\" List=\\"UserInfo\\" Name=\\"SinglePeopleField\\" Title=\\"SinglePeopleField\\" Type=\\"User\\" UserSelectionMode=\\"0\\" UserSelectionScope=\\"0\\" ID=\\"{992ba361-cf48-4c97-bf1e-c396db955e83}\\" StaticName=\\"SinglePeopleField\\" />\"\
        },\
        {\
          \"verb\": \"addSPFieldXml\",\
          \"schemaXml\": \"<Field DisplayName=\\"MultiPeopleField\\" Format=\\"Dropdown\\" IsModern=\\"TRUE\\" List=\\"UserInfo\\" Mult=\\"TRUE\\" Name=\\"MultiPeopleField\\" Title=\\"MultiPeopleField\\" Type=\\"UserMulti\\" UserSelectionMode=\\"0\\" UserSelectionScope=\\"0\\" ID=\\"{a0472ca6-203b-49c0-8fef-92777426e501}\\" StaticName=\\"MultiPeopleField\\" />\"\
        },\
        {\
          \"verb\": \"addSPFieldXml\",\
          \"schemaXml\": \"<Field DisplayName=\\"CustomHyperlink\\" Format=\\"Hyperlink\\" IsModern=\\"TRUE\\" Name=\\"CustomHyperlink\\" Title=\\"CustomHyperlink\\" Type=\\"URL\\" ID=\\"{9a9d8ba3-bbdc-467c-9a5d-9e8c3c73d85b}\\" StaticName=\\"CustomHyperlink\\" />\"\
        },\
        {\
          \"verb\": \"addSPFieldXml\",\
          \"schemaXml\": \"<Field CommaSeparator=\\"TRUE\\" CustomUnitOnRight=\\"TRUE\\" DisplayName=\\"NumberField\\" Format=\\"Dropdown\\" IsModern=\\"TRUE\\" Name=\\"NumberField\\" Percentage=\\"FALSE\\" Title=\\"NumberField\\" Type=\\"Number\\" Unit=\\"None\\" ID=\\"{57b7fd13-0d94-4c76-a57b-3b3224461f70}\\" StaticName=\\"NumberField\\" />\"\
        },\
        {\
          \"verb\": \"addSPFieldXml\",\
          \"schemaXml\": \"<Field ID=\\"{82642ec8-ef9b-478f-acf9-31f7d45fbc31}\\" ReadOnly=\\"TRUE\\" Type=\\"Computed\\" Name=\\"LinkTitle\\" DisplayName=\\"Titel\\" DisplayNameSrcField=\\"Title\\" ClassInfo=\\"Menu\\" AuthoringInfo=\\"(linked to item with edit menu)\\" ListItemMenuAllowed=\\"Required\\" LinkToItemAllowed=\\"Prohibited\\" SourceID=\\"http://schemas.microsoft.com/sharepoint/v3\\" StaticName=\\"LinkTitle\\" FromBaseType=\\"TRUE\\"><FieldRefs><FieldRef Name=\\"Title\\" /><FieldRef Name=\\"LinkTitleNoMenu\\" /><FieldRef Name=\\"_EditMenuTableStart2\\" /><FieldRef Name=\\"_EditMenuTableEnd\\" /></FieldRefs><DisplayPattern><FieldSwitch><Expr><GetVar Name=\\"FreeForm\\" /></Expr><Case Value=\\"TRUE\\"><Field Name=\\"LinkTitleNoMenu\\" /></Case><Default><HTML><![CDATA[<div class=\\"ms-vb itx\\" onmouseover=\\"OnItem(this)\\" CTXName=\\"ctx]]></HTML><Field Name=\\"_EditMenuTableStart2\\" /><HTML><![CDATA[\\">]]></HTML><Field Name=\\"LinkTitleNoMenu\\" /><HTML><![CDATA[</div>]]></HTML><HTML><![CDATA[<div class=\\"s4-ctx\\" onmouseover=\\"OnChildItem(this.parentNode); return false;\\">]]></HTML><HTML><![CDATA[<span>&nbsp;</span>]]></HTML><HTML><![CDATA[<a onfocus=\\"OnChildItem(this.parentNode.parentNode); return false;\\" onclick=\\"PopMenuFromChevron(event); return false;\\" href=\\"javascript:;\\" title=\\"Open Menu\\"></a>]]></HTML><HTML><![CDATA[<span>&nbsp;</span>]]></HTML><HTML><![CDATA[</div>]]></HTML></Default></FieldSwitch></DisplayPattern></Field>\"\
        },\
        {\
          \"verb\": \"addSPFieldXml\",\
          \"schemaXml\": \"<Field ID=\\"{f9a44731-84eb-43a4-9973-cd2953ad8646}\\" Name=\\"_vti_ItemDeclaredRecord\\" StaticName=\\"_vti_ItemDeclaredRecord\\" DisplayName=\\"Declared Record\\" SourceID=\\"http://schemas.microsoft.com/sharepoint/v3\\" Group=\\"Document and Record Management Columns\\" Type=\\"DateTime\\" Indexed=\\"FALSE\\" Hidden=\\"FALSE\\" CanToggleHidden=\\"TRUE\\" ShowInNewForm=\\"FALSE\\" ShowInEditForm=\\"FALSE\\" ShowInFileDlg=\\"FALSE\\" ShowInDisplayForm=\\"TRUE\\" Required=\\"FALSE\\" Sealed=\\"TRUE\\" ReadOnly=\\"TRUE\\" />\"\
        },\
        {\
          \"verb\": \"addSPFieldXml\",\
          \"schemaXml\": \"<Field ID=\\"{3afcc5c7-c6ef-44f8-9479-3561d72f9e8e}\\" Name=\\"_vti_ItemHoldRecordStatus\\" StaticName=\\"_vti_ItemHoldRecordStatus\\" DisplayName=\\"Hold and Record Status\\" SourceID=\\"http://schemas.microsoft.com/sharepoint/v3\\" Group=\\"Document and Record Management Columns\\" Type=\\"Integer\\" Min=\\"0\\" Max=\\"32\\" Decimals=\\"0\\" Indexed=\\"TRUE\\" Hidden=\\"TRUE\\" CanToggleHidden=\\"FALSE\\" ShowInNewForm=\\"FALSE\\" ShowInEditForm=\\"FALSE\\" ShowInFileDlg=\\"FALSE\\" ShowInDisplayForm=\\"FALSE\\" Required=\\"FALSE\\" Sealed=\\"TRUE\\" ReadOnly=\\"TRUE\\" Description=\\"\\" />\"\
        },\
        {\
          \"verb\": \"addSPFieldXml\",\
          \"schemaXml\": \"<Field Type=\\"Note\\" DisplayName=\\"SingleMetadataField_0\\" StaticName=\\"i9b00c9cacd64ef4b1b884e4e557092b\\" Name=\\"i9b00c9cacd64ef4b1b884e4e557092b\\" ID=\\"{655fadc8-4d62-49d8-bd3f-8c25ea0c2cce}\\" ShowInViewForms=\\"FALSE\\" Required=\\"FALSE\\" Hidden=\\"TRUE\\" CanToggleHidden=\\"TRUE\\" />\"\
        },\
        {\
          \"verb\": \"addSPLookupFieldXml\",\
          \"schemaXml\": \"<Field Type=\\"LookupMulti\\" DisplayName=\\"Taxonomy Catch All Column\\" StaticName=\\"TaxCatchAll\\" Name=\\"TaxCatchAll\\" ID=\\"{f3b0adf9-c1a2-4b02-920d-943fba4b3611}\\" ShowInViewForms=\\"FALSE\\" Required=\\"FALSE\\" Hidden=\\"TRUE\\" CanToggleHidden=\\"TRUE\\" ShowField=\\"CatchAllData\\" Mult=\\"TRUE\\" Sortable=\\"FALSE\\" AllowDeletion=\\"TRUE\\" Sealed=\\"TRUE\\" />\",\
          \"targetListName\": \"TaxonomyHiddenList\"\
        },\
        {\
          \"verb\": \"addSPFieldXml\",\
          \"schemaXml\": \"<Field Type=\\"Note\\" DisplayName=\\"MultiMetadataField_0\\" StaticName=\\"b184100100274934899cd69a928f35f6\\" Name=\\"b184100100274934899cd69a928f35f6\\" ID=\\"{c46e453f-0142-4231-8a29-e15df0832c39}\\" ShowInViewForms=\\"FALSE\\" Required=\\"FALSE\\" Hidden=\\"TRUE\\" CanToggleHidden=\\"TRUE\\" />\"\
        },\
        {\
          \"verb\": \"addContentType\",\
          \"name\": \"Item\",\
          \"id\": \"0x01\",\
          \"fieldRefsXml\": [\
            \"<FieldRef ID=\\"{fa564e0f-0c70-4ab9-b863-0177e6ddd247}\\" Name=\\"Title\\" />\",\
            \"<FieldRef ID=\\"{82642ec8-ef9b-478f-acf9-31f7d45fbc31}\\" Name=\\"LinkTitle\\" DisplayName=\\"Titel\\" ReadOnly=\\"TRUE\\" />\",\
            \"<FieldRef ID=\\"{b77cdbcf-5dce-4937-85a7-9fc202705c91}\\" Name=\\"IconOverlay\\" Required=\\"FALSE\\" />\",\
            \"<FieldRef ID=\\"{f9a44731-84eb-43a4-9973-cd2953ad8646}\\" Name=\\"_vti_ItemDeclaredRecord\\" Required=\\"FALSE\\" ReadOnly=\\"TRUE\\" />\",\
            \"<FieldRef ID=\\"{3afcc5c7-c6ef-44f8-9479-3561d72f9e8e}\\" Name=\\"_vti_ItemHoldRecordStatus\\" DisplayName=\\"Hold and Record Status\\" Required=\\"FALSE\\" Hidden=\\"TRUE\\" ShowInNewForm=\\"FALSE\\" ShowInEditForm=\\"FALSE\\" ShowInDisplayForm=\\"FALSE\\" ShowInFileDlg=\\"FALSE\\" ReadOnly=\\"TRUE\\" />\",\
            \"<FieldRef ID=\\"{9a802215-bf97-4a0d-8268-45785f054711}\\" Name=\\"SingleChoiceField\\" />\",\
\"<FieldRef ID=\\"{c4d18d33-4785-4e28-8fe4-fca269d7318d}\\" Name=\\"MultiChoiceField\\" />\",\
            \"<FieldRef ID=\\"{29b00c9c-acd6-4ef4-b1b8-84e4e557092b}\\" Name=\\"SingleMetadataField\\" DisplayName=\\"SingleMetadataField\\" Required=\\"FALSE\\" Hidden=\\"FALSE\\" ReadOnly=\\"FALSE\\" PITarget=\\"\\" PrimaryPITarget=\\"\\" PIAttribute=\\"\\" PrimaryPIAttribute=\\"\\" Aggregation=\\"\\" Node=\\"\\" />\",\
            \"<FieldRef ID=\\"{655fadc8-4d62-49d8-bd3f-8c25ea0c2cce}\\" Name=\\"i9b00c9cacd64ef4b1b884e4e557092b\\" Required=\\"FALSE\\" />\",\
            \"<FieldRef ID=\\"{f3b0adf9-c1a2-4b02-920d-943fba4b3611}\\" Name=\\"TaxCatchAll\\" Required=\\"FALSE\\" />\",\
            \"<FieldRef ID=\\"{b1841001-0027-4934-899c-d69a928f35f6}\\" Name=\\"MultiMetadataField\\" DisplayName=\\"MultiMetadataField\\" Required=\\"FALSE\\" />\",\
            \"<FieldRef ID=\\"{c46e453f-0142-4231-8a29-e15df0832c39}\\" Name=\\"b184100100274934899cd69a928f35f6\\" Required=\\"FALSE\\" />\",\
            \"<FieldRef ID=\\"{992ba361-cf48-4c97-bf1e-c396db955e83}\\" Name=\\"SinglePeopleField\\" />\",\
            \"<FieldRef ID=\\"{a0472ca6-203b-49c0-8fef-92777426e501}\\" Name=\\"MultiPeopleField\\" />\",\
\"<FieldRef ID=\\"{9a9d8ba3-bbdc-467c-9a5d-9e8c3c73d85b}\\" Name=\\"CustomHyperlink\\" />\",\
            \"<FieldRef ID=\\"{57b7fd13-0d94-4c76-a57b-3b3224461f70}\\" Name=\\"NumberField\\" />\"\
          ]\
        },\
        {\
          \"verb\": \"addContentType\",\
          \"name\": \"Folder\",\
          \"id\": \"0x0120\"\
        },\
        {\
          \"verb\": \"addSPView\",\
          \"name\": \"Alle items\",\
          \"viewFields\": [\
            \"ID\",\
            \"LinkTitle\",\
            \"SingleChoiceField\",\
            \"MultiChoiceField\",\
            \"SingleMetadataField\",\
            \"MultiMetadataField\",\
            \"SinglePeopleField\",\
            \"MultiPeopleField\",\
            \"CustomHyperlink\",\
            \"NumberField\"\
          ],\
          \"query\": \"\",\
          \"rowLimit\": 30,\
          \"isPaged\": true,\
          \"makeDefault\": true,\
          \"formatterJSON\": \"\",\
          \"replaceViewFields\": true\
        }\
      ]\
    }\
  ]\
}"
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  {
    "$schema": "https://developer.microsoft.com/json-schemas/sp/site-design-script-actions.schema.json",
    "actions": [
      {
        "verb": "createSPList",
        "listName": "Test",
        "templateType": 100,
        "color": "0",
        "icon": "3",
        "subactions": [
          {
            "verb": "addSPView",
            "name": "Alle items",
            "viewFields": [
              "ID"
            ],
            "query": "",
            "rowLimit": 30,
            "isPaged": true,
            "makeDefault": true,
            "formatterJSON": "",
            "replaceViewFields": true
          }
        ]
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  {
    "$schema": "https://developer.microsoft.com/json-schemas/sp/site-design-script-actions.schema.json",
    "actions": [
      {
        "verb": "createSPList",
        "listName": "Test",
        "templateType": 100,
        "color": "0",
        "icon": "3",
        "subactions": [
          {
            "verb": "addSPView",
            "name": "Alle items",
            "viewFields": [
              "ID"
            ],
            "query": "",
            "rowLimit": 30,
            "isPaged": true,
            "makeDefault": true,
            "formatterJSON": "",
            "replaceViewFields": true
          }
        ]
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  {
    "$schema": "https://developer.microsoft.com/json-schemas/sp/site-design-script-actions.schema.json",
    "actions": [
      {
        "verb": "createSPList",
        "listName": "Test",
        "templateType": 100,
        "color": "0",
        "icon": "3",
        "subactions": [
          {
            "verb": "addSPView",
            "name": "Alle items",
            "viewFields": [
              "ID"
            ],
            "query": "",
            "rowLimit": 30,
            "isPaged": true,
            "makeDefault": true,
            "formatterJSON": "",
            "replaceViewFields": true
          }
        ]
      }
    ]
  }
  ```

  </TabItem>
</Tabs>
