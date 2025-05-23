-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo list list

Gets all lists within the specified site

## Usage

```sh
m365 spo list list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the lists to retrieve are located.

`-p, --properties [properties]`
: Comma-separated list of properties to retrieve. Will retrieve all properties if not specified.

`--filter [filter]`
: OData filter to use to query the lists with.
```

<Global />

## Remarks

When the `--properties` option includes values with a `/`, for example: `RootFolder/ServerRelativeUrl`, an additional `$expand` query parameter should be included on `RootFolder`.

## Examples

Return all lists located in in a specific site.

```sh
m365 spo list list --webUrl https://contoso.sharepoint.com/sites/project-x
```

Return all lists located in in a specific site with specific properties.

```sh
m365 spo list list --webUrl https://contoso.sharepoint.com/sites/project-x --properties "BaseTemplate,ParentWebUrl"
```

Return all lists located in in a specific site with the Id, Title and ServerRelativeUrl properties.

```sh
m365 spo list list --webUrl https://contoso.sharepoint.com/sites/project-x --properties "Id,Title,RootFolder/ServerRelativeUrl"
```

Return all lists located in in a specific site based on the given filter.

```sh
m365 spo list list --webUrl https://contoso.sharepoint.com/sites/project-x --filter "BaseTemplate eq 100"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "RootFolder": {
        "ServerRelativeUrl": "/_catalogs/theme"
      },
      "AllowContentTypes": true,
      "BaseTemplate": 123,
      "BaseType": 1,
      "ContentTypesEnabled": false,
      "CrawlNonDefaultViews": false,
      "Created": "2020-01-12T01:03:13Z",
      "CurrentChangeToken": {
        "StringValue": "1;3;66e5148c-7060-4479-88e7-636d79579148;638042267256930000;564174226"
      },
      "DefaultContentApprovalWorkflowId": "00000000-0000-0000-0000-000000000000",
      "DefaultItemOpenUseListSetting": false,
      "Description": "Use the theme gallery to store themes. The themes in this gallery can be used by this site or any of its subsites.",
      "Direction": "none",
      "DisableCommenting": false,
      "DisableGridEditing": false,
      "DocumentTemplateUrl": null,
      "DraftVersionVisibility": 0,
      "EnableAttachments": false,
      "EnableFolderCreation": false,
      "EnableMinorVersions": false,
      "EnableModeration": false,
      "EnableRequestSignOff": true,
      "EnableVersioning": false,
      "EntityTypeName": "OData__x005f_catalogs_x002f_theme",
      "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
      "FileSavePostProcessingEnabled": false,
      "ForceCheckout": false,
      "HasExternalDataSource": false,
      "Hidden": true,
      "Id": "66e5148c-7060-4479-88e7-636d79579148",
      "ImagePath": {
        "DecodedUrl": "/_layouts/15/images/itdl.png?rev=47"
      },
      "ImageUrl": "/_layouts/15/images/itdl.png?rev=47",
      "DefaultSensitivityLabelForLibrary": "",
      "IrmEnabled": false,
      "IrmExpire": false,
      "IrmReject": false,
      "IsApplicationList": false,
      "IsCatalog": true,
      "IsPrivate": false,
      "ItemCount": 41,
      "LastItemDeletedDate": "2020-01-12T01:03:13Z",
      "LastItemModifiedDate": "2020-01-12T01:03:18Z",
      "LastItemUserModifiedDate": "2020-01-12T01:03:18Z",
      "ListExperienceOptions": 0,
      "ListItemEntityTypeFullName": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "MajorVersionLimit": 0,
      "MajorWithMinorVersionsLimit": 0,
      "MultipleDataList": false,
      "NoCrawl": true,
      "ParentWebPath": {
        "DecodedUrl": "/"
      },
      "ParentWebUrl": "/",
      "ParserDisabled": false,
      "ServerTemplateCanCreateFolders": false,
      "TemplateFeatureId": "00000000-0000-0000-0000-000000000000",
      "Title": "Theme Gallery"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Id                                    Title
  ------------------------------------  ----------------
  66e5148c-7060-4479-88e7-636d79579148  Theme Gallery
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Id,Title
  66e5148c-7060-4479-88e7-636d79579148,Theme Gallery
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo list list --webUrl "https://contoso.sharepoint.com"

  Date: 2/20/2023

  ## _catalogs/theme (66e5148c-7060-4479-88e7-636d79579148)

  Property | Value
  ---------|-------
  AllowContentTypes | true
  BaseTemplate | 123
  BaseType | 1
  ContentTypesEnabled | false
  CrawlNonDefaultViews | false
  Created | 2020-01-12T01:03:13Z
  DefaultContentApprovalWorkflowId | 00000000-0000-0000-0000-000000000000
  DefaultItemOpenUseListSetting | false
  Description | Use the theme gallery to store themes. The themes in this gallery can be used by this site or any of its subsites.
  Direction | none
  DisableCommenting | false
  DisableGridEditing | false
  DocumentTemplateUrl | null
  DraftVersionVisibility | 0
  EnableAttachments | false
  EnableFolderCreation | false
  EnableMinorVersions | false
  EnableModeration | false
  EnableRequestSignOff | true
  EnableVersioning | false
  EntityTypeName | OData\_\_x005f\_catalogs\_x002f\_theme
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  FileSavePostProcessingEnabled | false
  ForceCheckout | false
  HasExternalDataSource | false
  Hidden | true
  Id | 66e5148c-7060-4479-88e7-636d79579148
  ImageUrl | /\_layouts/15/images/itdl.png?rev=47
  DefaultSensitivityLabelForLibrary |
  IrmEnabled | false
  IrmExpire | false
  IrmReject | false
  IsApplicationList | false
  IsCatalog | true
  IsPrivate | false
  ItemCount | 41
  LastItemDeletedDate | 2020-01-12T01:03:13Z
  LastItemModifiedDate | 2020-01-12T01:03:18Z
  LastItemUserModifiedDate | 2020-01-12T01:03:18Z
  ListExperienceOptions | 0
  ListItemEntityTypeFullName | SP.Data.OData\_\_x005f\_catalogs\_x002f\_themeItem
  MajorVersionLimit | 0
  MajorWithMinorVersionsLimit | 0
  MultipleDataList | false
  NoCrawl | false
  ParentWebUrl | /
  ParserDisabled | false
  ServerTemplateCanCreateFolders | true
  TemplateFeatureId | 00000000-0000-0000-0000-000000000000
  Title | Theme Gallery
  ```

  </TabItem>
</Tabs>

## More information

- List REST API resources: [https://msdn.microsoft.com/en-us/library/office/dn531433.aspx#bk_ListEndpoint](https://msdn.microsoft.com/en-us/library/office/dn531433.aspx#bk_ListEndpoint)
