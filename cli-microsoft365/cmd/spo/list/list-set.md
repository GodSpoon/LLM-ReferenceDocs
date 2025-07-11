-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo list set

Updates the settings of the specified list

## Usage

```sh
m365 spo list set [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site.

`--id [id]`
: ID of the list. Specify either `id`, `title`, or `url` but not multiple.

`--title [title]`
: Title of the list. Specify either `id`, `title`, or `url` but not multiple.

`--url [url]`
: Relative URL of the list. Specify either `id`, `title`, or `url` but not multiple.

`--newTitle [newTitle]`
: New title for the list.

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
: Value that specifies the default workflow identifier for content approval on the list (GUID).

`--defaultDisplayFormUrl [defaultDisplayFormUrl]`
: Value that specifies the location of the default display form for the list.

`--defaultEditFormUrl [defaultEditFormUrl]`
: Value that specifies the URL of the edit form to use for list items in the list.

`--description [description]`
: The description for the list.

`--direction [direction]`
: Value that specifies the reading order of the list. Valid values are `NONE`, `LTR`, `RTL`.

`--disableCommenting [disableCommenting]`
: Property for enabling or disabling commenting on the list. Valid values are `true`, `false`.

`--disableGridEditing [disableGridEditing]`
: Property for assigning or retrieving grid editing on the list. Valid values are `true`, `false`.

`--draftVersionVisibility [draftVersionVisibility]`
: Value that specifies the minimum permission required to view minor versions and drafts within the list. Allowed values `Reader`, `Author`, `Approver`.

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
: Gets or sets the list experience for the list. Allowed values `Auto`, `NewExperience`, `ClassicExperience`.

`--majorVersionLimit [majorVersionLimit]`
: Gets or sets the maximum number of major versions allowed for an item in a document library that uses version control with major versions only.

`--majorWithMinorVersionsLimit [majorWithMinorVersionsLimit]`
: Gets or sets the maximum number of major versions that are allowed for an item in a document library that uses version control with both major and minor versions.

`--multipleDataList [multipleDataList]`
: Gets or sets a Boolean value that specifies whether the list in a Meeting Workspace sitecontains data for multiple meeting instances within the site.

`--navigateForFormsPages [navigateForFormsPages]`
: Indicates whether to navigate for forms pages or use a modal dialog.

`--needUpdateSiteClientTag [needUpdateSiteClientTag]`
: A boolean value that determines whether to editing documents in this list should increment the ClientTag for the site. The tag is used to allow clients to cache JS/CSS/resources that are retrieved from the Content DB, including custom CSR templates.

`--noCrawl [noCrawl]`
: Gets or sets a Boolean value specifying whether crawling is enabled for the list.

`--onQuickLaunch [onQuickLaunch]`
: Gets or sets a Boolean value that specifies whether the list appears on the Quick Launch area of the home page.

`--ordered [ordered]`
: Gets or sets a Boolean value that specifies whether the option to allow users to reorder items in the list is available on the Edit View page for the list.

`--parserDisabled [parserDisabled]`
: Gets or sets a Boolean value that specifies whether the parser should be disabled.

`--readOnlyUI [readOnlyUI]`
: A boolean value that indicates whether the UI for this list should be presented in a read-only fashion. This will not affect security nor will it actually prevent changes to the list from occurring - it only affects the way the UI is displayed.

`--readSecurity [readSecurity]`
: Gets or sets the Read security setting for the list. Valid values are 1 (All users have Read access to all items)|2 (Users have Read access only to items that they create).

`--requestAccessEnabled [requestAccessEnabled]`
: Gets or sets a Boolean value that specifies whether the option to allow users to request access to the list is available.

`--restrictUserUpdates [restrictUserUpdates]`
: A boolean value that indicates whether the this list is a restricted one or not The value can't be changed if there are existing items in the list.

`--sendToLocationName [sendToLocationName]`
: Gets or sets a file name to use when copying an item in the list to another document library.

`--sendToLocationUrl [sendToLocationUrl]`
: Gets or sets a URL to use when copying an item in the list to another document library.

`--showUser [showUser]`
: Gets or sets a Boolean value that specifies whether names of users are shown in the results of the survey.

`--templateFeatureId [templateFeatureId]`
: The globally unique identifier (GUID) of a template feature that is associated with the list.

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

Update the _contentTypesEnabled_ property of the list with id located in a specific site.

```sh
m365 spo list set --webUrl https://contoso.sharepoint.com/sites/project-x --id 3EA5A977-315E-4E25-8B0F-E4F949BF6B8F --contentTypesEnabled true
```

Enable versioning and set the number of major versions to keep on the list with id located in a specific site.

```sh
m365 spo list set --webUrl https://contoso.sharepoint.com/sites/project-x --id 3EA5A977-315E-4E25-8B0F-E4F949BF6B8F --enableVersioning true --majorVersionLimit 50
```

Enable content types and versioning in the list with id located in a specific site.

```sh
m365 spo list set --webUrl https://contoso.sharepoint.com/sites/project-x --id 3EA5A977-315E-4E25-8B0F-E4F949BF6B8F --contentTypesEnabled true --enableVersioning true --majorVersionLimit 50 --majorWithMinorVersionsLimit 100
```

Update the title of a list retrieved by it's original title.

```sh
m365 spo list set --webUrl https://contoso.sharepoint.com/sites/project-x --title Documents --newTitle 'Different Title'
```

## Response

The command won't return a response on success.

## More information

- SPList Class Members information: [https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER](https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER)
- ListTemplateType enum information: [https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER](https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER)
- DraftVersionVisibilityType enum information: [https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER](https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER)
- ListExperience enum information: [https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER](https://msdn.microsoft.com/en-us/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER)
