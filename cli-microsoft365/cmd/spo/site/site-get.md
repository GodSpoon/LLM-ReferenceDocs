-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo site get

Gets information about the specific site collection

## Usage

```sh
m365 spo site get [options]
```

## Options

```md definition-list
`-u, --url <url>`
: URL of the site collection to retrieve information for
```

<Global />

## Remarks

This command can retrieve information for both classic and modern sites.

## Examples

Return information about the _https://contoso.sharepoint.com/sites/project-x_ site collection.

```sh
m365 spo site get -u https://contoso.sharepoint.com/sites/project-x
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "AllowCreateDeclarativeWorkflow": true,
    "AllowDesigner": true,
    "AllowMasterPageEditing": false,
    "AllowRevertFromTemplate": false,
    "AllowSaveDeclarativeWorkflowAsTemplate": true,
    "AllowSavePublishDeclarativeWorkflow": true,
    "AllowSelfServiceUpgrade": true,
    "AllowSelfServiceUpgradeEvaluation": true,
    "AuditLogTrimmingRetention": 90,
    "ChannelGroupId": "00000000-0000-0000-0000-000000000000",
    "Classification": "",
    "CompatibilityLevel": 15,
    "CurrentChangeToken": {
      "StringValue": "1;1;a6dd24a9-6fb1-45af-9e7e-5f8a2dbdf787;638229493994700000;1164779077"
    },
    "DisableAppViews": false,
    "DisableCompanyWideSharingLinks": false,
    "DisableFlows": false,
    "ExternalSharingTipsEnabled": false,
    "GeoLocation": "EUR",
    "GroupId": "00000000-0000-0000-0000-000000000000",
    "HubSiteId": "00000000-0000-0000-0000-000000000000",
    "Id": "a6dd24a9-6fb1-45af-9e7e-5f8a2dbdf787",
    "SensitivityLabelId": "",
    "SensitivityLabel": "00000000-0000-0000-0000-000000000000",
    "IsHubSite": false,
    "LockIssue": null,
    "MaxItemsPerThrottledOperation": 5000,
    "MediaTranscriptionDisabled": false,
    "NeedsB2BUpgrade": false,
    "ResourcePath": {
      "DecodedUrl": "https://contoso.sharepoint.com/sites/team1"
    },
    "PrimaryUri": "https://contoso.sharepoint.com/sites/team1",
    "ReadOnly": false,
    "RequiredDesignerVersion": "15.0.0.0",
    "SandboxedCodeActivationCapability": 2,
    "ServerRelativeUrl": "/sites/team1",
    "ShareByEmailEnabled": false,
    "ShareByLinkEnabled": false,
    "ShowUrlStructure": false,
    "TrimAuditLog": true,
    "UIVersionConfigurationEnabled": false,
    "UpgradeReminderDate": "1899-12-30T00:00:00",
    "UpgradeScheduled": false,
    "UpgradeScheduledDate": "1753-01-01T00:00:00",
    "Upgrading": false,
    "Url": "https://contoso.sharepoint.com/sites/team1",
    "WriteLocked": false
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  AllowCreateDeclarativeWorkflow        : true
  AllowDesigner                         : true
  AllowMasterPageEditing                : false
  AllowRevertFromTemplate               : false
  AllowSaveDeclarativeWorkflowAsTemplate: true
  AllowSavePublishDeclarativeWorkflow   : true
  AllowSelfServiceUpgrade               : true
  AllowSelfServiceUpgradeEvaluation     : true
  AuditLogTrimmingRetention             : 90
  ChannelGroupId                        : 00000000-0000-0000-0000-000000000000
  Classification                        :
  CompatibilityLevel                    : 15
  CurrentChangeToken                    : {"StringValue":"1;1;a6dd24a9-6fb1-45af-9e7e-5f8a2dbdf787;638229494439430000;1164779297"}
  DisableAppViews                       : false
  DisableCompanyWideSharingLinks        : false
  DisableFlows                          : false
  ExternalSharingTipsEnabled            : false
  GeoLocation                           : EUR
  GroupId                               : 00000000-0000-0000-0000-000000000000
  HubSiteId                             : 00000000-0000-0000-0000-000000000000
  Id                                    : a6dd24a9-6fb1-45af-9e7e-5f8a2dbdf787
  IsHubSite                             : false
  LockIssue                             : null
  MaxItemsPerThrottledOperation         : 5000
  MediaTranscriptionDisabled            : false
  NeedsB2BUpgrade                       : false
  PrimaryUri                            : https://contoso.sharepoint.com/sites/team1
  ReadOnly                              : false
  RequiredDesignerVersion               : 15.0.0.0
  ResourcePath                          : {"DecodedUrl":"https://contoso.sharepoint.com/sites/team1"}
  SandboxedCodeActivationCapability     : 2
  SensitivityLabel                      : 00000000-0000-0000-0000-000000000000
  SensitivityLabelId                    :
  ServerRelativeUrl                     : /sites/team1
  ShareByEmailEnabled                   : false
  ShareByLinkEnabled                    : false
  ShowUrlStructure                      : false
  TrimAuditLog                          : true
  UIVersionConfigurationEnabled         : false
  UpgradeReminderDate                   : 1899-12-30T00:00:00
  UpgradeScheduled                      : false
  UpgradeScheduledDate                  : 1753-01-01T00:00:00
  Upgrading                             : false
  Url                                   : https://contoso.sharepoint.com/sites/team1
  WriteLocked                           : false
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  AllowCreateDeclarativeWorkflow,AllowDesigner,AllowMasterPageEditing,AllowRevertFromTemplate,AllowSaveDeclarativeWorkflowAsTemplate,AllowSavePublishDeclarativeWorkflow,AllowSelfServiceUpgrade,AllowSelfServiceUpgradeEvaluation,AuditLogTrimmingRetention,ChannelGroupId,Classification,CompatibilityLevel,DisableAppViews,DisableCompanyWideSharingLinks,DisableFlows,ExternalSharingTipsEnabled,GeoLocation,GroupId,HubSiteId,Id,SensitivityLabelId,SensitivityLabel,IsHubSite,MaxItemsPerThrottledOperation,MediaTranscriptionDisabled,NeedsB2BUpgrade,PrimaryUri,ReadOnly,RequiredDesignerVersion,SandboxedCodeActivationCapability,ServerRelativeUrl,ShareByEmailEnabled,ShareByLinkEnabled,ShowUrlStructure,TrimAuditLog,UIVersionConfigurationEnabled,UpgradeReminderDate,UpgradeScheduled,UpgradeScheduledDate,Upgrading,Url,WriteLocked
  1,1,,,1,1,1,1,90,00000000-0000-0000-0000-000000000000,,15,,,,,EUR,00000000-0000-0000-0000-000000000000,00000000-0000-0000-0000-000000000000,a6dd24a9-6fb1-45af-9e7e-5f8a2dbdf787,,00000000-0000-0000-0000-000000000000,,5000,,,https://contoso.sharepoint.com/sites/team1,,15.0.0.0,2,/sites/team1,,,,1,,1899-12-30T00:00:00,,1753-01-01T00:00:00,,https://contoso.sharepoint.com/sites/team1,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo site get --url "https://contoso.sharepoint.com/sites/team1"

  Date: 2023-06-21

  ## a6dd24a9-6fb1-45af-9e7e-5f8a2dbdf787

  Property | Value
  ---------|-------
  AllowCreateDeclarativeWorkflow | true
  AllowDesigner | true
  AllowMasterPageEditing | false
  AllowRevertFromTemplate | false
  AllowSaveDeclarativeWorkflowAsTemplate | true
  AllowSavePublishDeclarativeWorkflow | true
  AllowSelfServiceUpgrade | true
  AllowSelfServiceUpgradeEvaluation | true
  AuditLogTrimmingRetention | 90
  ChannelGroupId | 00000000-0000-0000-0000-000000000000
  Classification |
  CompatibilityLevel | 15
  DisableAppViews | false
  DisableCompanyWideSharingLinks | false
  DisableFlows | false
  ExternalSharingTipsEnabled | false
  GeoLocation | EUR
  GroupId | 00000000-0000-0000-0000-000000000000
  HubSiteId | 00000000-0000-0000-0000-000000000000
  Id | a6dd24a9-6fb1-45af-9e7e-5f8a2dbdf787
  SensitivityLabelId |
  SensitivityLabel | 00000000-0000-0000-0000-000000000000
  IsHubSite | false
  MaxItemsPerThrottledOperation | 5000
  MediaTranscriptionDisabled | false
  NeedsB2BUpgrade | false
  PrimaryUri | https://contoso.sharepoint.com/sites/team1
  ReadOnly | false
  RequiredDesignerVersion | 15.0.0.0
  SandboxedCodeActivationCapability | 2
  ServerRelativeUrl | /sites/team1
  ShareByEmailEnabled | false
  ShareByLinkEnabled | false
  ShowUrlStructure | false
  TrimAuditLog | true
  UIVersionConfigurationEnabled | false
  UpgradeReminderDate | 1899-12-30T00:00:00
  UpgradeScheduled | false
  UpgradeScheduledDate | 1753-01-01T00:00:00
  Upgrading | false
  Url | https://contoso.sharepoint.com/sites/team1
  WriteLocked | false
  ```

  </TabItem>
</Tabs>
