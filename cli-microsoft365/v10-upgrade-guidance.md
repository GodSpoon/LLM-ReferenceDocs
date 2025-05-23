-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# v10 Upgrade Guidance

The v10 release of CLI for Microsoft 365 introduces several breaking changes. To assist you in upgrading to the latest version, we’ve outlined the changes and the actions you may need to take.

## CLI

### Removed command `cli reconsent`

Due to the removal of the PnP Management Shell app registration, the cli reconsent command had no use anymore. Therefore, we have removed this command from the CLI.

### Removed `showSpinner` setting

Persistent issues with the spinner led to its removal from the CLI a few months ago. However, the `showSpinner` setting remained in the CLI configuration. In this major release, we have removed the `showSpinner` setting entirely.

#### What action do I need to take?

Remove all instances in your scripts where you reference the `showSpinner` setting.

### Updated output of `cli doctor` command

In this major release, we have updated the [cli doctor](./cmd/cli/cli-doctor.mdx) command output to reflect the renaming of Azure AD to Microsoft Entra ID.

The following properties have been renamed in the result:

- `cliAadAppId` to `cliEntraAppId`
- `cliAadAppTenant` to `cliEntraAppTenant`

#### What action do I need to take?

Review the documentation of the `cli doctor` command to see the new output structure and adjust your scripts accordingly.

### Removed deprecated environment variables

In the aftermath of renaming all Azure AD-related commands and options to Microsoft Entra ID, we have removed the deprecated environment variable `CLIMICROSOFT365_AADAPPID` that was used to store the Microsoft Entra app ID.

#### What action do I need to take?

Instead of using `CLIMICROSOFT365_AADAPPID`, use `CLIMICROSOFT365_ENTRAAPPID` to store the Microsoft Entra app ID.

### Updated output of `status` command

The command output of [status](./cmd/status.mdx) has been updated. Previously, the command returned `Logged out from Microsoft 365`, now it will simply return `Logged out`.

#### What action do I need to take?

Please, update your scripts to reflect the new output of the [status](./cmd/status.mdx) command.

## Entra ID

### Removed deprecated `guest` value from `entra m365group user list` command.

In the In the entra m365group user list command, it was previously possible to use the `role` option with the value `Guest`. Since this did not yield the expected output, we have removed this option.

#### What action do I need to take?

Remove all --role guest instances from your scripts. To list guest users of a group, use [entra m365group user list](./cmd/entra/m365group/m365group-user-list.mdx) in conjunction with [entra user get](./cmd/entra/user/user-get.mdx) to determine if a user is a guest.

### Enhanced `entra m365group set` command

We've enhanced the [entra m365group set](./cmd/entra/m365group/m365group-set.mdx) command to allow retrieving a group by its `displayName`. Previously, groups could only be retrieved by their ID. We have replaced the original `displayName` option with `newDisplayName`. Additionally, owners/members not specified in the command will now be **removed** from the group. To add members/owners without affecting existing ones, use [entra m365group user add](./cmd/entra/m365group/m365group-user-add).

#### What action do I need to take?

Ensure your scripts use `newDisplayName` when updating groups by `displayName`. Also, ensure that all intended group members and owners are specified, as any unspecified members or owners will be removed.

### Removed `aad` options and aliasses

As part of renaming Azure AD to Microsoft Entra ID, all references to `aad` in command and option names have been replaced with `entra`. For example, `aadAppId` is now `entraAppId`.

#### What action do I need to take?

Update any `aad` references in your scripts to `entra` for compatibility.

## SharePoint

### Updated `spo site appcatalog remove` options

The [spo site appcatalog remove](./cmd/spo/site/site-appcatalog-remove.mdx) command now includes a confirmation prompt to prevent unintentional deletions. To bypass this prompt, use the `--force` flag.

#### What action do I need to take?

Add `--force` to your scripts to bypass the confirmation prompt, if desired.

### Removed deprecated `wait` option from `spo site remove` and `spo tenant recyclebinitem restore`

The deprecated `wait` option has been removed from the [spo site remove](./cmd/spo/site/site-remove.mdx) and [spo tenant recyclebinitem restore](./cmd/spo/tenant/tenant-recyclebinitem-restore.mdx) commands. These commands no longer return a response on success.

**What action do I need to take?**

Remove the `--wait` option and adjust scripts to not expect a response from these commands.

### Removes duplicate property from `spo list list` command.

In the [spo list list](./cmd/spo/list/list-list.mdx) we removed the `Url` from the command output as it was a duplicate of the `RootFolder/ServerRelativeUrl` property.

#### What action do I need to take?

Please update your scripts not to use the `Url` property from the command output, instead use `RootFolder/ServerRelativeUrl`.

### Updated commands for file and folder operations

Due to limitations with the current endpoints for file and folder operations, the commands [spo file copy](./cmd/spo/file/file-copy.mdx), [spo file move](./cmd/spo/file/file-move.mdx), [spo folder copy](./cmd/spo/folder/folder-copy.mdx), and [spo file move](./cmd/spo/file/file-move.mdx) have been updated to use new endpoints. This change improves the commands' functionality and reliability. Consequently, the command inputs and outputs have been updated.

Several options previously available are no longer supported with the new commands:

* `spo file copy`: Removed `--resetAuthorAndCreated`
* `spo file move`: Removed `--retainEditorAndModified`
* `spo folder copy`: Removed `--resetAuthorAndCreated` and `--bypassSharedLock`
* `spo folder move`: Removed `--retainEditorAndModified` and `--bypassSharedLock`

In return, we have added new options to the commands:

* `spo file copy`:
  * `--ignoreVersionHistory`: Only copy the most recent version of the file and ignore the version history.
  * `--skipWait`: Don't wait for the move operation to complete.
* `spo file move`:
  * `--includeItemPermissions`: Ensure that item-level permissions are preserved during the move.
  * `--skipWait`: Don't wait for the move operation to complete.
* `spo folder copy` and `spo folder move`:
  * `--skipWait`: Don't wait for the move operation to complete.

Previously, these commands provided no output, making it difficult to track the final name of copied or moved items, especially when using the `--nameConflictBehavior rename` option. With the new endpoints, each command now returns information about the destination file or folder, allowing you to seamlessly execute further commands on the moved or copied items.

#### What action do I need to take?

To continue using these commands, update your scripts and automation tools to reflect the new command inputs. Remove any unsupported options (`--resetAuthorAndCreated`, `--retainEditorAndModified`, and `--bypassSharedLock` where applicable) to ensure compatibility with the updated commands.

### Updated output of `spo applicationcustomizer get` command

In the previous version of CLI, the command output had a `Rights` property that was a stringified JSON object. In this release, this has been changed to a JSON object.

#### What action do I need to take?

Please, check the documentation of the [spo applicationcustomizer get](./cmd/spo/applicationcustomizer/applicationcustomizer-get.mdx) command to see the updated output and adjust your scripts accordingly. If you are using the `Rights` property, there is no change you should make.

### Updated `spo sitescript get` output

We updated the output from the [spo sitescript get](./cmd/spo/sitescript/sitescript-get.mdx) command. The `Content` property is now a JSON object instead of a stringified JSON object, so it's easier to interact with the sitescript data, even when `--content` is not specified.

#### What action do I need to take?

Adjust your scripts to expect a valid JSON object instead of a stringified object in the `Content` property of the output.

## SharePoint Framework

### Removed overwrite option from `spfx project github workflow add` command

Overwriting the SPFx package should be the default behavior of the continuous delivery pipeline. The `overwrite` option was removed from the [spfx project github workflow add](./cmd/spfx/project/project-github-workflow-add.mdx) command.

#### What action do I need to take?

Please update your scripts not to use the `--overwrite` option.

## Teams

### Enhanced `teams cache remove` command

We enhanced the [teams cache remove](./cmd/teams/cache/cache-remove.mdx) command to support the removal of the cache from the new Teams client. The breaking change we introduced is that it now targets new Teams clients by default. 

To still support the old client, we have added the option `--client`, in which you can specify `classic` as value to remove the cache of the old Teams client.

#### What action do I need to take?

Add the `--client` option to your scripts to specify which client's cache you want to remove. Otherwise, it will attempt to remove the cache from the new client.

### Removes duplicate property from 'teams tab list' command.

For the [teams tab list](./cmd/teams/tab/tab-list.mdx) command we removed the `teamsAppTabId` from the command output as it was a duplicate of the `teamsApp/id` property.

#### What action do I need to take?

Please update your scripts not to use the `teamsAppTabId` property from the command output. Instead, use the `teamsApp/id` property.

## General

### Aligned command names

Some command names have been updated to reflect the latest Microsoft 365 terminology. Additionally, command improvements sometimes lead to renaming for better functionality alignment.

v9 command | v10 command
--- | ---
`entra group user add` | [entra group member add](./cmd/entra/group/group-member-add.mdx)
`entra group user list` | [entra group member list](./cmd/entra/group/group-member-list.mdx)
`entra group user set` | [entra group member set](./cmd/entra/group/group-member-set.mdx)
`spo folder rename` | [spo folder set](./cmd/spo/folder/folder-set.mdx)
`spo site rename` | [spo tenant site rename](./cmd/spo/tenant/tenant-site-rename.mdx)
`yammer search` | [viva engage search](./cmd/viva/engage/engage-search.mdx)
`yammer group list` | [viva engage group list](./cmd/viva/engage/engage-group-list.mdx)
`yammer group user add` | [viva engage group user add](./cmd/viva/engage/engage-group-user-add.mdx)
`yammer group user remove` | [viva engage group user remove](./cmd/viva/engage/engage-group-user-remove.mdx)
`yammer message add` | [viva engage message add](./cmd/viva/engage/engage-message-add.mdx)
`yammer message get` | [viva engage message get](./cmd/viva/engage/engage-message-get.mdx)
`yammer message list` | [viva engage message list](./cmd/viva/engage/engage-message-list.mdx)
`yammer message remove` | [viva engage message remove](./cmd/viva/engage/engage-message-remove.mdx)
`yammer message like set` | [viva engage message like set](./cmd/viva/engage/engage-message-like-set.mdx)
`yammer network list` | [viva engage network list](./cmd/viva/engage/engage-network-list.mdx)
`yammer report activitycounts` | [viva engage report activitycounts](./cmd/viva/engage/engage-report-activitycounts.mdx)
`yammer report activityusercounts` | [viva engage report activityusercounts](./cmd/viva/engage/engage-report-activityusercounts.mdx)
`yammer report activityuserdetail` | [viva engage report activityuserdetail](./cmd/viva/engage/engage-report-activityuserdetail.mdx)
`yammer report deviceusagedistributionusercounts` | [viva engage report deviceusagedistributionusercounts](./cmd/viva/engage/EXAMPLE_SECRET_VALUE_PLACEHOLDER)
`yammer report deviceusageusercounts` | [viva engage report deviceusageusercounts](./cmd/viva/engage/engage-report-deviceusageusercounts.mdx)
`yammer report deviceusageuserdetail` | [viva engage report deviceusageuserdetail](./cmd/viva/engage/engage-report-deviceusageuserdetail.mdx)
`yammer report groupsactivitycounts` | [viva engage report groupsactivitycounts](./cmd/viva/engage/engage-report-groupsactivitycounts.mdx)
`yammer report groupsactivitydetail` | [viva engage report groupsactivitydetail](./cmd/viva/engage/engage-report-groupsactivitydetail.mdx)
`yammer report groupsactivitygroupcounts` | [viva engage report groupsactivitygroupcounts](./cmd/viva/engage/EXAMPLE_SECRET_VALUE_PLACEHOLDER)
`yammer user get` | [viva engage user get](./cmd/viva/engage/engage-user-get.mdx)
`yammer user list` | [viva engage user list](./cmd/viva/engage/engage-user-list.mdx)

#### What action do I need to take?

Update your scripts to use the new command names listed.

### Aligned naming options

Just like with command names, we also have to rename options to reflect the changes in the product. We also try to make the options more descriptive and clearer to make it easier for you to use the CLI.
These changes aim to make it easier for you to use the CLI.

We've updated the following options:

Command | Old option | New option
------- | ---------- | ----------
[app permission add](./cmd/app/permission/permission-add.mdx) | `applicationPermission` <br /> `delegatedPermission` | `applicationPermissions` <br /> `delegatedPermissions`
[entra enterpriseapp add](./cmd/entra/enterpriseapp/enterpriseapp-add) | `appId` <br /> `appName` | `id` <br /> `displayName`
[entra enterpriseapp get](./cmd/entra/enterpriseapp/enterpriseapp-get) | `appId` <br /> `appDisplayName` <br /> `appObjectId` | `id` <br /> `displayName` <br /> `objectId`
[entra group member list](./cmd/entra/group/group-member-list.mdx) | `groupDisplayName` | `groupName`
[entra m365group set](./cmd/entra/m365group/m365group-set.mdx) | `displayName` | `newDisplayName`
[entra m365group conversation post list](./cmd/entra/m365group/m365group-conversation-post-list.mdx) | `groupDisplayName` | `groupName`
[entra m365group recyclebinitem list](./cmd/entra/m365group/m365group-recyclebinitem-list.mdx) | `groupDisplayName` | `groupName`
[entra m365group user add](./cmd/entra/m365group/m365group-user-add.mdx) | `userName` | `userNames`
[entra m365group user remove](./cmd/entra/m365group/m365group-user-remove.mdx) | `userName` | `userNames`
[entra m365group user set](./cmd/entra/m365group/m365group-user-set.mdx) | `userName` | `userNames`
[outlook message get](./cmd/outlook/message/message-get.mdx) | `userPrincipalName` | `userName`
[spo contenttype field remove](./cmd/spo/contenttype/contenttype-field-remove.mdx) | `i` <br /> `fieldLinkId` | `contentTypeId` <br /> `id`
[spo contenttype field set](./cmd/spo/contenttype/contenttype-field-set.mdx) | `i` | `contentTypeId`

#### What action do I need to take?

If you use any of the commands listed above, ensure that you use the new option names.

### Ensured output for `list` commands

We noticed that some of the `list` commands were not returning any output when no items were found. We've updated all `list` commands to return an empty array when no items are found.

The commands impacted by this change are:

- [entra oauth2grant list](./cmd/entra/oauth2grant/oauth2grant-list.mdx)
- [flow environment list](./cmd/flow/environment/environment-list.mdx)
- [pa app list](./cmd/pa/app/app-list.mdx)
- [pa connector list](./cmd/pa/connector/connector-list.mdx)
- [pa environment list](./cmd/pa/environment/environment-list.mdx)
- [pp environment list](./cmd/pp/environment/environment-list.mdx)
- [spo app instance list](./cmd/spo/app/app-instance-list.mdx)
- [spo app list](./cmd/spo/app/app-list.mdx)
- [spo feature list](./cmd/spo/feature/feature-list.mdx)
- [spo list webhook list](./cmd/spo/list/list-webhook-list.mdx)
- [spo listitem attachment list](./cmd/spo/listitem/listitem-attachment-list.mdx)
- [spo page list](./cmd/spo/page/page-list.mdx)
- [spo page template list](./cmd/spo/page/page-template-list.mdx)
- [spo sitescript list](./cmd/spo/sitescript/sitescript-list.mdx)
- [spo theme list](./cmd/spo/theme/theme-list.mdx)
- [spo web clientsidewebpart list](./cmd/spo/web/web-clientsidewebpart-list.mdx)

#### What action do I need to take?

Update your scripts to expect an empty array when no items are found.
