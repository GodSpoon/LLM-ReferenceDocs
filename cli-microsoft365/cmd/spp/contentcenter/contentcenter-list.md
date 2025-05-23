-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spp contentcenter list

Gets information about the SharePoint Premium content centers

## Usage

```sh
m365 spp contentcenter list [options]
```

## Options

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Gets information about the SharePoint Premium content centers

```sh
m365 spp contentcenter list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "_ObjectType_": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "_ObjectIdentity_": "855b40a1-6024-9000-87b1-7d412d935b3c|908bed80-a04a-4433-b4a0-883d9847d110:dc109ffd-4298-487e-9cbc-6b9b1a2cd3e2\
SiteProperties\
https%3a%2f%2fcontoso.sharepoint.com%2fsites%2fContentCentre",
      "AllowDownloadingNonWebViewableFiles": false,
      "AllowEditing": false,
      "AllowSelfServiceUpgrade": true,
      "AnonymousLinkExpirationInDays": 0,
      "ApplyToExistingDocumentLibraries": false,
      "ApplyToNewDocumentLibraries": false,
      "ArchiveStatus": "NotArchived",
      "AuthContextStrength": null,
      "AuthenticationContextLimitedAccess": false,
      "AuthenticationContextName": null,
      "AverageResourceUsage": 0,
      "BlockDownloadLinksFileType": 0,
      "BlockDownloadMicrosoft365GroupIds": null,
      "BlockDownloadPolicy": false,
      "BlockDownloadPolicyFileTypeIds": null,
      "BlockGuestsAsSiteAdmin": 0,
      "BonusDiskQuota": 0,
      "ClearRestrictedAccessControl": false,
      "CommentsOnSitePagesDisabled": false,
      "CompatibilityLevel": 15,
      "ConditionalAccessPolicy": 0,
      "CurrentResourceUsage": 0,
      "DefaultLinkPermission": 0,
      "DefaultLinkToExistingAccess": false,
      "DefaultLinkToExistingAccessReset": false,
      "DefaultShareLinkRole": 0,
      "DefaultShareLinkScope": 0,
      "DefaultSharingLinkType": 0,
      "DenyAddAndCustomizePages": 2,
      "Description": null,
      "DisableAppViews": 0,
      "DisableCompanyWideSharingLinks": 0,
      "DisableFlows": 0,
      "EnableAutoExpirationVersionTrim": false,
      "ExcludeBlockDownloadPolicySiteOwners": false,
      "ExcludeBlockDownloadSharePointGroups": [],
      "ExcludedBlockDownloadGroupIds": [],
      "ExpireVersionsAfterDays": 0,
      "ExternalUserExpirationInDays": 0,
      "GroupId": "/Guid(00000000-0000-0000-0000-000000000000)/",
      "GroupOwnerLoginName": null,
      "HasHolds": false,
      "HubSiteId": "/Guid(00000000-0000-0000-0000-000000000000)/",
      "IBMode": null,
      "IBSegments": null,
      "IBSegmentsToAdd": null,
      "IBSegmentsToRemove": null,
      "InheritVersionPolicyFromTenant": false,
      "IsGroupOwnerSiteAdmin": false,
      "IsHubSite": false,
      "IsTeamsChannelConnected": false,
      "IsTeamsConnected": false,
      "LastContentModifiedDate": "/Date(2024,6,22,2,59,8,0)/",
      "Lcid": 1045,
      "LimitedAccessFileType": 0,
      "ListsShowHeaderAndNavigation": false,
      "LockIssue": null,
      "LockReason": 0,
      "LockState": "Unlock",
      "LoopDefaultSharingLinkRole": 0,
      "LoopDefaultSharingLinkScope": 0,
      "MajorVersionLimit": 0,
      "MajorWithMinorVersionsLimit": 0,
      "MediaTranscription": 0,
      "OverrideBlockUserInfoVisibility": 0,
      "OverrideSharingCapability": false,
      "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
      "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
      "Owner": "user@contoso.onmicrosoft.com",
      "OwnerEmail": null,
      "OwnerLoginName": null,
      "OwnerName": null,
      "PWAEnabled": 1,
      "ReadOnlyAccessPolicy": false,
      "ReadOnlyForBlockDownloadPolicy": false,
      "ReadOnlyForUnmanagedDevices": false,
      "RelatedGroupId": "/Guid(00000000-0000-0000-0000-000000000000)/",
      "RequestFilesLinkEnabled": false,
      "RequestFilesLinkExpirationInDays": 0,
      "RestrictContentOrgWideSearch": false,
      "RestrictedAccessControl": false,
      "RestrictedAccessControlGroups": null,
      "RestrictedAccessControlGroupsToAdd": null,
      "RestrictedAccessControlGroupsToRemove": null,
      "RestrictedToRegion": 3,
      "SandboxedCodeActivationCapability": 0,
      "SensitivityLabel": "/Guid(00000000-0000-0000-0000-000000000000)/",
      "SensitivityLabel2": null,
      "SetOwnerWithoutUpdatingSecondaryAdmin": false,
      "SharingAllowedDomainList": null,
      "SharingBlockedDomainList": null,
      "SharingCapability": 0,
      "SharingDomainRestrictionMode": 0,
      "SharingLockDownCanBeCleared": false,
      "SharingLockDownEnabled": false,
      "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
      "SiteDefinedSharingCapability": 0,
      "SiteId": "/Guid(5fd4f5b5-38e6-423f-a1c6-96d2f78eeba7)/",
      "SocialBarOnSitePagesDisabled": false,
      "Status": "Active",
      "StorageMaximumLevel": 26214400,
      "StorageQuotaType": null,
      "StorageUsage": 1,
      "StorageWarningLevel": 25574400,
      "TeamsChannelType": 0,
      "Template": "CONTENTCTR#0",
      "TimeZoneId": 13,
      "Title": "ContentCentre",
      "TitleTranslations": null,
      "Url": "https://contoso.sharepoint.com/sites/ContentCentre",
      "UserCodeMaximumLevel": 0,
      "UserCodeWarningLevel": 0,
      "WebsCount": 0
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Title          Url
  -------------  --------------------------------------------------
  ContentCentre  https://contoso.sharepoint.com/sites/ContentCentre
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  _ObjectType_,_ObjectIdentity_,AllowDownloadingNonWebViewableFiles,AllowEditing,AllowSelfServiceUpgrade,AnonymousLinkExpirationInDays,ApplyToExistingDocumentLibraries,ApplyToNewDocumentLibraries,ArchiveStatus,AuthContextStrength,AuthenticationContextLimitedAccess,AuthenticationContextName,AverageResourceUsage,BlockDownloadLinksFileType,BlockDownloadMicrosoft365GroupIds,BlockDownloadPolicy,BlockDownloadPolicyFileTypeIds,BlockGuestsAsSiteAdmin,BonusDiskQuota,ClearRestrictedAccessControl,CommentsOnSitePagesDisabled,CompatibilityLevel,ConditionalAccessPolicy,CurrentResourceUsage,DefaultLinkPermission,DefaultLinkToExistingAccess,DefaultLinkToExistingAccessReset,DefaultShareLinkRole,DefaultShareLinkScope,DefaultSharingLinkType,DenyAddAndCustomizePages,Description,DisableAppViews,DisableCompanyWideSharingLinks,DisableFlows,EnableAutoExpirationVersionTrim,ExcludeBlockDownloadPolicySiteOwners,ExpireVersionsAfterDays,ExternalUserExpirationInDays,GroupId,GroupOwnerLoginName,HasHolds,HubSiteId,IBMode,IBSegments,IBSegmentsToAdd,IBSegmentsToRemove,InheritVersionPolicyFromTenant,IsGroupOwnerSiteAdmin,IsHubSite,IsTeamsChannelConnected,IsTeamsConnected,LastContentModifiedDate,Lcid,LimitedAccessFileType,ListsShowHeaderAndNavigation,LockIssue,LockReason,LockState,LoopDefaultSharingLinkRole,LoopDefaultSharingLinkScope,MajorVersionLimit,MajorWithMinorVersionsLimit,MediaTranscription,OverrideBlockUserInfoVisibility,OverrideSharingCapability,EXAMPLE_SECRET_VALUE_PLACEHOLDER,EXAMPLE_SECRET_VALUE_PLACEHOLDER,Owner,OwnerEmail,OwnerLoginName,OwnerName,PWAEnabled,ReadOnlyAccessPolicy,ReadOnlyForBlockDownloadPolicy,ReadOnlyForUnmanagedDevices,RelatedGroupId,RequestFilesLinkEnabled,RequestFilesLinkExpirationInDays,RestrictContentOrgWideSearch,RestrictedAccessControl,RestrictedAccessControlGroups,RestrictedAccessControlGroupsToAdd,RestrictedAccessControlGroupsToRemove,RestrictedToRegion,SandboxedCodeActivationCapability,SensitivityLabel,SensitivityLabel2,SetOwnerWithoutUpdatingSecondaryAdmin,SharingAllowedDomainList,SharingBlockedDomainList,SharingCapability,SharingDomainRestrictionMode,SharingLockDownCanBeCleared,SharingLockDownEnabled,EXAMPLE_SECRET_VALUE_PLACEHOLDER,SiteDefinedSharingCapability,SiteId,SocialBarOnSitePagesDisabled,Status,StorageMaximumLevel,StorageQuotaType,StorageUsage,StorageWarningLevel,TeamsChannelType,Template,TimeZoneId,Title,TitleTranslations,Url,UserCodeMaximumLevel,UserCodeWarningLevel,WebsCount
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,"035c40a1-703b-9000-87b1-77f1c297d218|908bed80-a04a-4433-b4a0-883d9847d110:dc109ffd-4298-487e-9cbc-6b9b1a2cd3e2
  SiteProperties
  https%3a%2f%2fcontoso.sharepoint.com%2fsites%2fContentCentre",,,1,0,,,NotArchived,,,,0,0,,,,0,0,,,15,0,0,0,,,0,0,0,2,,0,0,0,,,0,0,/Guid(00000000-0000-0000-0000-000000000000)/,,,/Guid(00000000-0000-0000-0000-000000000000)/,,,,,,,,,,"/Date(2024,6,22,2,59,8,0)/",1045,0,,,0,Unlock,0,0,0,0,0,0,,,,user@contoso.onmicrosoft.com,,,,1,,,,/Guid(00000000-0000-0000-0000-000000000000)/,,0,,,,,,3,0,/Guid(00000000-0000-0000-0000-000000000000)/,,,,,0,0,,,,0,/Guid(5fd4f5b5-38e6-423f-a1c6-96d2f78eeba7)/,,Active,26214400,,1,25574400,0,CONTENTCTR#0,13,ContentCentre,,https://contoso.sharepoint.com/sites/ContentCentre,0,0,0
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spp contentcenter list 

  Date: 27/07/2024

  ## ContentCentre (https://contoso.sharepoint.com/sites/ContentCentre)

  Property | Value
  ---------|-------
  \_ObjectType\_ | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  \_ObjectIdentity\_ | 0a5c40a1-2068-9000-8001-70e27f49586f\|908bed80-a04a-4433-b4a0-883d9847d110:dc109ffd-4298-487e-9cbc-6b9b1a2cd3e2<br>SiteProperties<br>https%3a%2f%2fcontoso.sharepoint.com%2fsites%2fContentCentre
  AllowDownloadingNonWebViewableFiles | false
  AllowEditing | false
  AllowSelfServiceUpgrade | true
  AnonymousLinkExpirationInDays | 0
  ApplyToExistingDocumentLibraries | false
  ApplyToNewDocumentLibraries | false
  ArchiveStatus | NotArchived
  AuthenticationContextLimitedAccess | false
  AverageResourceUsage | 0
  BlockDownloadLinksFileType | 0
  BlockDownloadPolicy | false
  BlockGuestsAsSiteAdmin | 0
  BonusDiskQuota | 0
  ClearRestrictedAccessControl | false
  CommentsOnSitePagesDisabled | false
  CompatibilityLevel | 15
  ConditionalAccessPolicy | 0
  CurrentResourceUsage | 0
  DefaultLinkPermission | 0
  DefaultLinkToExistingAccess | false
  DefaultLinkToExistingAccessReset | false
  DefaultShareLinkRole | 0
  DefaultShareLinkScope | 0
  DefaultSharingLinkType | 0
  DenyAddAndCustomizePages | 2
  DisableAppViews | 0
  DisableCompanyWideSharingLinks | 0
  DisableFlows | 0
  EnableAutoExpirationVersionTrim | false
  ExcludeBlockDownloadPolicySiteOwners | false
  ExpireVersionsAfterDays | 0
  ExternalUserExpirationInDays | 0
  GroupId | /Guid(00000000-0000-0000-0000-000000000000)/
  HasHolds | false
  HubSiteId | /Guid(00000000-0000-0000-0000-000000000000)/
  InheritVersionPolicyFromTenant | false
  IsGroupOwnerSiteAdmin | false
  IsHubSite | false
  IsTeamsChannelConnected | false
  IsTeamsConnected | false
  LastContentModifiedDate | /Date(2024,6,22,2,59,8,0)/
  Lcid | 1045
  LimitedAccessFileType | 0
  ListsShowHeaderAndNavigation | false
  LockReason | 0
  LockState | Unlock
  LoopDefaultSharingLinkRole | 0
  LoopDefaultSharingLinkScope | 0
  MajorVersionLimit | 0
  MajorWithMinorVersionsLimit | 0
  MediaTranscription | 0
  OverrideBlockUserInfoVisibility | 0
  OverrideSharingCapability | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  Owner | user@contoso.onmicrosoft.com
  PWAEnabled | 1
  ReadOnlyAccessPolicy | false
  ReadOnlyForBlockDownloadPolicy | false
  ReadOnlyForUnmanagedDevices | false
  RelatedGroupId | /Guid(00000000-0000-0000-0000-000000000000)/
  RequestFilesLinkEnabled | false
  RequestFilesLinkExpirationInDays | 0
  RestrictContentOrgWideSearch | false
  RestrictedAccessControl | false
  RestrictedToRegion | 3
  SandboxedCodeActivationCapability | 0
  SensitivityLabel | /Guid(00000000-0000-0000-0000-000000000000)/
  SetOwnerWithoutUpdatingSecondaryAdmin | false
  SharingCapability | 0
  SharingDomainRestrictionMode | 0
  SharingLockDownCanBeCleared | false
  SharingLockDownEnabled | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  SiteDefinedSharingCapability | 0
  SiteId | /Guid(5fd4f5b5-38e6-423f-a1c6-96d2f78eeba7)/
  SocialBarOnSitePagesDisabled | false
  Status | Active
  StorageMaximumLevel | 26214400
  StorageUsage | 1
  StorageWarningLevel | 25574400
  TeamsChannelType | 0
  Template | CONTENTCTR#0
  TimeZoneId | 13
  Title | ContentCentre
  Url | https://contoso.sharepoint.com/sites/ContentCentre
  UserCodeMaximumLevel | 0
  UserCodeWarningLevel | 0
  WebsCount | 0
  ```

  </TabItem>
</Tabs>
