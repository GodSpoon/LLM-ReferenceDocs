-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# onedrive list

Retrieves a list of OneDrive sites

## Usage

```sh
m365 onedrive list [options]
```

## Options

<Global />

## Examples

Retrieves a list of OneDrive sites from the tenant.

```sh
m365 onedrive list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "_ObjectType_": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "_ObjectIdentity_": "5555b5a0-d016-6000-aee2-595e1fa42910|908bed80-a04a-4433-b4a0-883d9847d110:1e852b49-bf4b-4ba5-bcd4-a8c4706c8ed4\
SiteProperties\
https%3a%2f%2fcontoso-my.sharepoint.com%2fpersonal%2fjohn_contoso_onmicrosoft_com",
      "AllowDownloadingNonWebViewableFiles": false,
      "AllowEditing": false,
      "AllowSelfServiceUpgrade": true,
      "AnonymousLinkExpirationInDays": 0,
      "AuthContextStrength": null,
      "AuthenticationContextLimitedAccess": false,
      "AuthenticationContextName": null,
      "AverageResourceUsage": 0,
      "BlockDownloadLinksFileType": 0,
      "BlockDownloadMicrosoft365GroupIds": null,
      "BlockDownloadPolicy": false,
      "BlockGuestsAsSiteAdmin": 0,
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
      "ExcludeBlockDownloadPolicySiteOwners": false,
      "ExcludedBlockDownloadGroupIds": [],
      "ExternalUserExpirationInDays": 0,
      "GroupId": "/Guid(00000000-0000-0000-0000-000000000000)/",
      "GroupOwnerLoginName": null,
      "HasHolds": false,
      "HubSiteId": "/Guid(00000000-0000-0000-0000-000000000000)/",
      "IBMode": null,
      "IBSegments": [],
      "IBSegmentsToAdd": null,
      "IBSegmentsToRemove": null,
      "IsGroupOwnerSiteAdmin": false,
      "IsHubSite": false,
      "IsTeamsChannelConnected": false,
      "IsTeamsConnected": false,
      "LastContentModifiedDate": "/Date(2023,4,22,10,47,36,867)/",
      "Lcid": 1033,
      "LimitedAccessFileType": 0,
      "ListsShowHeaderAndNavigation": false,
      "LockIssue": null,
      "LockState": "Unlock",
      "LoopDefaultSharingLinkRole": 0,
      "LoopDefaultSharingLinkScope": 0,
      "LoopOverrideSharingCapability": false,
      "LoopSharingCapability": 0,
      "MediaTranscription": 0,
      "OverrideBlockUserInfoVisibility": 0,
      "OverrideSharingCapability": false,
      "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
      "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
      "Owner": "john@contoso.onmicrosoft.com",
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
      "SiteDefinedSharingCapability": 2,
      "SocialBarOnSitePagesDisabled": false,
      "Status": "Active",
      "StorageMaximumLevel": 1048576,
      "StorageQuotaType": null,
      "StorageUsage": 99,
      "StorageWarningLevel": 943718,
      "TeamsChannelType": 0,
      "Template": "SPSPERS#10",
      "TimeZoneId": 13,
      "Title": "John",
      "TitleTranslations": null,
      "Url": "https://contoso-my.sharepoint.com/personal/john_contoso_onmicrosoft_com",
      "UserCodeMaximumLevel": 300,
      "UserCodeWarningLevel": 200,
      "WebsCount": 0
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Title  Url
  -----  -----------------------------------------------------------------------
  John   https://contoso-my.sharepoint.com/personal/john_contoso_onmicrosoft_com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  _ObjectType_,_ObjectIdentity_,AllowDownloadingNonWebViewableFiles,AllowEditing,AllowSelfServiceUpgrade,AnonymousLinkExpirationInDays,AuthenticationContextLimitedAccess,AverageResourceUsage,BlockDownloadLinksFileType,BlockDownloadPolicy,BlockGuestsAsSiteAdmin,ClearRestrictedAccessControl,CommentsOnSitePagesDisabled,CompatibilityLevel,ConditionalAccessPolicy,CurrentResourceUsage,DefaultLinkPermission,DefaultLinkToExistingAccess,DefaultLinkToExistingAccessReset,DefaultShareLinkRole,DefaultShareLinkScope,DefaultSharingLinkType,DenyAddAndCustomizePages,DisableAppViews,DisableCompanyWideSharingLinks,DisableFlows,ExcludeBlockDownloadPolicySiteOwners,ExternalUserExpirationInDays,GroupId,HasHolds,HubSiteId,IsGroupOwnerSiteAdmin,IsHubSite,IsTeamsChannelConnected,IsTeamsConnected,LastContentModifiedDate,Lcid,LimitedAccessFileType,ListsShowHeaderAndNavigation,LockState,LoopDefaultSharingLinkRole,LoopDefaultSharingLinkScope,LoopOverrideSharingCapability,LoopSharingCapability,MediaTranscription,OverrideBlockUserInfoVisibility,OverrideSharingCapability,EXAMPLE_SECRET_VALUE_PLACEHOLDER,EXAMPLE_SECRET_VALUE_PLACEHOLDER,Owner,PWAEnabled,ReadOnlyAccessPolicy,ReadOnlyForBlockDownloadPolicy,ReadOnlyForUnmanagedDevices,RelatedGroupId,RequestFilesLinkEnabled,RequestFilesLinkExpirationInDays,RestrictedAccessControl,RestrictedToRegion,SandboxedCodeActivationCapability,SensitivityLabel,SetOwnerWithoutUpdatingSecondaryAdmin,SharingCapability,SharingDomainRestrictionMode,SharingLockDownCanBeCleared,SharingLockDownEnabled,EXAMPLE_SECRET_VALUE_PLACEHOLDER,SiteDefinedSharingCapability,SocialBarOnSitePagesDisabled,Status,StorageMaximumLevel,StorageUsage,StorageWarningLevel,TeamsChannelType,Template,TimeZoneId,Title,Url,UserCodeMaximumLevel,UserCodeWarningLevel,WebsCount
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,"7755b5a0-60dd-6000-884e-d3cee2eebe74|908bed80-a04a-4433-b4a0-883d9847d110:1e852b49-bf4b-4ba5-bcd4-a8c4706c8ed4
  SiteProperties
  https%3a%2f%2fcontoso-my.sharepoint.com%2fpersonal%2fjohn_contoso_onmicrosoft_com",,,1,0,,0,0,,0,,,15,0,0,0,,,0,0,0,2,0,0,0,,0,/Guid(00000000-0000-0000-0000-000000000000)/,,/Guid(00000000-0000-0000-0000-000000000000)/,,,,,"/Date(2023,4,22,10,47,36,867)/",1033,0,,Unlock,0,0,,0,0,0,,,,john@contoso.onmicrosoft.com,1,,,,/Guid(00000000-0000-0000-0000-000000000000)/,,0,,3,0,/Guid(00000000-0000-0000-0000-000000000000)/,,0,0,,,,2,,Active,1048576,99,943718,0,SPSPERS#10,13,John,https://contoso-my.sharepoint.com/personal/john_contoso_onmicrosoft_com,300,200,0
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # onedrive list

  Date: 2023-05-22

  ## John (https://contoso-my.sharepoint.com/personal/john_contoso_onmicrosoft_com)

  Property | Value
  ---------|-------
  \_ObjectType\_ | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  \_ObjectIdentity\_ | 8b55b5a0-3004-6000-aee2-525984e67e44\|908bed80-a04a-4433-b4a0-883d9847d110:1e852b49-bf4b-4ba5-bcd4-a8c4706c8ed4<br>SiteProperties<br>https%3a%2f%2fcontoso-my.sharepoint.com%2fpersonal%2fjohn\_contoso\_onmicrosoft\_com
  AllowDownloadingNonWebViewableFiles | false
  AllowEditing | false
  AllowSelfServiceUpgrade | true
  AnonymousLinkExpirationInDays | 0
  AuthenticationContextLimitedAccess | false
  AverageResourceUsage | 0
  BlockDownloadLinksFileType | 0
  BlockDownloadPolicy | false
  BlockGuestsAsSiteAdmin | 0
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
  ExcludeBlockDownloadPolicySiteOwners | false
  ExternalUserExpirationInDays | 0
  GroupId | /Guid(00000000-0000-0000-0000-000000000000)/
  HasHolds | false
  HubSiteId | /Guid(00000000-0000-0000-0000-000000000000)/
  IsGroupOwnerSiteAdmin | false
  IsHubSite | false
  IsTeamsChannelConnected | false
  IsTeamsConnected | false
  LastContentModifiedDate | /Date(2023,4,22,10,47,36,867)/
  Lcid | 1033
  LimitedAccessFileType | 0
  ListsShowHeaderAndNavigation | false
  LockState | Unlock
  LoopDefaultSharingLinkRole | 0
  LoopDefaultSharingLinkScope | 0
  LoopOverrideSharingCapability | false
  LoopSharingCapability | 0
  MediaTranscription | 0
  OverrideBlockUserInfoVisibility | 0
  OverrideSharingCapability | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  Owner | john@contoso.onmicrosoft.com
  PWAEnabled | 1
  ReadOnlyAccessPolicy | false
  ReadOnlyForBlockDownloadPolicy | false
  ReadOnlyForUnmanagedDevices | false
  RelatedGroupId | /Guid(00000000-0000-0000-0000-000000000000)/
  RequestFilesLinkEnabled | false
  RequestFilesLinkExpirationInDays | 0
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
  SiteDefinedSharingCapability | 2
  SocialBarOnSitePagesDisabled | false
  Status | Active
  StorageMaximumLevel | 1048576
  StorageUsage | 99
  StorageWarningLevel | 943718
  TeamsChannelType | 0
  Template | SPSPERS#10
  TimeZoneId | 13
  Title | John
  Url | https://contoso-my.sharepoint.com/personal/john\_contoso\_onmicrosoft\_com
  UserCodeMaximumLevel | 300
  UserCodeWarningLevel | 200
  WebsCount | 0
  ```

  </TabItem>
</Tabs>
