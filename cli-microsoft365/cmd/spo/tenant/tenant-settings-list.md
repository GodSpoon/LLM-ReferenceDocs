-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo tenant settings list

Lists the global tenant settings

## Usage

```sh
m365 spo tenant settings list [options]
```

## Options

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Lists the settings of the tenant

```sh
m365 spo tenant settings list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "AIBuilderDefaultPowerAppsEnvironment": "",
    "AIBuilderEnabled": false,
    "AIBuilderEnabledInContentCenter": 0,
    "AIBuilderSiteListFileName": null,
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": 0,
    "AllowCommentsTextOnEmailEnabled": true,
    "AllowDownloadingNonWebViewableFiles": true,
    "AllowedDomainListForSyncClient": [],
    "AllowEditing": true,
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": true,
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
    "AllowLimitedAccessOnUnmanagedDevices": false,
    "AllowOverrideForBlockUserInfoVisibility": false,
    "AllowSelectSecurityGroupsInSPSitesList": null,
    "AllowSelectSGsInODBListInTenant": null,
    "AnyoneLinkTrackUsers": false,
    "AppBypassInformationBarriers": false,
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": true,
    "ArchiveRedirectUrl": null,
    "AuthContextResilienceMode": 0,
    "BccExternalSharingInvitations": false,
    "BccExternalSharingInvitationsList": null,
    "BlockAccessOnUnmanagedDevices": false,
    "BlockDownloadFileTypeIds": [],
    "BlockDownloadFileTypePolicy": false,
    "BlockDownloadLinksFileType": 1,
    "BlockDownloadOfAllFilesForGuests": false,
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
    "BlockDownloadOfViewableFilesForGuests": false,
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
    "BlockMacSync": false,
    "BlockSendLabelMismatchEmail": false,
    "BlockUserInfoVisibility": "",
    "BlockUserInfoVisibilityInOneDrive": 0,
    "BlockUserInfoVisibilityInSharePoint": 0,
    "CommentsOnFilesDisabled": false,
    "CommentsOnListItemsDisabled": false,
    "CommentsOnSitePagesDisabled": false,
    "CompatibilityRange": "15,15",
    "ConditionalAccessPolicy": "AllowFullAccess",
    "ConditionalAccessPolicyErrorHelpLink": "",
    "ContainerDefaultLinkToExistingAccess": false,
    "ContainerDefaultShareLinkRole": 0,
    "ContainerDefaultShareLinkScope": -1,
    "ContainerLoopDefaultShareLinkRole": 0,
    "ContainerLoopDefaultShareLinkScope": -1,
    "ContainerSharingCapability": 0,
    "ContentTypeSyncSiteTemplatesList": [],
    "CoreBlockGuestsAsSiteAdmin": 0,
    "CoreDefaultLinkToExistingAccess": false,
    "CoreDefaultShareLinkRole": 0,
    "CoreDefaultShareLinkScope": -1,
    "CoreLoopDefaultSharingLinkRole": 0,
    "CoreLoopDefaultSharingLinkScope": -1,
    "CoreLoopSharingCapability": 0,
    "CoreRequestFilesLinkEnabled": false,
    "CoreRequestFilesLinkExpirationInDays": -1,
    "CoreSharingCapability": 0,
    "CustomizedExternalSharingServiceUrl": "",
    "DefaultContentCenterSite": null,
    "DefaultLinkPermission": "Edit",
    "DefaultODBMode": "Explicit",
    "DefaultSharingLinkType": "Internal",
    "DenySelectSecurityGroupsInSPSitesList": null,
    "DisableAddToOneDrive": false,
    "DisableBackToClassic": false,
    "DisableCustomAppAuthentication": false,
    "DisabledModernListTemplateIds": [],
    "DisableDocumentLibraryDefaultLabeling": false,
    "DisabledWebPartIds": null,
    "DisableListSync": false,
    "DisableOutlookPSTVersionTrimming": false,
    "DisablePersonalListCreation": false,
    "DisableReportProblemDialog": false,
    "DisableSpacesActivation": false,
    "DisableVivaConnectionsAnalytics": false,
    "DisallowInfectedFileDownload": false,
    "DisplayNamesOfFileViewers": true,
    "DisplayNamesOfFileViewersInSpo": true,
    "DisplayStartASiteOption": true,
    "DocumentUnderstandingEnabled": true,
    "DocumentUnderstandingSiteListFileName": "",
    "EmailAttestationEnabled": false,
    "EmailAttestationReAuthDays": 30,
    "EmailAttestationRequired": false,
    "EnableAIPIntegration": true,
    "EnableAutoExpirationVersionTrim": false,
    "EnableAutoNewsDigest": true,
    "EnableAzureADB2BIntegration": false,
    "EnabledFlightAllowAADB2BSkipCheckingOTP": true,
    "EnableGuestSignInAcceleration": false,
    "EnableMinimumVersionRequirement": true,
    "EnableMipSiteLabel": false,
    "EnablePromotedFileHandlers": true,
    "EnableRestrictedAccessControl": false,
    "EnableSensitivityLabelForPDF": false,
    "ESignatureEnabled": true,
    "ESignatureSiteListFileName": "",
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": "",
    "ExcludedBlockDownloadGroupIds": [],
    "ExcludedFileExtensionsForSyncClient": [
      ""
    ],
    "ExpireVersionsAfterDays": 0,
    "ExternalServicesEnabled": true,
    "ExternalUserExpirationRequired": false,
    "ExternalUserExpireInDays": 60,
    "FileAnonymousLinkType": "Edit",
    "FilePickerExternalImageSearchEnabled": true,
    "FileVersionPolicyXml": "",
    "FolderAnonymousLinkType": "Edit",
    "GuestSharingGroupAllowListInTenant": "",
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": null,
    "HasAdminCompletedCUConfiguration": false,
    "HasIntelligentContentServicesCapability": false,
    "HasTopicExperiencesCapability": false,
    "HideSyncButtonOnDocLib": false,
    "HideSyncButtonOnODB": false,
    "IBImplicitGroupBased": false,
    "ImageTaggingOption": 1,
    "IncludeAtAGlanceInShareEmails": true,
    "InformationBarriersSuspension": true,
    "IPAddressAllowList": "",
    "IPAddressEnforcement": false,
    "IPAddressWACTokenLifetime": 15,
    "IsAppBarTemporarilyDisabled": false,
    "IsCollabMeetingNotesFluidEnabled": true,
    "IsEnableAppAuthPopUpEnabled": false,
    "IsFluidEnabled": true,
    "IsHubSitesMultiGeoFlightEnabled": true,
    "IsLoopEnabled": true,
    "IsMnAFlightEnabled": false,
    "IsMultiGeo": false,
    "IsMultipleHomeSitesFlightEnabled": false,
    "IsMultipleVivaConnectionsFlightEnabled": true,
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": true,
    "IsVivaHomeFlightEnabled": true,
    "IsVivaHomeGAFlightEnabled": true,
    "IsWBFluidEnabled": true,
    "LabelMismatchEmailHelpLink": null,
    "LegacyAuthProtocolsEnabled": true,
    "LegacyBrowserAuthProtocolsEnabled": true,
    "LimitedAccessFileType": "WebPreviewableFiles",
    "MachineLearningCaptureEnabled": false,
    "MajorVersionLimit": 500,
    "MarkNewFilesSensitiveByDefault": 0,
    "MassDeleteNotificationDisabled": false,
    "MediaTranscription": 0,
    "MediaTranscriptionAutomaticFeatures": 0,
    "MobileFriendlyUrlEnabledInTenant": true,
    "NoAccessRedirectUrl": null,
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": true,
    "NotificationsInSharePointEnabled": true,
    "NotifyOwnersWhenInvitationsAccepted": true,
    "NotifyOwnersWhenItemsReshared": true,
    "OCRAdminSiteListFileName": "",
    "OCRComplianceSiteListFileName": "",
    "OCRModeForAdminSites": 0,
    "OCRModeForComplianceODBs": 0,
    "OCRModeForComplianceSites": 0,
    "ODBAccessRequests": "Unspecified",
    "ODBMembersCanShare": "Unspecified",
    "ODBSharingCapability": 0,
    "OfficeClientADALDisabled": false,
    "OneDriveBlockGuestsAsSiteAdmin": 0,
    "OneDriveDefaultLinkToExistingAccess": false,
    "OneDriveDefaultShareLinkRole": 0,
    "OneDriveDefaultShareLinkScope": -1,
    "OneDriveForGuestsEnabled": false,
    "OneDriveLoopDefaultSharingLinkRole": 0,
    "OneDriveLoopDefaultSharingLinkScope": -1,
    "OneDriveLoopSharingCapability": 0,
    "OneDriveRequestFilesLinkEnabled": false,
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": -1,
    "OneDriveStorageQuota": 1048576,
    "OptOutOfGrooveBlock": false,
    "OptOutOfGrooveSoftBlock": false,
    "OrgNewsSiteUrl": null,
    "OrphanedPersonalSitesRetentionPeriod": 30,
    "OwnerAnonymousNotification": true,
    "PermissiveBrowserFileHandlingOverride": false,
    "PrebuiltEnabled": true,
    "PrebuiltSiteListFileName": "",
    "PreventExternalUsersFromResharing": false,
    "ProvisionSharedWithEveryoneFolder": false,
    "PublicCdnAllowedFileTypes": "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF",
    "PublicCdnEnabled": false,
    "PublicCdnOrigins": [],
    "RecycleBinRetentionPeriod": 93,
    "ReduceTempTokenLifetimeEnabled": false,
    "ReduceTempTokenLifetimeValue": 15,
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
    "RequireAnonymousLinksExpireInDays": -1,
    "ResourceQuota": 0,
    "ResourceQuotaAllocated": 0,
    "RestrictedOneDriveLicense": false,
    "RestrictedSharePointLicense": false,
    "RootSiteUrl": "https://contoso.sharepoint.com",
    "SearchResolveExactEmailOrUPN": false,
    "SharingAllowedDomainList": "contoso.onmicrosoft.com",
    "SharingBlockedDomainList": null,
    "SharingCapability": "Disabled",
    "SharingDomainRestrictionMode": "None",
    "ShowAllUsersClaim": false,
    "ShowEveryoneClaim": false,
    "ShowEveryoneExceptExternalUsersClaim": true,
    "ShowNGSCDialogForSyncOnODB": true,
    "ShowOpenInDesktopOptionForSyncedFiles": false,
    "ShowPeoplePickerGroupSuggestionsForIB": false,
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
    "SignInAccelerationDomain": "",
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": true,
    "SocialBarOnSitePagesDisabled": false,
    "SpecialCharactersStateInFileFolderNames": "Allowed",
    "StartASiteFormUrl": null,
    "StopNew2010Workflows": false,
    "StopNew2013Workflows": false,
    "StorageQuota": 1304576,
    "StorageQuotaAllocated": 0,
    "StreamLaunchConfig": 0,
    "StreamLaunchConfigLastUpdated": "/Date(1,0,1,0,0,0,0)/",
    "StreamLaunchConfigUpdateCount": 0,
    "SyncAadB2BManagementPolicy": false,
    "SyncPrivacyProfileProperties": true,
    "TaxonomyTaggingEnabled": false,
    "TaxonomyTaggingSiteListFileName": "",
    "TlsTokenBindingPolicyValue": 0,
    "UseFindPeopleInPeoplePicker": false,
    "UsePersistentCookiesForExplorerView": false,
    "UserVoiceForFeedbackEnabled": true,
    "ViewersCanCommentOnMediaDisabled": false,
    "ViewInFileExplorerEnabled": false,
    "WhoCanShareAllowListInTenant": "",
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": null,
    "Workflow2010Disabled": false,
    "Workflows2013State": 0,
    "HideDefaultThemes": false
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  AIBuilderDefaultPowerAppsEnvironment                 :
  AIBuilderEnabled                                     : false
  AIBuilderEnabledInContentCenter                      : 0
  AIBuilderSiteListFileName                            : null
  EXAMPLE_SECRET_VALUE_PLACEHOLDER : 0
  AllowCommentsTextOnEmailEnabled                      : true
  AllowDownloadingNonWebViewableFiles                  : true
  AllowEditing                                         : true
  EXAMPLE_SECRET_VALUE_PLACEHOLDER   : true
  EXAMPLE_SECRET_VALUE_PLACEHOLDER        : false
  AllowLimitedAccessOnUnmanagedDevices                 : false
  AllowOverrideForBlockUserInfoVisibility              : false
  AllowSelectSGsInODBListInTenant                      : null
  AllowSelectSecurityGroupsInSPSitesList               : null
  AllowedDomainListForSyncClient                       : []
  AnyoneLinkTrackUsers                                 : false
  AppBypassInformationBarriers                         : false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER        : true
  ArchiveRedirectUrl                                   : null
  AuthContextResilienceMode                            : 0
  BccExternalSharingInvitations                        : false
  BccExternalSharingInvitationsList                    : null
  BlockAccessOnUnmanagedDevices                        : false
  BlockDownloadFileTypeIds                             : []
  BlockDownloadFileTypePolicy                          : false
  BlockDownloadLinksFileType                           : 1
  BlockDownloadOfAllFilesForGuests                     : false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER            : false
  BlockDownloadOfViewableFilesForGuests                : false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER       : false
  BlockMacSync                                         : false
  BlockSendLabelMismatchEmail                          : false
  BlockUserInfoVisibility                              :
  BlockUserInfoVisibilityInOneDrive                    : 0
  BlockUserInfoVisibilityInSharePoint                  : 0
  CommentsOnFilesDisabled                              : false
  CommentsOnListItemsDisabled                          : false
  CommentsOnSitePagesDisabled                          : false
  CompatibilityRange                                   : 15,15
  ConditionalAccessPolicy                              : AllowFullAccess
  ConditionalAccessPolicyErrorHelpLink                 :
  ContainerDefaultLinkToExistingAccess                 : false
  ContainerDefaultShareLinkRole                        : 0
  ContainerDefaultShareLinkScope                       : -1
  ContainerLoopDefaultShareLinkRole                    : 0
  ContainerLoopDefaultShareLinkScope                   : -1
  ContainerSharingCapability                           : 0
  ContentTypeSyncSiteTemplatesList                     : []
  CoreBlockGuestsAsSiteAdmin                           : 0
  CoreDefaultLinkToExistingAccess                      : false
  CoreDefaultShareLinkRole                             : 0
  CoreDefaultShareLinkScope                            : -1
  CoreLoopDefaultSharingLinkRole                       : 0
  CoreLoopDefaultSharingLinkScope                      : -1
  CoreLoopSharingCapability                            : 0
  CoreRequestFilesLinkEnabled                          : false
  CoreRequestFilesLinkExpirationInDays                 : -1
  CoreSharingCapability                                : 0
  CustomizedExternalSharingServiceUrl                  :
  DefaultContentCenterSite                             : null
  DefaultLinkPermission                                : Edit
  DefaultODBMode                                       : Explicit
  DefaultSharingLinkType                               : Internal
  DenySelectSecurityGroupsInSPSitesList                : null
  DisableAddToOneDrive                                 : false
  DisableBackToClassic                                 : false
  DisableCustomAppAuthentication                       : false
  DisableDocumentLibraryDefaultLabeling                : false
  DisableListSync                                      : false
  DisableOutlookPSTVersionTrimming                     : false
  DisablePersonalListCreation                          : false
  DisableReportProblemDialog                           : false
  DisableSpacesActivation                              : false
  DisableVivaConnectionsAnalytics                      : false
  DisabledModernListTemplateIds                        : []
  DisabledWebPartIds                                   : null
  DisallowInfectedFileDownload                         : false
  DisplayNamesOfFileViewers                            : true
  DisplayNamesOfFileViewersInSpo                       : true
  DisplayStartASiteOption                              : true
  DocumentUnderstandingEnabled                         : true
  DocumentUnderstandingSiteListFileName                :
  ESignatureEnabled                                    : true
  ESignatureSiteListFileName                           :
  EXAMPLE_SECRET_VALUE_PLACEHOLDER             :
  EmailAttestationEnabled                              : false
  EmailAttestationReAuthDays                           : 30
  EmailAttestationRequired                             : false
  EnableAIPIntegration                                 : true
  EnableAutoExpirationVersionTrim                      : false
  EnableAutoNewsDigest                                 : true
  EnableAzureADB2BIntegration                          : false
  EnableGuestSignInAcceleration                        : false
  EnableMinimumVersionRequirement                      : true
  EnableMipSiteLabel                                   : false
  EnablePromotedFileHandlers                           : true
  EnableRestrictedAccessControl                        : false
  EnableSensitivityLabelForPDF                         : false
  EnabledFlightAllowAADB2BSkipCheckingOTP              : true
  ExcludedBlockDownloadGroupIds                        : []
  ExcludedFileExtensionsForSyncClient                  : [""]
  ExpireVersionsAfterDays                              : 0
  ExternalServicesEnabled                              : true
  ExternalUserExpirationRequired                       : false
  ExternalUserExpireInDays                             : 60
  FileAnonymousLinkType                                : Edit
  FilePickerExternalImageSearchEnabled                 : true
  FileVersionPolicyXml                                 :
  FolderAnonymousLinkType                              : Edit
  GuestSharingGroupAllowListInTenant                   :
  EXAMPLE_SECRET_VALUE_PLACEHOLDER: null
  HasAdminCompletedCUConfiguration                     : false
  HasIntelligentContentServicesCapability              : false
  HasTopicExperiencesCapability                        : false
  HideDefaultThemes                                    : false
  HideSyncButtonOnDocLib                               : false
  HideSyncButtonOnODB                                  : false
  IBImplicitGroupBased                                 : false
  IPAddressAllowList                                   :
  IPAddressEnforcement                                 : false
  IPAddressWACTokenLifetime                            : 15
  ImageTaggingOption                                   : 1
  IncludeAtAGlanceInShareEmails                        : true
  InformationBarriersSuspension                        : true
  IsAppBarTemporarilyDisabled                          : false
  IsCollabMeetingNotesFluidEnabled                     : true
  IsEnableAppAuthPopUpEnabled                          : false
  IsFluidEnabled                                       : true
  IsHubSitesMultiGeoFlightEnabled                      : true
  IsLoopEnabled                                        : true
  IsMnAFlightEnabled                                   : false
  IsMultiGeo                                           : false
  IsMultipleHomeSitesFlightEnabled                     : false
  IsMultipleVivaConnectionsFlightEnabled               : true
  EXAMPLE_SECRET_VALUE_PLACEHOLDER             : false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER        : true
  IsVivaHomeFlightEnabled                              : true
  IsVivaHomeGAFlightEnabled                            : true
  IsWBFluidEnabled                                     : true
  LabelMismatchEmailHelpLink                           : null
  LegacyAuthProtocolsEnabled                           : true
  LegacyBrowserAuthProtocolsEnabled                    : true
  LimitedAccessFileType                                : WebPreviewableFiles
  MachineLearningCaptureEnabled                        : false
  MajorVersionLimit                                    : 500
  MarkNewFilesSensitiveByDefault                       : 0
  MassDeleteNotificationDisabled                       : false
  MediaTranscription                                   : 0
  MediaTranscriptionAutomaticFeatures                  : 0
  MobileFriendlyUrlEnabledInTenant                     : true
  NoAccessRedirectUrl                                  : null
  EXAMPLE_SECRET_VALUE_PLACEHOLDER            : true
  NotificationsInSharePointEnabled                     : true
  NotifyOwnersWhenInvitationsAccepted                  : true
  NotifyOwnersWhenItemsReshared                        : true
  OCRAdminSiteListFileName                             :
  OCRComplianceSiteListFileName                        :
  OCRModeForAdminSites                                 : 0
  OCRModeForComplianceODBs                             : 0
  OCRModeForComplianceSites                            : 0
  ODBAccessRequests                                    : Unspecified
  ODBMembersCanShare                                   : Unspecified
  ODBSharingCapability                                 : 0
  OfficeClientADALDisabled                             : false
  OneDriveBlockGuestsAsSiteAdmin                       : 0
  OneDriveDefaultLinkToExistingAccess                  : false
  OneDriveDefaultShareLinkRole                         : 0
  OneDriveDefaultShareLinkScope                        : -1
  OneDriveForGuestsEnabled                             : false
  OneDriveLoopDefaultSharingLinkRole                   : 0
  OneDriveLoopDefaultSharingLinkScope                  : -1
  OneDriveLoopSharingCapability                        : 0
  OneDriveRequestFilesLinkEnabled                      : false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER             : -1
  OneDriveStorageQuota                                 : 1048576
  OptOutOfGrooveBlock                                  : false
  OptOutOfGrooveSoftBlock                              : false
  OrgNewsSiteUrl                                       : null
  OrphanedPersonalSitesRetentionPeriod                 : 30
  OwnerAnonymousNotification                           : true
  PermissiveBrowserFileHandlingOverride                : false
  PrebuiltEnabled                                      : true
  PrebuiltSiteListFileName                             :
  PreventExternalUsersFromResharing                    : false
  ProvisionSharedWithEveryoneFolder                    : false
  PublicCdnAllowedFileTypes                            : CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF
  PublicCdnEnabled                                     : false
  PublicCdnOrigins                                     : []
  RecycleBinRetentionPeriod                            : 93
  ReduceTempTokenLifetimeEnabled                       : false
  ReduceTempTokenLifetimeValue                         : 15
  EXAMPLE_SECRET_VALUE_PLACEHOLDER           : false
  RequireAnonymousLinksExpireInDays                    : -1
  ResourceQuota                                        : 0
  ResourceQuotaAllocated                               : 0
  RestrictedOneDriveLicense                            : false
  RestrictedSharePointLicense                          : false
  RootSiteUrl                                          : https://contoso.sharepoint.com
  SearchResolveExactEmailOrUPN                         : false
  SharingAllowedDomainList                             : contoso.onmicrosoft.com
  SharingBlockedDomainList                             : null
  SharingCapability                                    : Disabled
  SharingDomainRestrictionMode                         : None
  ShowAllUsersClaim                                    : false
  ShowEveryoneClaim                                    : false
  ShowEveryoneExceptExternalUsersClaim                 : true
  ShowNGSCDialogForSyncOnODB                           : true
  ShowOpenInDesktopOptionForSyncedFiles                : false
  ShowPeoplePickerGroupSuggestionsForIB                : false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER             : false
  SignInAccelerationDomain                             :
  EXAMPLE_SECRET_VALUE_PLACEHOLDER         : true
  SocialBarOnSitePagesDisabled                         : false
  SpecialCharactersStateInFileFolderNames              : Allowed
  StartASiteFormUrl                                    : null
  StopNew2010Workflows                                 : false
  StopNew2013Workflows                                 : false
  StorageQuota                                         : 1304576
  StorageQuotaAllocated                                : 0
  StreamLaunchConfig                                   : 0
  StreamLaunchConfigLastUpdated                        : /Date(1,0,1,0,0,0,0)/
  StreamLaunchConfigUpdateCount                        : 0
  SyncAadB2BManagementPolicy                           : false
  SyncPrivacyProfileProperties                         : true
  TaxonomyTaggingEnabled                               : false
  TaxonomyTaggingSiteListFileName                      :
  TlsTokenBindingPolicyValue                           : 0
  UseFindPeopleInPeoplePicker                          : false
  UsePersistentCookiesForExplorerView                  : false
  UserVoiceForFeedbackEnabled                          : true
  ViewInFileExplorerEnabled                            : false
  ViewersCanCommentOnMediaDisabled                     : false
  WhoCanShareAllowListInTenant                         :
  EXAMPLE_SECRET_VALUE_PLACEHOLDER      : null
  Workflow2010Disabled                                 : false
  Workflows2013State                                   : 0
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  AIBuilderDefaultPowerAppsEnvironment,AIBuilderEnabled,AIBuilderEnabledInContentCenter,EXAMPLE_SECRET_VALUE_PLACEHOLDER,AllowCommentsTextOnEmailEnabled,AllowDownloadingNonWebViewableFiles,AllowEditing,EXAMPLE_SECRET_VALUE_PLACEHOLDER,EXAMPLE_SECRET_VALUE_PLACEHOLDER,AllowLimitedAccessOnUnmanagedDevices,AllowOverrideForBlockUserInfoVisibility,AnyoneLinkTrackUsers,AppBypassInformationBarriers,EXAMPLE_SECRET_VALUE_PLACEHOLDER,AuthContextResilienceMode,BccExternalSharingInvitations,BlockAccessOnUnmanagedDevices,BlockDownloadFileTypePolicy,BlockDownloadLinksFileType,BlockDownloadOfAllFilesForGuests,EXAMPLE_SECRET_VALUE_PLACEHOLDER,BlockDownloadOfViewableFilesForGuests,EXAMPLE_SECRET_VALUE_PLACEHOLDER,BlockMacSync,BlockSendLabelMismatchEmail,BlockUserInfoVisibility,BlockUserInfoVisibilityInOneDrive,BlockUserInfoVisibilityInSharePoint,CommentsOnFilesDisabled,CommentsOnListItemsDisabled,CommentsOnSitePagesDisabled,CompatibilityRange,ConditionalAccessPolicy,ConditionalAccessPolicyErrorHelpLink,ContainerDefaultLinkToExistingAccess,ContainerDefaultShareLinkRole,ContainerDefaultShareLinkScope,ContainerLoopDefaultShareLinkRole,ContainerLoopDefaultShareLinkScope,ContainerSharingCapability,CoreBlockGuestsAsSiteAdmin,CoreDefaultLinkToExistingAccess,CoreDefaultShareLinkRole,CoreDefaultShareLinkScope,CoreLoopDefaultSharingLinkRole,CoreLoopDefaultSharingLinkScope,CoreLoopSharingCapability,CoreRequestFilesLinkEnabled,CoreRequestFilesLinkExpirationInDays,CoreSharingCapability,CustomizedExternalSharingServiceUrl,DefaultLinkPermission,DefaultODBMode,DefaultSharingLinkType,DisableAddToOneDrive,DisableBackToClassic,DisableCustomAppAuthentication,DisableDocumentLibraryDefaultLabeling,DisableListSync,DisableOutlookPSTVersionTrimming,DisablePersonalListCreation,DisableReportProblemDialog,DisableSpacesActivation,DisableVivaConnectionsAnalytics,DisallowInfectedFileDownload,DisplayNamesOfFileViewers,DisplayNamesOfFileViewersInSpo,DisplayStartASiteOption,DocumentUnderstandingEnabled,DocumentUnderstandingSiteListFileName,EmailAttestationEnabled,EmailAttestationReAuthDays,EmailAttestationRequired,EnableAIPIntegration,EnableAutoExpirationVersionTrim,EnableAutoNewsDigest,EnableAzureADB2BIntegration,EnabledFlightAllowAADB2BSkipCheckingOTP,EnableGuestSignInAcceleration,EnableMinimumVersionRequirement,EnableMipSiteLabel,EnablePromotedFileHandlers,EnableRestrictedAccessControl,EnableSensitivityLabelForPDF,ESignatureEnabled,ESignatureSiteListFileName,EXAMPLE_SECRET_VALUE_PLACEHOLDER,ExpireVersionsAfterDays,ExternalServicesEnabled,ExternalUserExpirationRequired,ExternalUserExpireInDays,FileAnonymousLinkType,FilePickerExternalImageSearchEnabled,FileVersionPolicyXml,FolderAnonymousLinkType,GuestSharingGroupAllowListInTenant,HasAdminCompletedCUConfiguration,HasIntelligentContentServicesCapability,HasTopicExperiencesCapability,HideSyncButtonOnDocLib,HideSyncButtonOnODB,IBImplicitGroupBased,ImageTaggingOption,IncludeAtAGlanceInShareEmails,InformationBarriersSuspension,IPAddressAllowList,IPAddressEnforcement,IPAddressWACTokenLifetime,IsAppBarTemporarilyDisabled,IsCollabMeetingNotesFluidEnabled,IsEnableAppAuthPopUpEnabled,IsFluidEnabled,IsHubSitesMultiGeoFlightEnabled,IsLoopEnabled,IsMnAFlightEnabled,IsMultiGeo,IsMultipleHomeSitesFlightEnabled,IsMultipleVivaConnectionsFlightEnabled,EXAMPLE_SECRET_VALUE_PLACEHOLDER,EXAMPLE_SECRET_VALUE_PLACEHOLDER,IsVivaHomeFlightEnabled,IsVivaHomeGAFlightEnabled,IsWBFluidEnabled,LegacyAuthProtocolsEnabled,LegacyBrowserAuthProtocolsEnabled,LimitedAccessFileType,MachineLearningCaptureEnabled,MajorVersionLimit,MarkNewFilesSensitiveByDefault,MassDeleteNotificationDisabled,MediaTranscription,MediaTranscriptionAutomaticFeatures,MobileFriendlyUrlEnabledInTenant,EXAMPLE_SECRET_VALUE_PLACEHOLDER,NotificationsInSharePointEnabled,NotifyOwnersWhenInvitationsAccepted,NotifyOwnersWhenItemsReshared,OCRAdminSiteListFileName,OCRComplianceSiteListFileName,OCRModeForAdminSites,OCRModeForComplianceODBs,OCRModeForComplianceSites,ODBAccessRequests,ODBMembersCanShare,ODBSharingCapability,OfficeClientADALDisabled,OneDriveBlockGuestsAsSiteAdmin,OneDriveDefaultLinkToExistingAccess,OneDriveDefaultShareLinkRole,OneDriveDefaultShareLinkScope,OneDriveForGuestsEnabled,OneDriveLoopDefaultSharingLinkRole,OneDriveLoopDefaultSharingLinkScope,OneDriveLoopSharingCapability,OneDriveRequestFilesLinkEnabled,EXAMPLE_SECRET_VALUE_PLACEHOLDER,OneDriveStorageQuota,OptOutOfGrooveBlock,OptOutOfGrooveSoftBlock,OrphanedPersonalSitesRetentionPeriod,OwnerAnonymousNotification,PermissiveBrowserFileHandlingOverride,PrebuiltEnabled,PrebuiltSiteListFileName,PreventExternalUsersFromResharing,ProvisionSharedWithEveryoneFolder,PublicCdnAllowedFileTypes,PublicCdnEnabled,RecycleBinRetentionPeriod,ReduceTempTokenLifetimeEnabled,ReduceTempTokenLifetimeValue,EXAMPLE_SECRET_VALUE_PLACEHOLDER,RequireAnonymousLinksExpireInDays,ResourceQuota,ResourceQuotaAllocated,RestrictedOneDriveLicense,RestrictedSharePointLicense,RootSiteUrl,SearchResolveExactEmailOrUPN,SharingAllowedDomainList,SharingCapability,SharingDomainRestrictionMode,ShowAllUsersClaim,ShowEveryoneClaim,ShowEveryoneExceptExternalUsersClaim,ShowNGSCDialogForSyncOnODB,ShowOpenInDesktopOptionForSyncedFiles,ShowPeoplePickerGroupSuggestionsForIB,EXAMPLE_SECRET_VALUE_PLACEHOLDER,SignInAccelerationDomain,EXAMPLE_SECRET_VALUE_PLACEHOLDER,SocialBarOnSitePagesDisabled,SpecialCharactersStateInFileFolderNames,StopNew2010Workflows,StopNew2013Workflows,StorageQuota,StorageQuotaAllocated,StreamLaunchConfig,StreamLaunchConfigLastUpdated,StreamLaunchConfigUpdateCount,SyncAadB2BManagementPolicy,SyncPrivacyProfileProperties,TaxonomyTaggingEnabled,TaxonomyTaggingSiteListFileName,TlsTokenBindingPolicyValue,UseFindPeopleInPeoplePicker,UsePersistentCookiesForExplorerView,UserVoiceForFeedbackEnabled,ViewersCanCommentOnMediaDisabled,ViewInFileExplorerEnabled,WhoCanShareAllowListInTenant,Workflow2010Disabled,Workflows2013State,HideDefaultThemes
  ,,0,0,1,1,1,1,,,,,,1,0,,,,1,,,,,,,,0,0,,,,"15,15",AllowFullAccess,,,0,-1,0,-1,0,0,,0,-1,0,-1,0,,-1,0,,Edit,Explicit,Internal,,,,,,,,,,,,1,1,1,1,,,30,,1,,1,,1,,1,,1,,,1,,,0,1,,60,Edit,1,,Edit,,,,,,,,1,1,1,,,15,,1,,1,1,1,,,,1,,1,1,1,1,1,1,WebPreviewableFiles,,500,0,,0,0,1,1,1,1,1,,,0,0,0,Unspecified,Unspecified,0,,0,,0,-1,,0,-1,0,,-1,1048576,,,30,1,,1,,,,"CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF",,93,,15,,-1,0,0,,,https://contoso.sharepoint.com,,contoso.onmicrosoft.com,Disabled,None,,,1,1,,,,,1,,Allowed,,,1304576,0,0,"/Date(1,0,1,0,0,0,0)/",0,,1,,,0,,,1,,,,,0,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo tenant settings list

  Date: 2023-06-22

  Property | Value
  ---------|-------
  AIBuilderDefaultPowerAppsEnvironment |
  AIBuilderEnabled | false
  AIBuilderEnabledInContentCenter | 0
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | 0
  AllowCommentsTextOnEmailEnabled | true
  AllowDownloadingNonWebViewableFiles | true
  AllowEditing | true
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | true
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  AllowLimitedAccessOnUnmanagedDevices | false
  AllowOverrideForBlockUserInfoVisibility | false
  AnyoneLinkTrackUsers | false
  AppBypassInformationBarriers | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | true
  AuthContextResilienceMode | 0
  BccExternalSharingInvitations | false
  BlockAccessOnUnmanagedDevices | false
  BlockDownloadFileTypePolicy | false
  BlockDownloadLinksFileType | 1
  BlockDownloadOfAllFilesForGuests | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  BlockDownloadOfViewableFilesForGuests | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  BlockMacSync | false
  BlockSendLabelMismatchEmail | false
  BlockUserInfoVisibility |
  BlockUserInfoVisibilityInOneDrive | 0
  BlockUserInfoVisibilityInSharePoint | 0
  CommentsOnFilesDisabled | false
  CommentsOnListItemsDisabled | false
  CommentsOnSitePagesDisabled | false
  CompatibilityRange | 15,15
  ConditionalAccessPolicy | AllowFullAccess
  ConditionalAccessPolicyErrorHelpLink |
  ContainerDefaultLinkToExistingAccess | false
  ContainerDefaultShareLinkRole | 0
  ContainerDefaultShareLinkScope | -1
  ContainerLoopDefaultShareLinkRole | 0
  ContainerLoopDefaultShareLinkScope | -1
  ContainerSharingCapability | 0
  CoreBlockGuestsAsSiteAdmin | 0
  CoreDefaultLinkToExistingAccess | false
  CoreDefaultShareLinkRole | 0
  CoreDefaultShareLinkScope | -1
  CoreLoopDefaultSharingLinkRole | 0
  CoreLoopDefaultSharingLinkScope | -1
  CoreLoopSharingCapability | 0
  CoreRequestFilesLinkEnabled | false
  CoreRequestFilesLinkExpirationInDays | -1
  CoreSharingCapability | 0
  CustomizedExternalSharingServiceUrl |
  DefaultLinkPermission | Edit
  DefaultODBMode | Explicit
  DefaultSharingLinkType | Internal
  DisableAddToOneDrive | false
  DisableBackToClassic | false
  DisableCustomAppAuthentication | false
  DisableDocumentLibraryDefaultLabeling | false
  DisableListSync | false
  DisableOutlookPSTVersionTrimming | false
  DisablePersonalListCreation | false
  DisableReportProblemDialog | false
  DisableSpacesActivation | false
  DisableVivaConnectionsAnalytics | false
  DisallowInfectedFileDownload | false
  DisplayNamesOfFileViewers | true
  DisplayNamesOfFileViewersInSpo | true
  DisplayStartASiteOption | true
  DocumentUnderstandingEnabled | true
  DocumentUnderstandingSiteListFileName |
  EmailAttestationEnabled | false
  EmailAttestationReAuthDays | 30
  EmailAttestationRequired | false
  EnableAIPIntegration | true
  EnableAutoExpirationVersionTrim | false
  EnableAutoNewsDigest | true
  EnableAzureADB2BIntegration | false
  EnabledFlightAllowAADB2BSkipCheckingOTP | true
  EnableGuestSignInAcceleration | false
  EnableMinimumVersionRequirement | true
  EnableMipSiteLabel | false
  EnablePromotedFileHandlers | true
  EnableRestrictedAccessControl | false
  EnableSensitivityLabelForPDF | false
  ESignatureEnabled | true
  ESignatureSiteListFileName |
  EXAMPLE_SECRET_VALUE_PLACEHOLDER |
  ExpireVersionsAfterDays | 0
  ExternalServicesEnabled | true
  ExternalUserExpirationRequired | false
  ExternalUserExpireInDays | 60
  FileAnonymousLinkType | Edit
  FilePickerExternalImageSearchEnabled | true
  FileVersionPolicyXml |
  FolderAnonymousLinkType | Edit
  GuestSharingGroupAllowListInTenant |
  HasAdminCompletedCUConfiguration | false
  HasIntelligentContentServicesCapability | false
  HasTopicExperiencesCapability | false
  HideSyncButtonOnDocLib | false
  HideSyncButtonOnODB | false
  IBImplicitGroupBased | false
  ImageTaggingOption | 1
  IncludeAtAGlanceInShareEmails | true
  InformationBarriersSuspension | true
  IPAddressAllowList |
  IPAddressEnforcement | false
  IPAddressWACTokenLifetime | 15
  IsAppBarTemporarilyDisabled | false
  IsCollabMeetingNotesFluidEnabled | true
  IsEnableAppAuthPopUpEnabled | false
  IsFluidEnabled | true
  IsHubSitesMultiGeoFlightEnabled | true
  IsLoopEnabled | true
  IsMnAFlightEnabled | false
  IsMultiGeo | false
  IsMultipleHomeSitesFlightEnabled | false
  IsMultipleVivaConnectionsFlightEnabled | true
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | true
  IsVivaHomeFlightEnabled | true
  IsVivaHomeGAFlightEnabled | true
  IsWBFluidEnabled | true
  LegacyAuthProtocolsEnabled | true
  LegacyBrowserAuthProtocolsEnabled | true
  LimitedAccessFileType | WebPreviewableFiles
  MachineLearningCaptureEnabled | false
  MajorVersionLimit | 500
  MarkNewFilesSensitiveByDefault | 0
  MassDeleteNotificationDisabled | false
  MediaTranscription | 0
  MediaTranscriptionAutomaticFeatures | 0
  MobileFriendlyUrlEnabledInTenant | true
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | true
  NotificationsInSharePointEnabled | true
  NotifyOwnersWhenInvitationsAccepted | true
  NotifyOwnersWhenItemsReshared | true
  OCRAdminSiteListFileName |
  OCRComplianceSiteListFileName |
  OCRModeForAdminSites | 0
  OCRModeForComplianceODBs | 0
  OCRModeForComplianceSites | 0
  ODBAccessRequests | Unspecified
  ODBMembersCanShare | Unspecified
  ODBSharingCapability | 0
  OfficeClientADALDisabled | false
  OneDriveBlockGuestsAsSiteAdmin | 0
  OneDriveDefaultLinkToExistingAccess | false
  OneDriveDefaultShareLinkRole | 0
  OneDriveDefaultShareLinkScope | -1
  OneDriveForGuestsEnabled | false
  OneDriveLoopDefaultSharingLinkRole | 0
  OneDriveLoopDefaultSharingLinkScope | -1
  OneDriveLoopSharingCapability | 0
  OneDriveRequestFilesLinkEnabled | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | -1
  OneDriveStorageQuota | 1048576
  OptOutOfGrooveBlock | false
  OptOutOfGrooveSoftBlock | false
  OrphanedPersonalSitesRetentionPeriod | 30
  OwnerAnonymousNotification | true
  PermissiveBrowserFileHandlingOverride | false
  PrebuiltEnabled | true
  PrebuiltSiteListFileName |
  PreventExternalUsersFromResharing | false
  ProvisionSharedWithEveryoneFolder | false
  PublicCdnAllowedFileTypes | CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF
  PublicCdnEnabled | false
  RecycleBinRetentionPeriod | 93
  ReduceTempTokenLifetimeEnabled | false
  ReduceTempTokenLifetimeValue | 15
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  RequireAnonymousLinksExpireInDays | -1
  ResourceQuota | 0
  ResourceQuotaAllocated | 0
  RestrictedOneDriveLicense | false
  RestrictedSharePointLicense | false
  RootSiteUrl | https://contoso.sharepoint.com
  SearchResolveExactEmailOrUPN | false
  SharingAllowedDomainList | contoso.onmicrosoft.com
  SharingCapability | Disabled
  SharingDomainRestrictionMode | None
  ShowAllUsersClaim | false
  ShowEveryoneClaim | false
  ShowEveryoneExceptExternalUsersClaim | true
  ShowNGSCDialogForSyncOnODB | true
  ShowOpenInDesktopOptionForSyncedFiles | false
  ShowPeoplePickerGroupSuggestionsForIB | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  SignInAccelerationDomain |
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | true
  SocialBarOnSitePagesDisabled | false
  SpecialCharactersStateInFileFolderNames | Allowed
  StopNew2010Workflows | false
  StopNew2013Workflows | false
  StorageQuota | 1304576
  StorageQuotaAllocated | 0
  StreamLaunchConfig | 0
  StreamLaunchConfigLastUpdated | /Date(1,0,1,0,0,0,0)/
  StreamLaunchConfigUpdateCount | 0
  SyncAadB2BManagementPolicy | false
  SyncPrivacyProfileProperties | true
  TaxonomyTaggingEnabled | false
  TaxonomyTaggingSiteListFileName |
  TlsTokenBindingPolicyValue | 0
  UseFindPeopleInPeoplePicker | false
  UsePersistentCookiesForExplorerView | false
  UserVoiceForFeedbackEnabled | true
  ViewersCanCommentOnMediaDisabled | false
  ViewInFileExplorerEnabled | false
  WhoCanShareAllowListInTenant |
  Workflow2010Disabled | false
  Workflows2013State | 0
  HideDefaultThemes | false
  ```

  </TabItem>
</Tabs>
