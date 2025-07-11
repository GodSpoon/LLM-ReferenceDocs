-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo list add

Creates list in the specified site

## Usage

```sh
m365 spo list add [options]
```

## Options

```md definition-list
`-t, --title <title>`
: Title of the list to add.

`--baseTemplate [baseTemplate]`
: The list definition type on which the list is based. Allowed values `Announcements`, `Contacts`, `CustomGrid`, `DataSources`,`DiscussionBoard`, `DocumentLibrary`, `Events`, `GanttTasks`, `GenericList`, `IssuesTracking`, `Links`, `NoCodeWorkflows`,`PictureLibrary`, `Survey`, `Tasks`, `WebPageLibrary`, `WorkflowHistory`, `WorkflowProcess`, `XmlForm`. Default value is `GenericList`.

`-u, --webUrl <webUrl>`
: URL of the site where the list should be added.

`--description [description]`
: The description for the list.

`--templateFeatureId [templateFeatureId]`
: The globally unique identifier (GUID) of a template feature that is associated with the list.

`--allowDeletion [allowDeletion]`
: Boolean value specifying whether the list can be deleted. Valid values are `true`, `false`.

`--allowEveryoneViewItems [allowEveryoneViewItems]`
: Boolean value specifying whether everyone can view documents in the documentlibrary or attachments to items in the list. Valid values are `true`, `false`.

`--allowMultiResponses [allowMultiResponses]`
: Boolean value specifying whether users are allowed to give multiple responses to the survey. Valid values are `true`, `false`.

`--contentTypesEnabled [contentTypesEnabled]`
: Boolean value specifying whether content types are enabled for the list. Valid values are `true`, `false`.

`--crawlNonDefaultViews [crawlNonDefaultViews]`
: Boolean value specifying whether to crawl non default views. Valid values are `true`, `false`.

`--defaultContentApprovalWorkflowId [defaultContentApprovalWorkflowId]`
: Value that specifies the default workflow identifier for content approval onthe list (GUID).

`--defaultDisplayFormUrl [defaultDisplayFormUrl]`
: Value that specifies the location of the default display form for the list.

`--defaultEditFormUrl [defaultEditFormUrl]`
: Value that specifies the URL of the edit form to use for list items in the list.

`--direction [direction]`
: Value that specifies the reading order of the list. Valid values are `NONE`, `LTR`, `RTL`.

`--disableCommenting [disableCommenting]`
: Property for enabling or disabling commenting on the list. Valid values are `true`, `false`.

`--disableGridEditing [disableGridEditing]`
: Property for assigning or retrieving grid editing on the list. Valid values are `true`, `false`.

`--draftVersionVisibility [draftVersionVisibility]`
: Value that specifies the minimum permission required to view minor versions and drafts within the list. Allowed values `Reader`, `Author`, `Approver`. Default `Reader`.

`--emailAlias [emailAlias]`
: If e-mail notification is enabled, gets or sets the e-mail address to use tonotify to the owner of an item when an assignment has changed or the item has been updated.

`--enableAssignToEmail [enableAssignToEmail]`
: Boolean value specifying whether e-mail notification is enabled for the list. Valid values are `true`, `false`.

`--enableAttachments [enableAttachments]`
: Boolean value that specifies whether attachments can be added to items in the list. Valid values are `true`, `false`.

`--enableDeployWithDependentList [enableDeployWithDependentList]`
: Boolean value that specifies whether the list can be deployed with a dependent list. Valid values are `true`, `false`.

`--enableFolderCreation [enableFolderCreation]`
: Boolean value that specifies whether folders can be created for the list. Valid values are `true`, `false`.

`--enableMinorVersions [enableMinorVersions]`
: Boolean value that specifies whether minor versions are enabled when versioning is enabled for the document library. Valid values are `true`, `false`.

`--enableModeration [enableModeration]`
: Boolean value that specifies whether Content Approval is enabled for the list. Valid values are `true`, `false`.

`--enablePeopleSelector [enablePeopleSelector]`
: Enable user selector on event list. Valid values are `true`, `false`.

`--enableResourceSelector [enableResourceSelector]`
: Enables resource selector on an event list. Valid values are `true`, `false`.

`--enableSchemaCaching [enableSchemaCaching]`
: Boolean value specifying whether schema caching is enabled for the list. Valid values are `true`, `false`.

`--enableSyndication [enableSyndication]`
: Boolean value that specifies whether RSS syndication is enabled for the list. Valid values are `true`, `false`.

`--enableThrottling [enableThrottling]`
: Indicates whether throttling for this list is enabled or not. Valid values are `true`, `false`.

`--enableVersioning [enableVersioning]`
: Boolean value that specifies whether versioning is enabled for the document library. Valid values are `true`, `false`.

`--enforceDataValidation [enforceDataValidation]`
: Value that indicates whether certain field properties are enforced when an item is added or updated. Valid values are `true`, `false`.

`--excludeFromOfflineClient [excludeFromOfflineClient]`
: Value that indicates whether the list should be downloaded to the client during offline synchronization. Valid values are `true`, `false`.

`--fetchPropertyBagForListView [fetchPropertyBagForListView]`
: Specifies whether property bag information, as part of the list schema JSON,is retrieved when the list is being rendered on the client. Valid values are `true`, `false`.

`--followable [followable]`
: Can a list be followed in an activity feed?. Valid values are `true`, `false`.

`--forceCheckout [forceCheckout]`
: Boolean value that specifies whether forced checkout is enabled for the document library. Valid values are `true`, `false`.

`--forceDefaultContentType [forceDefaultContentType]`
: Specifies whether we want to return the default Document root content type. Valid values are `true`, `false`.

`--hidden [hidden]`
: Boolean value that specifies whether the list is hidden. Valid values are `true`, `false`.

`--includedInMyFilesScope [includedInMyFilesScope]`
: Specifies whether this list is accessible to an app principal that has been granted an OAuth scope that contains the string "myfiles" by a case-insensitive comparison when the current user is a site collection administrator of the personal site that contains the list.

`--irmEnabled [irmEnabled]`
: Gets or sets a Boolean value that specifies whether Information Rights Management (IRM) is enabled for the list.

`--irmExpire [irmExpire]`
: Gets or sets a Boolean value that specifies whether Information Rights Management (IRM) expiration is enabled for the list.

`--irmReject [irmReject]`
: Gets or sets a Boolean value that specifies whether Information Rights Management (IRM) rejection is enabled for the list.

`--isApplicationList [isApplicationList]`
: Indicates whether this list should be treated as a top level navigation object or not.

`--listExperienceOptions [listExperienceOptions]`
: Gets or sets the list experience for the list. Allowed values `Auto`, `NewExperience`, `ClassicExperience`. Default `Auto`.

`--majorVersionLimit [majorVersionLimit]`
: Gets or sets the maximum number of major versions allowed for an item in a document library that uses version control with major versions only.

`--majorWithMinorVersionsLimit [majorWithMinorVersionsLimit]`
: Gets or sets the maximum number of major versions that are allowed for an item in a document library that uses version control with both major and minor versions.

`--multipleDataList [multipleDataList]`
: Gets or sets a Boolean value that specifies whether the list in a Meeting Workspace sitecontains data for multiple meeting instances within the site

`--navigateForFormsPages [navigateForFormsPages]`
: Indicates whether to navigate for forms pages or use a modal dialog.

`--needUpdateSiteClientTag [needUpdateSiteClientTag]`
: A boolean value that determines whether to editing documents in this list should increment the ClientTag for the site. The tag is used to allow clients to cache JS/CSS/resources that are retrieved from the Content DB, including custom CSR templates.

`--noCrawl [noCrawl]`
: Gets or sets a Boolean value specifying whether crawling is enabled for the list.

`--onQuickLaunch [onQuickLaunch]`
: Gets or sets a Boolean value that specifies whether the list appears on the Quick Launcharea of the home page.

`--ordered [ordered]`
: Gets or sets a Boolean value that specifies whether the option to allow users to reorderitems in the list is available on the Edit View page for the list.

`--parserDisabled [parserDisabled]`
: Gets or sets a Boolean value that specifies whether the parser should be disabled.

`--readOnlyUI [readOnlyUI]`
: A boolean value that indicates whether the UI for this list should be presented in a read-only fashion. This will not affect security nor will it actually prevent changes to the list from occurring - it only affects the way the UI is displayed.

`--readSecurity [readSecurity]`
: Gets or sets the Read security setting for the list. Valid values are 1 (All users have Read access to all items)|2 (Users have Read access only to items that they create).

`--requestAccessEnabled [requestAccessEnabled]`
: Gets or sets a Boolean value that specifies whether the option to allow users to requestaccess to the list is available.

`--restrictUserUpdates [restrictUserUpdates]`
: A boolean value that indicates whether the this list is a restricted one or not The value can't be changed if there are existing items in the list.

`--sendToLocationName [sendToLocationName]`
: Gets or sets a file name to use when copying an item in the list to another document library.

`--sendToLocationUrl [sendToLocationUrl]`
: Gets or sets a URL to use when copying an item in the list to another document library.

`--showUser [showUser]`
: Gets or sets a Boolean value that specifies whether names of users are shown in the results of the survey.

`--useFormsForDisplay [useFormsForDisplay]`
: Indicates whether forms should be considered for display context or not.

`--validationFormula [validationFormula]`
: Gets or sets a formula that is evaluated each time that a list item is added or updated.

`--validationMessage [validationMessage]`
: Gets or sets the message that is displayed when validation fails for a list item.

`--writeSecurity [writeSecurity]`
: Gets or sets the Write security setting for the list. Valid values are 1 (All users can modify all items)|2 (Users can modify only items that they create)|4 (Users cannot modify any list item).
```

<Global />

## Examples

Add a list with specific title and baseTemplate in a specific site.

```sh
m365 spo list add --title Announcements --baseTemplate Announcements --webUrl https://contoso.sharepoint.com/sites/project-x
```

Add a list with specific title and baseTemplate in a specific site with content types and versioning enabled and major version limit set.

```sh
m365 spo list add --webUrl https://contoso.sharepoint.com/sites/project-x --title Announcements --baseTemplate Announcements --contentTypesEnabled true --enableVersioning true --majorVersionLimit 50
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "AllowContentTypes": true,
    "BaseTemplate": 100,
    "BaseType": 0,
    "ContentTypesEnabled": false,
    "CrawlNonDefaultViews": false,
    "Created": "2022-11-16T19:51:42Z",
    "CurrentChangeToken": {
      "StringValue": "1;3;ea3dc19f-bc1f-4b77-afb8-14e08f4c0f6d;638042251016970000;564165920"
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
    "Id": "ea3dc19f-bc1f-4b77-afb8-14e08f4c0f6d",
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
    "LastItemDeletedDate": "2022-11-16T19:51:42Z",
    "LastItemModifiedDate": "2022-11-16T19:51:42Z",
    "LastItemUserModifiedDate": "2022-11-16T19:51:42Z",
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
  ContentTypesEnabled                      : false
  CrawlNonDefaultViews                     : false
  Created                                  : 2022-11-16T19:52:16Z
  CurrentChangeToken                       : {"StringValue":"1;3;4d66e81a-ac73-4894-9e33-7999edaa36bc;638042251364530000;564166119"}
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
  Id                                       : 4d66e81a-ac73-4894-9e33-7999edaa36bc
  ImagePath                                : {"DecodedUrl":"/_layouts/15/images/itgen.png?rev=47"}
  ImageUrl                                 : /_layouts/15/images/itgen.png?rev=47
  IrmEnabled                               : false
  IrmExpire                                : false
  IrmReject                                : false
  IsApplicationList                        : false
  IsCatalog                                : false
  IsPrivate                                : false
  ItemCount                                : 0
  LastItemDeletedDate                      : 2022-11-16T19:52:16Z
  LastItemModifiedDate                     : 2022-11-16T19:52:16Z
  LastItemUserModifiedDate                 : 2022-11-16T19:52:16Z
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
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  AllowContentTypes,BaseTemplate,BaseType,ContentTypesEnabled,CrawlNonDefaultViews,Created,CurrentChangeToken,DefaultContentApprovalWorkflowId,DefaultItemOpenUseListSetting,Description,Direction,DisableCommenting,DisableGridEditing,DocumentTemplateUrl,DraftVersionVisibility,EnableAttachments,EnableFolderCreation,EnableMinorVersions,EnableModeration,EnableRequestSignOff,EnableVersioning,EntityTypeName,EXAMPLE_SECRET_VALUE_PLACEHOLDER,FileSavePostProcessingEnabled,ForceCheckout,HasExternalDataSource,Hidden,Id,ImagePath,ImageUrl,DefaultSensitivityLabelForLibrary,IrmEnabled,IrmExpire,IrmReject,IsApplicationList,IsCatalog,IsPrivate,ItemCount,LastItemDeletedDate,LastItemModifiedDate,LastItemUserModifiedDate,ListExperienceOptions,ListItemEntityTypeFullName,MajorVersionLimit,MajorWithMinorVersionsLimit,MultipleDataList,NoCrawl,ParentWebPath,ParentWebUrl,ParserDisabled,ServerTemplateCanCreateFolders,TemplateFeatureId,Title
  1,100,0,,,2022-11-16T19:52:41Z,"{""StringValue"":""1;3;3b6bd39e-1e62-4ddf-ac8e-020bf5353891;638042251616230000;564166296""}",00000000-0000-0000-0000-000000000000,,,none,,,,0,1,,,,1,1,TestList,,,,,,3b6bd39e-1e62-4ddf-ac8e-020bf5353891,"{""DecodedUrl"":""/_layouts/15/images/itgen.png?rev=47""}",/_layouts/15/images/itgen.png?rev=47,,,,,,,,0,2022-11-16T19:52:41Z,2022-11-16T19:52:42Z,2022-11-16T19:52:41Z,0,SP.Data.TestListItem,50,0,,,"{""DecodedUrl"":""/""}",/,,1,00bfea71-de22-43b2-a848-c05709900100,Test
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo list add --contentTypesEnabled "true" --enableVersioning "true" --webUrl "https://contoso.sharepoint.com" --title "Test" --baseTemplate "GenericList" --majorVersionLimit "50"

  Date: 2/20/2023

  ## Test (ea3dc19f-bc1f-4b77-afb8-14e08f4c0f6d)

  Property | Value
  ---------|-------
  AllowContentTypes | true
  BaseTemplate | 100
  BaseType | 0
  ContentTypesEnabled | false
  CrawlNonDefaultViews | false
  Created | 2022-11-16T19:51:42Z
  DefaultContentApprovalWorkflowId | 00000000-0000-0000-0000-000000000000
  DefaultItemOpenUseListSetting | false
  Description | 
  Direction | none
  DisableCommenting | false
  DisableGridEditing | false
  DocumentTemplateUrl | null
  DraftVersionVisibility | 0
  EnableAttachments | true
  EnableFolderCreation | false
  EnableMinorVersions | false
  EnableModeration | false
  EnableRequestSignOff | true
  EnableVersioning | true
  EntityTypeName | AnnouncementsList
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  FileSavePostProcessingEnabled | false
  ForceCheckout | false
  HasExternalDataSource | false
  Hidden | false
  Id | ea3dc19f-bc1f-4b77-afb8-14e08f4c0f6d
  ImageUrl | /\/_layouts/15/images/itgen.png?rev=47
  DefaultSensitivityLabelForLibrary |
  IrmEnabled | false
  IrmExpire | false
  IrmReject | false
  IsApplicationList | false
  IsCatalog | false
  IsPrivate | false
  ItemCount | 0
  LastItemDeletedDate | 2022-11-16T19:51:42Z
  LastItemModifiedDate | 2022-11-16T19:51:42Z
  LastItemUserModifiedDate | 2022-11-16T19:51:42Z
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

- SPList Class Members information: [https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER](https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER)
- ListTemplateType enum information: [https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER](https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER)
- DraftVersionVisibilityType enum information: [https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER](https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER)
- ListExperience enum information: [https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER](https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER)
