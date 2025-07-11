-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo tenant site list

Lists modern sites of the given type

## Usage

```sh
m365 spo tenant site list [options]
```

## Alias

```sh
m365 spo site list
```

## Options

```md definition-list
`-t, --type [type]`
: convenience option for type of sites to list. Allowed values are `TeamSite,CommunicationSite`.

`--webTemplate [webTemplate]`
: type of sites to list. To be used with values like `GROUP#0` and `SITEPAGEPUBLISHING#0`. Specify either `type` or `webTemplate`, but not both.  

`--filter [filter]`
: filter to apply when retrieving sites.

`--includeOneDriveSites`
: (deprecated. Use option `withOneDriveSites` instead) use this switch to include OneDrive sites in the result when retrieving sites. Do not specify the `type` or `webTemplate` options when using this.

`--withOneDriveSites`
: use this switch to include OneDrive sites in the result when retrieving sites. Do not specify the `type` or `webTemplate` options when using this.
```

<Global />

## Remarks

Using the `--filter` option you can specify which sites you want to retrieve. For example, to get sites with _project_ in their URL, use `Url -like 'project'` as the filter.

When using the text output type, the command lists only the values of the `Title`, and `Url` properties of the site. When setting the output type to JSON, all available properties are included in the command output.

If you wish to list deleted sites in your tenant, you should use the command [spo tenant recyclebinitem list](../tenant/tenant-recyclebinitem-list.mdx)

:::info

To use this command you have to have permissions to access the tenant admin site.

:::

## Examples

List all sites in the currently connected tenant.

```sh
m365 spo tenant site list
```

List all group connected team sites in the currently connected tenant.

```sh
m365 spo tenant site list --type TeamSite
```

List all communication sites in the currently connected tenant.

```sh
m365 spo tenant site list --type CommunicationSite
```

List all group connected team sites that contain _project_ in the URL.

```sh
m365 spo tenant site list --type TeamSite --filter "Url -like 'project'"
```

List all sites in the currently connected tenant including OneDrive sites.

```sh
m365 spo tenant site list --withOneDriveSites
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "_ObjectType_": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "_ObjectIdentity_": "c904bfa0-90e8-6000-a541-33f81aef922d|908bed80-a04a-4433-b4a0-883d9847d110:1e852b49-bf4b-4ba5-bcd4-a8c4706c8ed4\
SiteProperties\
https%3a%2f%2fcontoso.sharepoint.com%2fteams%2fteam1",
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
      "ExcludeBlockDownloadSharePointGroups": null,
      "ExcludedBlockDownloadGroupIds": [],
      "ExternalUserExpirationInDays": 0,
      "GroupId": "/Guid(00000000-0000-0000-0000-000000000000)/",
      "GroupOwnerLoginName": null,
      "HasHolds": false,
      "HubSiteId": "/Guid(b3adc7fd-ac6b-4c0b-86a0-447f14fe4d17)/",
      "IBMode": null,
      "IBSegments": [],
      "IBSegmentsToAdd": null,
      "IBSegmentsToRemove": null,
      "IsGroupOwnerSiteAdmin": false,
      "IsHubSite": false,
      "IsTeamsChannelConnected": true,
      "IsTeamsConnected": false,
      "LastContentModifiedDate": "/Date(2023,5,14,7,30,33,573)/",
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
      "RelatedGroupId": "/Guid(e5b29bb6-21ca-4d00-8d0a-abf3b6857c52)/",
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
      "SiteDefinedSharingCapability": 1,
      "SiteId": "/Guid(a7c46398-494d-4a8d-b0db-f6e58432eb67)/",
      "SocialBarOnSitePagesDisabled": false,
      "Status": "Active",
      "StorageMaximumLevel": 1048576,
      "StorageQuotaType": null,
      "StorageUsage": 0,
      "StorageWarningLevel": 1022361,
      "TeamsChannelType": 1,
      "Template": "TEAMCHANNEL#1",
      "TimeZoneId": 13,
      "Title": "Benelux Demo 031622 - demo",
      "TitleTranslations": null,
      "Url": "https://contoso.sharepoint.com/teams/team1",
      "UserCodeMaximumLevel": 300,
      "UserCodeWarningLevel": 200,
      "WebsCount": 0
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Title                            Url
  -------------------------------  ------------------------------------------------
  Give @ Contoso                   https://contoso.sharepoint.com/sites/team1
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  _ObjectType_,_ObjectIdentity_,AllowDownloadingNonWebViewableFiles,AllowEditing,AllowSelfServiceUpgrade,AnonymousLinkExpirationInDays,ApplyToExistingDocumentLibraries,ApplyToNewDocumentLibraries,ArchivedBy,ArchivedTime,ArchiveStatus,AuthContextStrength,AuthenticationContextLimitedAccess,AuthenticationContextName,AverageResourceUsage,BlockDownloadLinksFileType,BlockDownloadMicrosoft365GroupIds,BlockDownloadPolicy,BlockDownloadPolicyFileTypeIds,BlockGuestsAsSiteAdmin,BonusDiskQuota,ClearGroupId,ClearRestrictedAccessControl,CommentsOnSitePagesDisabled,CompatibilityLevel,ConditionalAccessPolicy,CurrentResourceUsage,DefaultLinkPermission,DefaultLinkToExistingAccess,DefaultLinkToExistingAccessReset,DefaultShareLinkRole,DefaultShareLinkScope,DefaultSharingLinkType,DenyAddAndCustomizePages,Description,DisableAppViews,DisableCompanyWideSharingLinks,DisableFlows,EnableAutoExpirationVersionTrim,ExcludeBlockDownloadPolicySiteOwners,ExpireVersionsAfterDays,ExternalUserExpirationInDays,GroupId,GroupOwnerLoginName,HasHolds,HubSiteId,IBMode,IBSegments,IBSegmentsToAdd,IBSegmentsToRemove,InheritVersionPolicyFromTenant,IsGroupOwnerSiteAdmin,IsHubSite,IsTeamsChannelConnected,IsTeamsConnected,LastContentModifiedDate,Lcid,LimitedAccessFileType,ListsShowHeaderAndNavigation,LockIssue,LockReason,LockState,LoopDefaultSharingLinkRole,LoopDefaultSharingLinkScope,MajorVersionLimit,MajorWithMinorVersionsLimit,MediaTranscription,OverrideBlockUserInfoVisibility,OverrideSharingCapability,EXAMPLE_SECRET_VALUE_PLACEHOLDER,EXAMPLE_SECRET_VALUE_PLACEHOLDER,Owner,OwnerEmail,OwnerLoginName,OwnerName,PWAEnabled,ReadOnlyAccessPolicy,ReadOnlyForBlockDownloadPolicy,ReadOnlyForUnmanagedDevices,RelatedGroupId,RequestFilesLinkEnabled,RequestFilesLinkExpirationInDays,RestrictContentOrgWideSearch,RestrictedAccessControl,RestrictedAccessControlGroups,RestrictedAccessControlGroupsToAdd,RestrictedAccessControlGroupsToRemove,RestrictedToRegion,SandboxedCodeActivationCapability,SensitivityLabel,SensitivityLabel2,SetOwnerWithoutUpdatingSecondaryAdmin,SharingAllowedDomainList,SharingBlockedDomainList,SharingCapability,SharingDomainRestrictionMode,SharingLockDownCanBeCleared,SharingLockDownEnabled,EXAMPLE_SECRET_VALUE_PLACEHOLDER,SiteDefinedSharingCapability,SiteId,SocialBarOnSitePagesDisabled,Status,StorageMaximumLevel,StorageQuotaType,StorageUsage,StorageWarningLevel,TeamsChannelType,Template,TimeZoneId,Title,TitleTranslations,Url,UserCodeMaximumLevel,UserCodeWarningLevel,WebsCount
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,"7f934fa1-20ab-9000-f15c-df8f2970f555|908bed80-a04a-4433-b4a0-883d9847d110:18c58817-3bc9-489d-ac63-f7264fb357e5
SiteProperties
https%3a%2f%2fcontoso.sharepoint.com%2fsites%2fteam1",,,1,0,,,,"/Date(1,0,1,0,0,0,0)/",NotArchived,,,,0,0,,,,0,0,,,,15,0,0,0,,,0,0,0,2,,0,0,0,,,0,0,/Guid(004db326-a1de-4c5e-ad45-746fd89f57bb)/,,,/Guid(00000000-0000-0000-0000-000000000000)/,,,,,,,,,,"/Date(2024,6,17,21,54,44,437)/",1033,0,,,0,Unlock,0,0,0,0,0,0,,,,,,,,1,,,,/Guid(004db326-a1de-4c5e-ad45-746fd89f57bb)/,,0,,,,,,3,0,/Guid(00000000-0000-0000-0000-000000000000)/,,,,,1,0,,,,1,/Guid(a7c46398-494d-4a8d-b0db-f6e58432eb67)/,,Active,26214400,,1,25574400,0,GROUP#0,3,team1,,https://contoso.sharepoint.com/sites/team1,300,200,0
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo site list --filter "Url -like 'comm'"

  Date: 2023-06-21

  ## team1 (https://contoso.sharepoint.com/sites/team1)

  Property | Value
  ---------|-------
  \_ObjectType\_ | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  \_ObjectIdentity\_ | 9705bfa0-a04c-6000-dbee-f912abf55939\|908bed80-a04a-4433-b4a0-883d9847d110:1e852b49-bf4b-4ba5-bcd4-a8c4706c8ed4<br>SiteProperties<br>https%3a%2f%2fcontoso.sharepoint.com%2fsites%2fteam1
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
  LastContentModifiedDate | /Date(2023,1,25,23,52,17,163)/
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
  Owner | markus@contoso.onmicrosoft.com
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
  SiteDefinedSharingCapability | 0
  SiteId | /Guid(a7c46398-494d-4a8d-b0db-f6e58432eb67)/,
  SocialBarOnSitePagesDisabled | false
  Status | Active
  StorageMaximumLevel | 0
  StorageUsage | 1
  StorageWarningLevel | 25574400
  TeamsChannelType | 0
  Template | SITEPAGEPUBLISHING#0
  TimeZoneId | 13
  Title | team1
  Url | https://contoso.sharepoint.com/sites/team1
  UserCodeMaximumLevel | 300
  UserCodeWarningLevel | 200
  WebsCount | 0
  ```

  </TabItem>
</Tabs>
