-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo list get

Gets information about the specific list

## Usage

```sh
m365 spo list get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list to retrieve is located.

`-i, --id [id]`
: ID of the list to retrieve information for. Specify either `id`, `title`,`url` or `default` but not multiple.

`-t, --title [title]`
: Title of the list to retrieve information for. Specify either `id`, `title`,`url` or `default` but not multiple.

`--url [url]`
: Server- or site-relative URL of the list. Specify either `id`, `title`,`url` or `default` but not multiple.

`--default`
: Set to retrieve the default list from the site. Specify either `id`, `title`, `url`, or `default` but not multiple.  

`-p, --properties [properties]`
: Comma-separated list of properties to retrieve from the list. Will retrieve all properties possible from default response, if not specified.

`--withPermissions`
: Set if you want to return associated roles and permissions of the list.
```

<Global />

## Remarks

When the `properties` option includes values with a `/`, for example: `ListItemAllFields/Id`, an additional `$expand` query parameter will be included on `ListItemAllFields`.

## Examples

Get the default document library located in the specified site.

```sh
m365 spo list get --webUrl https://contoso.sharepoint.com/sites/project-x --default  
```

Get information about a list with specified ID located in the specified site.

```sh
m365 spo list get --id 0cd891ef-afce-4e55-b836-fce03286cccf --webUrl https://contoso.sharepoint.com/sites/project-x
```

Get information about a list with specified title located in the specified site.

```sh
m365 spo list get --title Documents --webUrl https://contoso.sharepoint.com/sites/project-x
```

Get information about a list with specified server relative url located in the specified site.

```sh
m365 spo list get --url 'sites/project-x/Documents' --webUrl https://contoso.sharepoint.com/sites/project-x
```

Get information about a list with specified site-relative URL located in the specified site.

```sh
m365 spo list get --url 'Shared Documents' --webUrl https://contoso.sharepoint.com/sites/project-x
```

Get information about a list returning the specified list properties.

```sh
m365 spo list get --title Documents --webUrl https://contoso.sharepoint.com/sites/project-x --properties "Title,Id,HasUniqueRoleAssignments,AllowContentTypes"
```

Get information about a list returning the list Id, Title and ServerRelativeUrl properties.

```sh
m365 spo list get --title Documents --webUrl https://contoso.sharepoint.com/sites/project-x --properties "Title,Id,RootFolder/ServerRelativeUrl"
```

Get information about a list along with the roles and permissions.

```sh
m365 spo list get --title Documents --webUrl https://contoso.sharepoint.com/sites/project-x --withPermissions
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "VersionPolicies": {
      "DefaultExpireAfterDays": 0,
      "DefaultTrimMode": 0,
      "DefaultTrimModeValue": "NoExpiration"
    },
    "AllowContentTypes": true,
    "BaseTemplate": 100,
    "BaseType": 0,
    "ContentTypesEnabled": true,
    "CrawlNonDefaultViews": false,
    "Created": "2022-10-23T09:30:00Z",
    "CurrentChangeToken": {
      "StringValue": "1;3;97d19285-b8a6-4c7f-9c6c-d6b850a6561a;638042258222730000;564169620"
    },
    "DefaultContentApprovalWorkflowId": "00000000-0000-0000-0000-000000000000",
    "DefaultItemOpenUseListSetting": false,
    "Description": "",
    "Direction": "none",
    "DisableCommenting": false,
    "DisableGridEditing": false,
    "DocumentTemplateUrl": null,
    "DraftVersionVisibility": 0,
    "EnableAttachments": true,
    "EnableFolderCreation": false,
    "EnableMinorVersions": false,
    "EnableModeration": false,
    "EnableRequestSignOff": true,
    "EnableVersioning": true,
    "EntityTypeName": "TestList",
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
    "FileSavePostProcessingEnabled": false,
    "ForceCheckout": false,
    "HasExternalDataSource": false,
    "Hidden": false,
    "Id": "97d19285-b8a6-4c7f-9c6c-d6b850a6561a",
    "ImagePath": {
      "DecodedUrl": "/_layouts/15/images/itgen.png?rev=47"
    },
    "ImageUrl": "/_layouts/15/images/itgen.png?rev=47",
    "DefaultSensitivityLabelForLibrary": "",
    "IrmEnabled": false,
    "IrmExpire": false,
    "IrmReject": false,
    "IsApplicationList": false,
    "IsCatalog": false,
    "IsPrivate": false,
    "ItemCount": 0,
    "LastItemDeletedDate": "2022-11-16T19:55:37Z",
    "LastItemModifiedDate": "2022-11-16T19:55:39Z",
    "LastItemUserModifiedDate": "2022-11-16T19:55:37Z",
    "ListExperienceOptions": 0,
    "ListItemEntityTypeFullName": "SP.Data.TestListItem",
    "MajorVersionLimit": 50,
    "MajorWithMinorVersionsLimit": 0,
    "MultipleDataList": false,
    "NoCrawl": false,
    "ParentWebPath": {
      "DecodedUrl": "/"
    },
    "ParentWebUrl": "/",
    "ParserDisabled": false,
    "ServerTemplateCanCreateFolders": true,
    "TemplateFeatureId": "00bfea71-de22-43b2-a848-c05709900100",
    "Title": "Test"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  AllowContentTypes                        : true
  BaseTemplate                             : 100
  BaseType                                 : 0
  ContentTypesEnabled                      : true
  CrawlNonDefaultViews                     : false
  Created                                  : 2022-10-23T09:30:00Z
  CurrentChangeToken                       : {"StringValue":"1;3;97d19285-b8a6-4c7f-9c6c-d6b850a6561a;638042258464070000;564169707"}
  DefaultContentApprovalWorkflowId         : 00000000-0000-0000-0000-000000000000
  DefaultItemOpenUseListSetting            : false
  DefaultSensitivityLabelForLibrary        :
  Description                              :
  Direction                                : none
  DisableCommenting                        : false
  DisableGridEditing                       : false
  DocumentTemplateUrl                      : null
  DraftVersionVisibility                   : 0
  EnableAttachments                        : true
  EnableFolderCreation                     : false
  EnableMinorVersions                      : false
  EnableModeration                         : false
  EnableRequestSignOff                     : true
  EnableVersioning                         : true
  EntityTypeName                           : TestList
  EXAMPLE_SECRET_VALUE_PLACEHOLDER: false
  FileSavePostProcessingEnabled            : false
  ForceCheckout                            : false
  HasExternalDataSource                    : false
  Hidden                                   : false
  Id                                       : 97d19285-b8a6-4c7f-9c6c-d6b850a6561a
  ImagePath                                : {"DecodedUrl":"/_layouts/15/images/itgen.png?rev=47"}
  ImageUrl                                 : /_layouts/15/images/itgen.png?rev=47
  IrmEnabled                               : false
  IrmExpire                                : false
  IrmReject                                : false
  IsApplicationList                        : false
  IsCatalog                                : false
  IsPrivate                                : false
  ItemCount                                : 0
  LastItemDeletedDate                      : 2022-11-16T19:55:37Z
  LastItemModifiedDate                     : 2022-11-16T19:55:39Z
  LastItemUserModifiedDate                 : 2022-11-16T19:55:37Z
  ListExperienceOptions                    : 0
  ListItemEntityTypeFullName               : SP.Data.TestListItem
  MajorVersionLimit                        : 50
  MajorWithMinorVersionsLimit              : 0
  MultipleDataList                         : false
  NoCrawl                                  : false
  ParentWebPath                            : {"DecodedUrl":"/"}
  ParentWebUrl                             : /
  ParserDisabled                           : false
  ServerTemplateCanCreateFolders           : true
  TemplateFeatureId                        : 00bfea71-de22-43b2-a848-c05709900100
  Title                                    : Test
  VersionPolicies                          : {"DefaultExpireAfterDays": 0,"DefaultTrimMode": 0,"DefaultTrimModeValue": "NoExpiration"}
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  AllowContentTypes,BaseTemplate,BaseType,ContentTypesEnabled,CrawlNonDefaultViews,Created,CurrentChangeToken,DefaultContentApprovalWorkflowId,DefaultItemOpenUseListSetting,Description,Direction,DisableCommenting,DisableGridEditing,DocumentTemplateUrl,DraftVersionVisibility,EnableAttachments,EnableFolderCreation,EnableMinorVersions,EnableModeration,EnableRequestSignOff,EnableVersioning,EntityTypeName,EXAMPLE_SECRET_VALUE_PLACEHOLDER,FileSavePostProcessingEnabled,ForceCheckout,HasExternalDataSource,Hidden,Id,ImagePath,ImageUrl,DefaultSensitivityLabelForLibrary,IrmEnabled,IrmExpire,IrmReject,IsApplicationList,IsCatalog,IsPrivate,ItemCount,LastItemDeletedDate,LastItemModifiedDate,LastItemUserModifiedDate,ListExperienceOptions,ListItemEntityTypeFullName,MajorVersionLimit,MajorWithMinorVersionsLimit,MultipleDataList,NoCrawl,ParentWebPath,ParentWebUrl,ParserDisabled,ServerTemplateCanCreateFolders,TemplateFeatureId,Title
  1,100,0,1,,2022-10-23T09:30:00Z,"{""StringValue"":""1;3;97d19285-b8a6-4c7f-9c6c-d6b850a6561a;638042258543870000;564169743""}",00000000-0000-0000-0000-000000000000,,,none,,,,0,1,,,,1,1,TestList,,,,,,97d19285-b8a6-4c7f-9c6c-d6b850a6561a,"{""DecodedUrl"":""/_layouts/15/images/itgen.png?rev=47""}",/_layouts/15/images/itgen.png?rev=47,,,,,,,,0,2022-11-16T19:55:37Z,2022-11-16T19:55:39Z,2022-11-16T19:55:37Z,0,SP.Data.TestListItem,50,0,,,"{""DecodedUrl"":""/""}",/,,1,00bfea71-de22-43b2-a848-c05709900100,Test
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo list get --title "Test" --webUrl "https://contoso.sharepoint.com"

  Date: 2/20/2023

  ## Test (97d19285-b8a6-4c7f-9c6c-d6b850a6561a)

  Property | Value
  ---------|-------
  AllowContentTypes | true
  BaseTemplate | 100
  BaseType | 0
  ContentTypesEnabled | false
  CrawlNonDefaultViews | false
  Created | 2022-10-23T09:30:00Z
  DefaultContentApprovalWorkflowId | 00000000-0000-0000-0000-000000000000
  DefaultItemOpenUseListSetting | false
  Description |
  Direction | none
  DisableCommenting | false
  DisableGridEditing | false
  DocumentTemplateUrl | 
  DraftVersionVisibility | 0
  EnableAttachments | true
  EnableFolderCreation | false
  EnableMinorVersions | false
  EnableModeration | false
  EnableRequestSignOff | true
  EnableVersioning | true
  EntityTypeName | TestList
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  FileSavePostProcessingEnabled | false
  ForceCheckout | false
  HasExternalDataSource | false
  Hidden | false
  Id | 97d19285-b8a6-4c7f-9c6c-d6b850a6561a
  ImageUrl | /\_layouts/15/images/itgen.png?rev=47
  DefaultSensitivityLabelForLibrary |
  IrmEnabled | false
  IrmExpire | false
  IrmReject | false
  IsApplicationList | false
  IsCatalog | false
  IsPrivate | false
  ItemCount | 0
  LastItemDeletedDate | 2022-11-16T19:55:37Z
  LastItemModifiedDate | 2022-11-16T19:55:39Z
  LastItemUserModifiedDate | 2022-11-16T19:55:37Z
  ListExperienceOptions | 0
  ListItemEntityTypeFullName | SP.Data.TestListItem
  MajorVersionLimit | 50
  MajorWithMinorVersionsLimit | 0
  MultipleDataList | false
  NoCrawl | false
   ParentWebUrl | /
  ParserDisabled | false
  ServerTemplateCanCreateFolders | true
  TemplateFeatureId | 00bfea71-de22-43b2-a848-c05709900100
  Title | Test
  ```

  </TabItem>
</Tabs>

## More information

- List REST API resources: [https://msdn.microsoft.com/en-us/library/office/dn531433.aspx#bk_ListEndpoint](https://msdn.microsoft.com/en-us/library/office/dn531433.aspx#bk_ListEndpoint)
