<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - SPO Commands Reference

*This is an automatically generated condensed reference of all SPO commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-06-01*

---

## Table of Contents

- [app-add](#app-add)
- [app-deploy](#app-deploy)
- [app-get](#app-get)
- [app-install](#app-install)
- [app-instance-list](#app-instance-list)
- [applicationcustomizer-add](#applicationcustomizer-add)
- [applicationcustomizer-get](#applicationcustomizer-get)
- [applicationcustomizer-list](#applicationcustomizer-list)
- [applicationcustomizer-remove](#applicationcustomizer-remove)
- [applicationcustomizer-set](#applicationcustomizer-set)
- [app-list](#app-list)
- [apppage-add](#apppage-add)
- [apppage-set](#apppage-set)
- [app-remove](#app-remove)
- [app-retract](#app-retract)
- [app-teamspackage-download](#app-teamspackage-download)
- [app-uninstall](#app-uninstall)
- [app-upgrade](#app-upgrade)
- [cdn-get](#cdn-get)
- [cdn-origin-add](#cdn-origin-add)
- [cdn-origin-list](#cdn-origin-list)
- [cdn-origin-remove](#cdn-origin-remove)
- [cdn-policy-list](#cdn-policy-list)
- [cdn-policy-set](#cdn-policy-set)
- [cdn-set](#cdn-set)
- [commandset-add](#commandset-add)
- [commandset-get](#commandset-get)
- [commandset-list](#commandset-list)
- [commandset-remove](#commandset-remove)
- [commandset-set](#commandset-set)
- [contenttype-add](#contenttype-add)
- [contenttype-field-list](#contenttype-field-list)
- [contenttype-field-remove](#contenttype-field-remove)
- [contenttype-field-set](#contenttype-field-set)
- [contenttype-get](#contenttype-get)
- [contenttypehub-get](#contenttypehub-get)
- [contenttype-list](#contenttype-list)
- [contenttype-remove](#contenttype-remove)
- [contenttype-set](#contenttype-set)
- [contenttype-sync](#contenttype-sync)
- [customaction-add](#customaction-add)
- [customaction-clear](#customaction-clear)
- [customaction-get](#customaction-get)
- [customaction-list](#customaction-list)
- [customaction-remove](#customaction-remove)
- [customaction-set](#customaction-set)
- [eventreceiver-get](#eventreceiver-get)
- [eventreceiver-list](#eventreceiver-list)
- [eventreceiver-remove](#eventreceiver-remove)
- [externaluser-list](#externaluser-list)
- [feature-disable](#feature-disable)
- [feature-enable](#feature-enable)
- [feature-list](#feature-list)
- [field-add](#field-add)
- [field-get](#field-get)
- [field-list](#field-list)
- [field-remove](#field-remove)
- [field-set](#field-set)
- [file-add](#file-add)
- [file-checkin](#file-checkin)
- [file-checkout](#file-checkout)
- [file-checkout-undo](#file-checkout-undo)
- [file-copy](#file-copy)
- [file-get](#file-get)
- [file-list](#file-list)
- [file-move](#file-move)
- [file-remove](#file-remove)
- [file-rename](#file-rename)
- [file-retentionlabel-ensure](#file-retentionlabel-ensure)
- [file-retentionlabel-remove](#file-retentionlabel-remove)
- [file-roleassignment-add](#file-roleassignment-add)
- [file-roleassignment-remove](#file-roleassignment-remove)
- [file-roleinheritance-break](#file-roleinheritance-break)
- [file-roleinheritance-reset](#file-roleinheritance-reset)
- [file-sharinginfo-get](#file-sharinginfo-get)
- [file-sharinglink-add](#file-sharinglink-add)
- [file-sharinglink-clear](#file-sharinglink-clear)
- [file-sharinglink-get](#file-sharinglink-get)
- [file-sharinglink-list](#file-sharinglink-list)
- [file-sharinglink-remove](#file-sharinglink-remove)
- [file-sharinglink-set](#file-sharinglink-set)
- [file-version-clear](#file-version-clear)
- [file-version-get](#file-version-get)
- [file-version-list](#file-version-list)
- [file-version-remove](#file-version-remove)
- [file-version-restore](#file-version-restore)
- [folder-add](#folder-add)
- [folder-copy](#folder-copy)
- [folder-get](#folder-get)
- [folder-list](#folder-list)
- [folder-move](#folder-move)
- [folder-remove](#folder-remove)
- [folder-retentionlabel-ensure](#folder-retentionlabel-ensure)
- [folder-retentionlabel-remove](#folder-retentionlabel-remove)
- [folder-roleassignment-add](#folder-roleassignment-add)
- [folder-roleassignment-remove](#folder-roleassignment-remove)
- [folder-roleinheritance-break](#folder-roleinheritance-break)
- [folder-roleinheritance-reset](#folder-roleinheritance-reset)
- [folder-set](#folder-set)
- [folder-sharinglink-add](#folder-sharinglink-add)
- [folder-sharinglink-clear](#folder-sharinglink-clear)
- [folder-sharinglink-get](#folder-sharinglink-get)
- [folder-sharinglink-list](#folder-sharinglink-list)
- [folder-sharinglink-remove](#folder-sharinglink-remove)
- [folder-sharinglink-set](#folder-sharinglink-set)
- [group-add](#group-add)
- [group-get](#group-get)
- [group-list](#group-list)
- [group-member-add](#group-member-add)
- [group-member-list](#group-member-list)
- [group-member-remove](#group-member-remove)
- [group-remove](#group-remove)
- [group-set](#group-set)
- [hidedefaultthemes-get](#hidedefaultthemes-get)
- [hidedefaultthemes-set](#hidedefaultthemes-set)
- [homesite-add](#homesite-add)
- [homesite-get](#homesite-get)
- [homesite-list](#homesite-list)
- [homesite-remove](#homesite-remove)
- [homesite-set](#homesite-set)
- [hubsite-connect](#hubsite-connect)
- [hubsite-data-get](#hubsite-data-get)
- [hubsite-disconnect](#hubsite-disconnect)
- [hubsite-get](#hubsite-get)
- [hubsite-list](#hubsite-list)
- [hubsite-register](#hubsite-register)
- [hubsite-rights-grant](#hubsite-rights-grant)
- [hubsite-rights-revoke](#hubsite-rights-revoke)
- [hubsite-set](#hubsite-set)
- [hubsite-unregister](#hubsite-unregister)
- [knowledgehub-get](#knowledgehub-get)
- [knowledgehub-remove](#knowledgehub-remove)
- [knowledgehub-set](#knowledgehub-set)
- [list-add](#list-add)
- [list-contenttype-add](#list-contenttype-add)
- [list-contenttype-default-set](#list-contenttype-default-set)
- [list-contenttype-list](#list-contenttype-list)
- [list-contenttype-remove](#list-contenttype-remove)
- [list-defaultvalue-clear](#list-defaultvalue-clear)
- [list-defaultvalue-list](#list-defaultvalue-list)
- [list-defaultvalue-remove](#list-defaultvalue-remove)
- [list-defaultvalue-set](#list-defaultvalue-set)
- [list-get](#list-get)
- [listitem-add](#listitem-add)
- [listitem-attachment-add](#listitem-attachment-add)
- [listitem-attachment-get](#listitem-attachment-get)
- [listitem-attachment-list](#listitem-attachment-list)
- [listitem-attachment-remove](#listitem-attachment-remove)
- [listitem-attachment-set](#listitem-attachment-set)
- [listitem-batch-add](#listitem-batch-add)
- [listitem-batch-remove](#listitem-batch-remove)
- [listitem-batch-set](#listitem-batch-set)
- [listitem-get](#listitem-get)
- [listitem-isrecord](#listitem-isrecord)
- [listitem-list](#listitem-list)
- [listitem-record-declare](#listitem-record-declare)
- [listitem-record-lock](#listitem-record-lock)
- [listitem-record-undeclare](#listitem-record-undeclare)
- [listitem-record-unlock](#listitem-record-unlock)
- [listitem-remove](#listitem-remove)
- [listitem-retentionlabel-ensure](#listitem-retentionlabel-ensure)
- [listitem-retentionlabel-remove](#listitem-retentionlabel-remove)
- [listitem-roleassignment-add](#listitem-roleassignment-add)
- [listitem-roleassignment-remove](#listitem-roleassignment-remove)
- [listitem-roleinheritance-break](#listitem-roleinheritance-break)
- [listitem-roleinheritance-reset](#listitem-roleinheritance-reset)
- [listitem-set](#listitem-set)
- [list-list](#list-list)
- [list-remove](#list-remove)
- [list-retentionlabel-ensure](#list-retentionlabel-ensure)
- [list-retentionlabel-get](#list-retentionlabel-get)
- [list-retentionlabel-remove](#list-retentionlabel-remove)
- [list-roleassignment-add](#list-roleassignment-add)
- [list-roleassignment-remove](#list-roleassignment-remove)
- [list-roleinheritance-break](#list-roleinheritance-break)
- [list-roleinheritance-reset](#list-roleinheritance-reset)
- [list-sensitivitylabel-ensure](#list-sensitivitylabel-ensure)
- [list-set](#list-set)
- [list-sitescript-get](#list-sitescript-get)
- [list-view-add](#list-view-add)
- [list-view-field-add](#list-view-field-add)
- [list-view-field-remove](#list-view-field-remove)
- [list-view-field-set](#list-view-field-set)
- [list-view-get](#list-view-get)
- [list-view-list](#list-view-list)
- [list-view-remove](#list-view-remove)
- [list-view-set](#list-view-set)
- [list-webhook-add](#list-webhook-add)
- [list-webhook-get](#list-webhook-get)
- [list-webhook-list](#list-webhook-list)
- [list-webhook-remove](#list-webhook-remove)
- [list-webhook-set](#list-webhook-set)
- [mail-send](#mail-send)
- [navigation-node-add](#navigation-node-add)
- [navigation-node-get](#navigation-node-get)
- [navigation-node-list](#navigation-node-list)
- [navigation-node-remove](#navigation-node-remove)
- [navigation-node-set](#navigation-node-set)
- [orgassetslibrary-add](#orgassetslibrary-add)
- [orgassetslibrary-list](#orgassetslibrary-list)
- [orgassetslibrary-remove](#orgassetslibrary-remove)
- [orgnewssite-list](#orgnewssite-list)
- [orgnewssite-remove](#orgnewssite-remove)
- [orgnewssite-set](#orgnewssite-set)
- [page-add](#page-add)
- [page-clientsidewebpart-add](#page-clientsidewebpart-add)
- [page-column-get](#page-column-get)
- [page-column-list](#page-column-list)
- [page-control-get](#page-control-get)
- [page-control-list](#page-control-list)
- [page-control-set](#page-control-set)
- [page-copy](#page-copy)
- [page-get](#page-get)
- [page-header-set](#page-header-set)
- [page-list](#page-list)
- [page-publish](#page-publish)
- [page-remove](#page-remove)
- [page-section-add](#page-section-add)
- [page-section-get](#page-section-get)
- [page-section-list](#page-section-list)
- [page-section-remove](#page-section-remove)
- [page-set](#page-set)
- [page-template-list](#page-template-list)
- [page-text-add](#page-text-add)
- [propertybag-get](#propertybag-get)
- [propertybag-list](#propertybag-list)
- [propertybag-remove](#propertybag-remove)
- [propertybag-set](#propertybag-set)
- [report-activityfilecounts](#report-activityfilecounts)
- [report-activitypages](#report-activitypages)
- [report-activityusercounts](#report-activityusercounts)
- [report-activityuserdetail](#report-activityuserdetail)
- [report-siteusagedetail](#report-siteusagedetail)
- [report-siteusagefilecounts](#report-siteusagefilecounts)
- [report-siteusagepages](#report-siteusagepages)
- [report-siteusagesitecounts](#report-siteusagesitecounts)
- [report-siteusagestorage](#report-siteusagestorage)
- [roledefinition-add](#roledefinition-add)
- [roledefinition-get](#roledefinition-get)
- [roledefinition-list](#roledefinition-list)
- [roledefinition-remove](#roledefinition-remove)
- [serviceprincipal-grant-add](#serviceprincipal-grant-add)
- [serviceprincipal-grant-list](#serviceprincipal-grant-list)
- [serviceprincipal-grant-revoke](#serviceprincipal-grant-revoke)
- [EXAMPLE_SECRET_VALUE_PLACEHOLDER](#EXAMPLE_SECRET_VALUE_PLACEHOLDER)
- [serviceprincipal-permissionrequest-deny](#serviceprincipal-permissionrequest-deny)
- [serviceprincipal-permissionrequest-list](#serviceprincipal-permissionrequest-list)
- [serviceprincipal-set](#serviceprincipal-set)
- [site-add](#site-add)
- [site-admin-add](#site-admin-add)
- [site-admin-list](#site-admin-list)
- [site-admin-remove](#site-admin-remove)
- [site-appcatalog-add](#site-appcatalog-add)
- [site-appcatalog-list](#site-appcatalog-list)
- [site-appcatalog-remove](#site-appcatalog-remove)
- [site-apppermission-add](#site-apppermission-add)
- [site-apppermission-get](#site-apppermission-get)
- [site-apppermission-list](#site-apppermission-list)
- [site-apppermission-remove](#site-apppermission-remove)
- [site-apppermission-set](#site-apppermission-set)
- [site-chrome-set](#site-chrome-set)
- [site-commsite-enable](#site-commsite-enable)
- [sitedesign-add](#sitedesign-add)
- [sitedesign-apply](#sitedesign-apply)
- [sitedesign-get](#sitedesign-get)
- [sitedesign-list](#sitedesign-list)
- [sitedesign-remove](#sitedesign-remove)
- [sitedesign-rights-grant](#sitedesign-rights-grant)
- [sitedesign-rights-list](#sitedesign-rights-list)
- [sitedesign-rights-revoke](#sitedesign-rights-revoke)
- [sitedesign-run-list](#sitedesign-run-list)
- [sitedesign-run-status-get](#sitedesign-run-status-get)
- [sitedesign-set](#sitedesign-set)
- [sitedesign-task-get](#sitedesign-task-get)
- [sitedesign-task-list](#sitedesign-task-list)
- [sitedesign-task-remove](#sitedesign-task-remove)
- [site-ensure](#site-ensure)
- [site-get](#site-get)
- [site-groupify](#site-groupify)
- [site-hubsite-connect](#site-hubsite-connect)
- [site-hubsite-disconnect](#site-hubsite-disconnect)
- [site-hubsite-theme-sync](#site-hubsite-theme-sync)
- [site-inplacerecordsmanagement-set](#site-inplacerecordsmanagement-set)
- [site-recyclebinitem-clear](#site-recyclebinitem-clear)
- [site-recyclebinitem-list](#site-recyclebinitem-list)
- [site-recyclebinitem-move](#site-recyclebinitem-move)
- [site-recyclebinitem-remove](#site-recyclebinitem-remove)
- [site-recyclebinitem-restore](#site-recyclebinitem-restore)
- [site-remove](#site-remove)
- [sitescript-add](#sitescript-add)
- [sitescript-get](#sitescript-get)
- [sitescript-list](#sitescript-list)
- [sitescript-remove](#sitescript-remove)
- [sitescript-set](#sitescript-set)
- [site-set](#site-set)
- [site-sharingpermission-set](#site-sharingpermission-set)
- [spo-get](#spo-get)
- [spo-search](#spo-search)
- [spo-set](#spo-set)
- [storageentity-get](#storageentity-get)
- [storageentity-list](#storageentity-list)
- [storageentity-remove](#storageentity-remove)
- [storageentity-set](#storageentity-set)
- [tenant-appcatalog-add](#tenant-appcatalog-add)
- [tenant-appcatalogurl-get](#tenant-appcatalogurl-get)
- [tenant-applicationcustomizer-add](#tenant-applicationcustomizer-add)
- [tenant-applicationcustomizer-get](#tenant-applicationcustomizer-get)
- [tenant-applicationcustomizer-list](#tenant-applicationcustomizer-list)
- [tenant-applicationcustomizer-remove](#tenant-applicationcustomizer-remove)
- [tenant-applicationcustomizer-set](#tenant-applicationcustomizer-set)
- [tenant-commandset-add](#tenant-commandset-add)
- [tenant-commandset-get](#tenant-commandset-get)
- [tenant-commandset-list](#tenant-commandset-list)
- [tenant-commandset-remove](#tenant-commandset-remove)
- [tenant-commandset-set](#tenant-commandset-set)
- [tenant-recyclebinitem-list](#tenant-recyclebinitem-list)
- [tenant-recyclebinitem-remove](#tenant-recyclebinitem-remove)
- [tenant-recyclebinitem-restore](#tenant-recyclebinitem-restore)
- [tenant-settings-list](#tenant-settings-list)
- [tenant-settings-set](#tenant-settings-set)
- [tenant-site-archive](#tenant-site-archive)
- [tenant-site-list](#tenant-site-list)
- [tenant-site-membership-list](#tenant-site-membership-list)
- [tenant-site-rename](#tenant-site-rename)
- [tenant-site-unarchive](#tenant-site-unarchive)
- [term-add](#term-add)
- [term-get](#term-get)
- [term-group-add](#term-group-add)
- [term-group-get](#term-group-get)
- [term-group-list](#term-group-list)
- [term-list](#term-list)
- [term-set-add](#term-set-add)
- [term-set-get](#term-set-get)
- [term-set-list](#term-set-list)
- [theme-apply](#theme-apply)
- [theme-get](#theme-get)
- [theme-list](#theme-list)
- [theme-remove](#theme-remove)
- [theme-set](#theme-set)
- [user-ensure](#user-ensure)
- [user-get](#user-get)
- [user-list](#user-list)
- [userprofile-get](#userprofile-get)
- [userprofile-set](#userprofile-set)
- [user-remove](#user-remove)
- [web-add](#web-add)
- [web-clientsidewebpart-list](#web-clientsidewebpart-list)
- [web-get](#web-get)
- [web-installedlanguage-list](#web-installedlanguage-list)
- [web-list](#web-list)
- [web-reindex](#web-reindex)
- [web-remove](#web-remove)
- [web-retentionlabel-list](#web-retentionlabel-list)
- [web-roleassignment-add](#web-roleassignment-add)
- [web-roleassignment-remove](#web-roleassignment-remove)
- [web-roleinheritance-break](#web-roleinheritance-break)
- [web-roleinheritance-reset](#web-roleinheritance-reset)
- [web-set](#web-set)

---

## app-add

### Syntax
```
m365 spo app add [options]
```

### Example
```
m365 spo app add --filePath /Users/pnp/spfx/sharepoint/solution/spfx.sppkg

m365 spo app add --filePath sharepoint/solution/spfx.sppkg --overwrite

m365 spo app add --filePath c:\spfx.sppkg --appCatalogScope sitecollection --appCatalogUrl https://contoso.sharepoint.com/sites/site1

```

### Remarks
When specifying the path to the app package file you can use both relative and absolute paths. Note, that `~` in the path, will not be resolved and will most likely result in an error.

When adding an app to the tenant app catalog, it's not necessary to specify the tenant app catalog URL. When the URL is not specified, the CLI will try to resolve the URL itself. Specifying the app catalog URL is required when you want to add the app to a site collection app catalog.

When specifying site collection app catalog, you can specify the URL either with our without the _AppCatalog_ part, for example `https://contoso.sharepoint.com/sites/team-a/AppCatalog` or `https://contoso.sharepoint.com/sites/team-a`. CLI will accept both formats.

If you try to upload a package that already exists in the app catalog without specifying the `--overwrite` option, the command will fail with an error stating that the specified package already exists.



---

## app-deploy

### Syntax
```
m365 spo app deploy [options]
```

### Example
```
m365 spo app deploy --id EXAMPLE-GUID-PLACEHOLDER

m365 spo app deploy --id EXAMPLE-GUID-PLACEHOLDER --appCatalogScope sitecollection --appCatalogUrl https://contoso.sharepoint.com/sites/site1

m365 spo app deploy --name solution.sppkg

m365 spo app deploy --id EXAMPLE-GUID-PLACEHOLDER --appCatalogUrl https://contoso.sharepoint.com/sites/apps

m365 spo app deploy --id EXAMPLE-GUID-PLACEHOLDER --skipFeatureDeployment

```

### Remarks
When deploying an app in the tenant app catalog, it's not necessary to specify the tenant app catalog URL. When the URL is not specified, the CLI will try to resolve the URL itself. Specifying the app catalog URL is required when you want to deploy the app in a site collection app catalog.

When specifying site collection app catalog, you can specify the URL either with our without the _AppCatalog_ part, for example `https://contoso.sharepoint.com/sites/team-a/AppCatalog` or `https://contoso.sharepoint.com/sites/team-a`. CLI will accept both formats.

If the app with the specified ID doesn't exist in the app catalog, the command will fail with an error. Before you can deploy an app, you have to add it to the app catalog first using the [spo app add](./app-add.mdx) command.



---

## app-get

### Syntax
```
m365 spo app get [options]
```

### Example
```
m365 spo app get --id EXAMPLE-GUID-PLACEHOLDER

m365 spo app get --name solution.sppkg

m365 spo app get --name solution.sppkg --appCatalogUrl https://contoso.sharepoint.com/sites/apps

m365 spo app get --id EXAMPLE-GUID-PLACEHOLDER --appCatalogScope sitecollection --appCatalogUrl https://contoso.sharepoint.com/sites/site1

```

### Remarks
When getting information about an app from the tenant app catalog, it's not necessary to specify the tenant app catalog URL. When the URL is not specified, the CLI will try to resolve the URL itself. Specifying the app catalog URL is required when you want to get information about an app from a site collection app catalog.

When specifying site collection app catalog, you can specify the URL either with our without the _AppCatalog_ part, for example `https://contoso.sharepoint.com/sites/team-a/AppCatalog` or `https://contoso.sharepoint.com/sites/team-a`. CLI will accept both formats.



---

## app-install

### Syntax
```
m365 spo app install [options]
```

### Example
```
m365 spo app install --id EXAMPLE-GUID-PLACEHOLDER --siteUrl https://contoso.sharepoint.com

m365 spo app install --id EXAMPLE-GUID-PLACEHOLDER --siteUrl https://contoso.sharepoint.com --appCatalogScope sitecollection

```

### Remarks
If the app with the specified ID doesn't exist in the app catalog, the command will fail with an error. Before you can install app in a site, you have to add it to the tenant or site collection app catalog first using the [spo app add](./app-add.mdx) command.



---

## app-instance-list

### Syntax
```
m365 spo app instance list [options]
```

### Example
```
m365 spo app instance list --siteUrl https://contoso.sharepoint.com/sites/site1

```

---

## applicationcustomizer-add

### Syntax
```
m365 spo applicationcustomizer add [options]
```

### Example
```
m365 spo applicationcustomizer add --title 'Some customizer' --clientSideComponentId EXAMPLE-GUID-PLACEHOLDER --webUrl https://contoso.sharepoint.com/sites/sales

m365 spo applicationcustomizer add --title 'Some customizer' --clientSideComponentId EXAMPLE-GUID-PLACEHOLDER --clientSideComponentProperties '{ "someProperty": "Some value" }' --webUrl https://contoso.sharepoint.com/sites/sales --scope 'Site'

```

### Remarks
Running this command from the Windows Command Shell (cmd.exe) or PowerShell for Windows OS XP, 7, 8, 8.1 without bash installed might require additional formatting for command options that have JSON, XML or JavaScript values because the command shell treats quotes differently. For example, this is how an application customizer can be created from the Windows cmd.exe:

Note, how the clientSideComponentProperties option has escaped double quotes `'{\"testMessage\":\"Test message\"}'` compared to execution from bash `'{"testMessage":"Test message"}'`.

:::warning[Escaping JSON in PowerShell]

When using the `--clientSideComponentProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

This command can be used for configuring an application customizer on a specific site. To configure an application customizer tenant-wide, view our dedicated [spo tenant applicationcustomizer add](../tenant/tenant-applicationcustomizer-add.mdx) command.



---

## applicationcustomizer-get

### Syntax
```
m365 spo applicationcustomizer get [options]
```

### Example
```
m365 spo applicationcustomizer get --title "Some customizer" --webUrl https://contoso.sharepoint.com/sites/sales```

### Remarks
This command can be used for retrieving an application customizer from a specific site. To retrieve an application customizer that's installed tenant-wide, view our dedicated [spo tenant applicationcustomizer get](../tenant/tenant-applicationcustomizer-get.mdx) command.



---

## applicationcustomizer-list

### Syntax
```
m365 spo applicationcustomizer list [options]
```

### Example
```
m365 spo applicationcustomizer list --webUrl https://contoso.sharepoint.com/sites/sales

```

### Remarks
This command can be used for retrieving a list of application customizers from a specific site. To retrieve a list of application customizers that are installed tenant-wide, view our dedicated [spo tenant applicationcustomizer list](../tenant/tenant-applicationcustomizer-list.mdx) command.



---

## applicationcustomizer-remove

### Syntax
```
m365 spo applicationcustomizer remove [options]
```

### Example
```
m365 spo applicationcustomizer remove --id EXAMPLE-GUID-PLACEHOLDER --webUrl https://contoso.sharepoint.com/sites/sales```

### Remarks
If the command finds multiple application customizers with the specified title or clientSideComponentId, it will prompt you to disambiguate which customizer it should remove, listing the discovered IDs.

This command can be used for removing an application customizer added to a specific site. To remove an application customizer that's installed tenant-wide, view our dedicated [spo tenant applicationcustomizer remove](../tenant/tenant-applicationcustomizer-remove.mdx) command.

This command can be used for removing an application customizer from a specific site. To remove a tenant-wide installed application customizer, view our dedicated [spo tenant applicationcustomizer remove](../tenant/tenant-applicationcustomizer-remove.mdx) command.



---

## applicationcustomizer-set

### Syntax
```
m365 spo applicationcustomizer set [options]
```

### Example
```
m365 spo applicationcustomizer set --id EXAMPLE-GUID-PLACEHOLDER --newTitle "Some customizer" --webUrl https://contoso.sharepoint.com/sites/sales

m365 spo applicationcustomizer set --id EXAMPLE-GUID-PLACEHOLDER --clientSideComponentProperties '{ "testMessage": "Test message" }' --webUrl https://contoso.sharepoint.com/sites/sales

```

### Remarks
Running this command from the Windows Command Shell (cmd.exe) or PowerShell for Windows OS XP, 7, 8, 8.1 without bash installed might require additional formatting for clientSideComponentProperties option that has JSON value because the command shell treats quotes differently. For example, this is how Application Customizer can be updated from the Windows cmd.exe:

Note, how the clientSideComponentProperties option (--clientSideComponentProperties) has escaped double quotes `'{\"testMessage\":\"Test message\"}'` compared to execution from bash `'{"testMessage":"Test message"}'`.

:::warning[Escaping JSON in PowerShell]

When using the `--clientSideComponentProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

This command can be used for updating an application customizer on a specific site. To update an application customizer that's installed tenant-wide, view our dedicated [spo tenant applicationcustomizer set](../tenant/tenant-applicationcustomizer-set.mdx) command.



---

## app-list

### Syntax
```
m365 spo app list [options]
```

### Example
```
m365 spo app list

m365 spo app list --appCatalogScope sitecollection --appCatalogUrl https://contoso.sharepoint.com/sites/site1

```

### Remarks
When listing information about apps available in the tenant app catalog, it's not necessary to specify the tenant app catalog URL. When the URL is not specified, the CLI will try to resolve the URL itself. Specifying the app catalog URL is required when you want to list information about apps in a site collection app catalog.

When specifying site collection app catalog, you can specify the URL either with our without the _AppCatalog_ part, for example `https://contoso.sharepoint.com/sites/team-a/AppCatalog` or `https://contoso.sharepoint.com/sites/team-a`. CLI will accept both formats.

When using the text output type (default), the command lists only the values of the `Title`, `ID`, `Deployed` and `AppCatalogVersion` properties of the app. When setting the output type to JSON, all available properties are included in the command output.



---

## apppage-add

### Syntax
```
m365 spo apppage add [options]
```

### Example
```
m365 spo apppage add --title "Contoso" --webUrl "https://contoso.sharepoint.com" --webPartData $webPartData --addToQuickLaunch

```

### Remarks
If you want to add the single-part app page to quick launch, use the addToQuickLaunch flag.



---

## apppage-set

### Syntax
```
m365 spo apppage set [options]
```

### Example
```
m365 spo apppage set --webUrl "https://contoso.sharepoint.com" --name "Contoso.aspx" --webPartData $webPartData

```

---

## app-remove

### Syntax
```
m365 spo app remove [options]
```

### Example
```
m365 spo app remove --id EXAMPLE-GUID-PLACEHOLDER

m365 spo app remove --id EXAMPLE-GUID-PLACEHOLDER --appCatalogUrl https://contoso.sharepoint.com/sites/apps

m365 spo app remove --id EXAMPLE-GUID-PLACEHOLDER --appCatalogUrl https://contoso.sharepoint.com/sites/apps --force

m365 spo app remove --id EXAMPLE-GUID-PLACEHOLDER --appCatalogScope sitecollection --appCatalogUrl https://contoso.sharepoint.com/sites/site1/AppCatalog

```

### Remarks
When removing an app from the tenant app catalog, it's not necessary to specify the tenant app catalog URL. When the URL is not specified, the CLI will try to resolve the URL itself. Specifying the app catalog URL is required when you want to remove the app from a site collection app catalog.

When specifying site collection app catalog, you can specify the URL either with our without the _AppCatalog_ part, for example `https://contoso.sharepoint.com/sites/team-a/AppCatalog` or `https://contoso.sharepoint.com/sites/team-a`. CLI will accept both formats.

If the app with the specified ID doesn't exist in the app catalog, the command will fail with an error.



---

## app-retract

### Syntax
```
m365 spo app retract [options]
```

### Example
```
m365 spo app retract --id EXAMPLE-GUID-PLACEHOLDER

m365 spo app retract --id EXAMPLE-GUID-PLACEHOLDER --appCatalogUrl https://contoso.sharepoint.com/sites/apps

m365 spo app retract --id EXAMPLE-GUID-PLACEHOLDER --force

m365 spo app retract --id EXAMPLE-GUID-PLACEHOLDER --appCatalogScope sitecollection --appCatalogUrl https://contoso.sharepoint.com/sites/site1

```

### Remarks
When getting information about an app from the tenant app catalog, it's not necessary to specify the tenant app catalog URL. When the URL is not specified, the CLI will try to resolve the URL itself. Specifying the app catalog URL is required when you want to get information about an app from a site collection app catalog.

When specifying site collection app catalog, you can specify the URL either with our without the _AppCatalog_ part, for example `https://contoso.sharepoint.com/sites/team-a/AppCatalog` or `https://contoso.sharepoint.com/sites/team-a`. CLI will accept both formats.

If the app with the specified ID doesn't exist in the app catalog, the command will fail with an error.



---

## app-teamspackage-download

### Syntax
```
m365 spo app teamspackage download [options]
```

### Example
```
m365 spo app teamspackage download --appItemId 1

m365 spo app teamspackage download --appItemUniqueId EXAMPLE-GUID-PLACEHOLDER --fileName my-app.zip

m365 spo app teamspackage download --appName my-app.sppkg --appCatalogUrl https://contoso.sharepoint.com/sites/appcatalog

```

### Remarks
Download the Teams app package for an SPFx solution works only for solutions deployed to the tenant app catalog.

If you try to download Teams app package for an SPFx solution that doesn't support deployment to Teams, you'll get the _Request failed with status code 404_ error.

For maximum performance, specify the URL of the tenant app catalog, the item ID (`appItemId`) of the SPFx package for which you want to download the Teams app package and the name of the file where you want to save the downloaded package to (`fileName`).



---

## app-uninstall

### Syntax
```
m365 spo app uninstall [options]
```

### Example
```
m365 spo app uninstall --id EXAMPLE-GUID-PLACEHOLDER --siteUrl https://contoso.sharepoint.com

m365 spo app uninstall --id EXAMPLE-GUID-PLACEHOLDER --siteUrl https://contoso.sharepoint.com --force

m365 spo app uninstall --id EXAMPLE-GUID-PLACEHOLDER --siteUrl https://contoso.sharepoint.com --appCatalogScope sitecollection

```

### Remarks
If the app with the specified ID doesn't exist in the app catalog, the command will fail with an error.



---

## app-upgrade

### Syntax
```
m365 spo app upgrade [options]
```

### Example
```
m365 spo app upgrade --id EXAMPLE-GUID-PLACEHOLDER --siteUrl https://contoso.sharepoint.com

m365 spo app upgrade --id EXAMPLE-GUID-PLACEHOLDER --siteUrl https://contoso.sharepoint.com --appCatalogScope sitecollection

```

### Remarks
If the app with the specified ID doesn't exist in the app catalog, the command will fail with an error.



---

## cdn-get

### Syntax
```
m365 spo cdn get [options]
```

### Example
```
m365 spo cdn get

m365 spo cdn get --type Private

```

### Remarks
Using the `-t, --type` option you can choose whether you want to manage the settings of the Public (default) or Private CDN. If you don't use the option, the command will use the Public CDN.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## cdn-origin-add

### Syntax
```
m365 spo cdn origin add [options]
```

### Example
```
m365 spo cdn origin add --type Public --origin */CDN

```

### Remarks
Using the `-t, --type` option you can choose whether you want to manage the settings of the Public (default) or Private CDN. If you don't use the option, the command will use the Public CDN.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## cdn-origin-list

### Syntax
```
m365 spo cdn origin list [options]
```

### Example
```
m365 spo cdn origin list

m365 spo cdn origin list --type Private

```

### Remarks
Using the `-t, --type` option you can choose whether you want to manage the settings of the Public (default) or Private CDN. If you don't use the option, the command will use the Public CDN.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## cdn-origin-remove

### Syntax
```
m365 spo cdn origin remove [options]
```

### Example
```
m365 spo cdn origin remove --type Public --origin */CDN

```

### Remarks
Using the `-t, --type` option you can choose whether you want to manage the settings of the Public (default) or Private CDN. If you don't use the option, the command will use the Public CDN.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## cdn-policy-list

### Syntax
```
m365 spo cdn policy list [options]
```

### Example
```
m365 spo cdn policy list

m365 spo cdn policy list --cdnType Private

```

### Remarks
Using the `-t, --cdnType` option you can choose whether you want to manage the settings of the Public (default) or Private CDN. If you don't use the option, the command will use the Public CDN.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## cdn-policy-set

### Syntax
```
m365 spo cdn policy set [options]
```

### Example
```
m365 spo cdn policy set --cdnType Public --policy IncludeFileExtensions --value CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON

```

### Remarks
Using the `-t, --cdnType` option you can choose whether you want to manage the settings of the Public (default) or Private CDN. If you don't use the option, the command will use the Public CDN.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## cdn-set

### Syntax
```
m365 spo cdn set [options]
```

### Example
```
m365 spo cdn set --type Public --enabled true

m365 spo cdn set --type Public --enabled false

m365 spo cdn set --type Private --enabled true

m365 spo cdn set --type Both --enabled true

m365 spo cdn set --type Both --enabled true --noDefaultOrigins

```

### Remarks
Using the `-t, --type` option you can choose whether you want to manage the settings of the Public (default), Private CDN or both. If you don't use the option, the command will use the Public CDN.

Using the `-e, --enabled` option you can specify whether the given CDN type should be enabled or disabled. Use true to enable the specified CDN and false to disable it.

Using the `--noDefaultOrigins` option you can specify to skip the creation of the default origins.

:::info

To use this command you must be a Global or SharePoint administrator.

:::



---

## commandset-add

### Syntax
```
m365 spo commandset add [options]
```

### Example
```
m365 spo commandset add --title "Some customizer" --clientSideComponentId EXAMPLE-GUID-PLACEHOLDER --listType List --webUrl https://contoso.sharepoint.com/sites/sales

m365 spo commandset add --title "Some customizer" --clientSideComponentId EXAMPLE-GUID-PLACEHOLDER --clientSideComponentProperties '{ "someProperty": "Some value" }' --listType List --webUrl https://contoso.sharepoint.com/sites/sales

```

### Remarks
Running this command from the Windows Command Shell (cmd.exe) or PowerShell for Windows OS XP, 7, 8, 8.1 without bash installed might require additional formatting for command options that have JSON, XML, or JavaScript values because the command shell treats quotes differently. For example, this is how a ListView Command Set can be created from the Windows cmd.exe:

Note, how the clientSideComponentProperties option (-p) has escaped double quotes `'{\"testMessage\":\"Test message\"}'` compared to execution from bash `'{"testMessage":"Test message"}'`.

:::warning[Escaping JSON in PowerShell]

When using the `--clientSideComponentProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

This command can be used for configuring ListView Command Sets on a specific site. To configure a ListView Command Set tenant-wide, view our dedicated [spo tenant commandset add](../tenant/tenant-commandset-add.mdx) command.



---

## commandset-get

### Syntax
```
m365 spo commandset get [options]
```

### Example
```
m365 spo commandset get --title "Some customizer" --webUrl https://contoso.sharepoint.com/sites/sales```

### Remarks
If the command finds multiple command sets with the specified title, it will prompt you to disambiguate which command set it should use, listing the discovered IDs.

This command can be used for retrieving a ListView Command Set from a specific site. To retrieve a ListView Command Set that's installed tenant-wide, view our dedicated [spo tenant commandset get](../tenant/tenant-commandset-get.mdx) command.



---

## commandset-list

### Syntax
```
m365 spo commandset list [options]
```

### Example
```
m365 spo commandset list --webUrl https://contoso.sharepoint.com/sites/sales

```

### Remarks
This command can be used for retrieving a list of ListView Command Sets from a specific site. To retrieve a list of ListView Command Sets that are installed tenant-wide, view our dedicated [spo tenant commandset list](../tenant/tenant-commandset-list.mdx) command.



---

## commandset-remove

### Syntax
```
m365 spo commandset remove [options]
```

### Example
```
m365 spo commandset remove --title "Some customizer" --webUrl https://contoso.sharepoint.com/sites/sales

m365 spo commandset remove --id EXAMPLE-GUID-PLACEHOLDER --webUrl https://contoso.sharepoint.com/sites/sales

m365 spo commandset remove --clientSideComponentId EXAMPLE-GUID-PLACEHOLDER --webUrl https://contoso.sharepoint.com/sites/sales

```

### Remarks
This command can be used for removing a ListView Command Set from a specific site. To remove a ListView Command Set that's installed tenant-wide, view our dedicated [spo tenant commandset remove](../tenant/tenant-commandset-remove.mdx) command.



---

## commandset-set

### Syntax
```
m365 spo commandset set [options]
```

### Example
```
m365 spo commandset set --clientSideComponentId EXAMPLE-GUID-PLACEHOLDER --newTitle "Some new title" --location Both --webUrl https://contoso.sharepoint.com/sites/sales --scope Site```

### Remarks
Running this command from the Windows Command Shell (cmd.exe) or PowerShell for Windows OS XP, 7, 8, 8.1 without bash installed might require additional formatting for command options that have JSON, XML or JavaScript values because the command shell treats quotes differently. For example, this is how a ListView Command Set can be created from the Windows cmd.exe:

Note, how the clientSideComponentProperties option has escaped double quotes `'{\"testMessage\":\"Test message\"}'` compared to execution from bash `'{"testMessage":"Test message"}'`.

:::warning[Escaping JSON in PowerShell]

When using the `--clientSideComponentProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

This command can be used for updating a ListView Command Set on a specific site. To update a ListView Command Set that's installed tenant-wide, view our dedicated [spo tenant commandset set](../tenant/tenant-commandset-set.mdx) command.



---

## contenttype-add

### Syntax
```
m365 spo contenttype add [options]
```

### Example
```
m365 spo contenttype add --webUrl https://contoso.sharepoint.com/sites/contoso-sales --name 'PnP Alert' --id 0x01007926A45D687BA842B947286090B8F67D --group 'PnP Content Types'```

### Remarks
If the specified content type already exists, you will get a _A duplicate content type "Your Content Type" was found._ error.

The ID of the content type specifies the parent content type from which this content type inherits.



---

## contenttype-field-list

### Syntax
```
m365 spo contenttype field list [options]
```

### Example
```
m365 spo contenttype field list --webUrl https://contoso.sharepoint.com/sites/contoso-sales --contentTypeId "0x01"

m365 spo contenttype field list --webUrl https://contoso.sharepoint.com/sites/contoso-sales --contentTypeName "Document" --listTitle "Documents"

```

---

## contenttype-field-remove

### Syntax
```
m365 spo contenttype field remove [options]
```

### Example
```
m365 spo contenttype field remove --contentTypeId "0x0100CA0FA0F5DAEF784494B9C6020C3020A6" --id "EXAMPLE-GUID-PLACEHOLDER" --webUrl https://contoso.sharepoint.com --force```

---

## contenttype-field-set

### Syntax
```
m365 spo contenttype field set [options]
```

### Example
```
m365 spo contenttype field set --webUrl https://contoso.sharepoint.com/sites/portal --contentTypeId 0x01007926A45D687BA842B947286090B8F67D --id EXAMPLE-GUID-PLACEHOLDER```

### Remarks
If the field reference already exists, the command will update its _required_ and _hidden_ properties as specified in the command.



---

## contenttype-get

### Syntax
```
m365 spo contenttype get [options]
```

### Example
```
m365 spo contenttype get --webUrl https://contoso.sharepoint.com/sites/contoso-sales --id 0x0100558D85B7216F6A489A499DB361E1AE2F```

### Remarks
If no content type with the specified is found in the site or the list, you will get the _Content type with ID 0x010012 not found_ error.



---

## contenttypehub-get

### Syntax
```
m365 spo contenttypehub get [options]
```

### Example
```
m365 spo contenttypehub get

```

---

## contenttype-list

### Syntax
```
m365 spo contenttype list [options]
```

### Example
```
m365 spo contenttype list --webUrl "https://contoso.sharepoint.com/sites/contoso-sales"

m365 spo contenttype list --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --category "List Content Types"

```

---

## contenttype-remove

### Syntax
```
m365 spo contenttype remove [options]
```

### Example
```
m365 spo contenttype remove --id "0x01007926A45D687BA842B947286090B8F67D" --webUrl https://contoso.sharepoint.com

m365 spo contenttype remove --name "My Content Type" --webUrl https://contoso.sharepoint.com --force

m365 spo contenttype remove --name "My Content Type" --webUrl https://contoso.sharepoint.com --force

```

### Remarks
If the specified content type is in use by a list and cannot be removed, you will be returned the error: _Another site or list is still using this content type._ SharePoint will not allow a content type to be removed unless any dependent objects are also emptied from the recycle bin including the second-stage recycle bin.

The content type you wish to remove can be selected by the ID or Name of the content type. Either ID or Name parameter must be specified.



---

## contenttype-set

### Syntax
```
m365 spo contenttype set [options]
```

### Example
```
m365 spo contenttype set --id 0x001001 --webUrl https://contoso.sharepoint.com --Group "My group"```

### Remarks
:::warning[Updating child content types]

When specifying the `--updateChildren` flag, SharePoint will only propagate the changes that are made in the current request. If you want to know more about updating a content type and propagating changes to child content types, be sure to [read more here](https://learn.microsoft.com/previous-versions/office/developer/sharepoint-2010/ms442695(v=office.14)#EXAMPLE_SECRET_VALUE_PLACEHOLDER). 

:::



---

## contenttype-sync

### Syntax
```
m365 spo contenttype sync [options]
```

### Example
```
m365 spo contenttype sync —webUrl https://contoso.sharepoint.com/sites/sales --id 0x01007926A45D687BA842B947286090B8F67D

m365 spo contenttype sync —webUrl https://contoso.sharepoint.com/sites/sales --id 0x01007926A45D687BA842B947286090B8F67D --listTitle Contacts

```

---

## customaction-add

### Syntax
```
m365 spo customaction add [options]
```

### Example
```
m365 spo customaction add --webUrl https://contoso.sharepoint.com/sites/test --title "YourAppCustomizer" --name "YourName" --location "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --clientSideComponentId EXAMPLE-GUID-PLACEHOLDER --clientSideComponentProperties '{"testMessage":"Test message"}'```

### Remarks
Running this command from the Windows Command Shell (cmd.exe) or PowerShell for Windows OS XP, 7, 8, 8.1 without bash installed might require additional formatting for command options that have JSON, XML or JavaScript values because the command shell treats quotes differently. For example, this is how ApplicationCustomizer user custom action can be created from the Windows cmd.exe:

Note, how the clientSideComponentProperties option (-p) has escaped double quotes `'{\"testMessage\":\"Test message\"}'` compared to execution from bash `'{"testMessage":"Test message"}'`.

The `--rights` option accepts **case sensitive** values.

:::warning[Escaping JSON in PowerShell]

When using the `--clientSideComponentProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::



---

## customaction-clear

### Syntax
```
m365 spo customaction clear [options]
```

### Example
```
m365 spo customaction clear --webUrl https://contoso.sharepoint.com/sites/test --force

m365 spo customaction clear --webUrl https://contoso.sharepoint.com/sites/test --scope Web

m365 spo customaction clear --webUrl https://contoso.sharepoint.com/sites/test --scope Site

```

---

## customaction-get

### Syntax
```
m365 spo customaction get [options]
```

### Example
```
m365 spo customaction get --id EXAMPLE-GUID-PLACEHOLDER --webUrl https://contoso.sharepoint.com/sites/test```

### Remarks
If the command finds multiple user custom actions with the specified `title` or `clientSideComponentId`, it will prompt you to disambiguate which user custom action it should get, listing the discovered IDs.



---

## customaction-list

### Syntax
```
m365 spo customaction list [options]
```

### Example
```
m365 spo customaction list --webUrl https://contoso.sharepoint.com/sites/test

m365 spo customaction list --webUrl https://contoso.sharepoint.com/sites/test --scope Site

m365 spo customaction list --webUrl https://contoso.sharepoint.com/sites/test --scope Web

```

### Remarks
When using the text output type (default), the command lists only the values of the `Name`, `Location`, `Scope` and `Id` properties of the custom action. When setting the output type to JSON, all available properties are included in the command output.



---

## customaction-remove

### Syntax
```
m365 spo customaction remove [options]
```

### Example
```
m365 spo customaction remove --id EXAMPLE-GUID-PLACEHOLDER --webUrl https://contoso.sharepoint.com/sites/test```

### Remarks
If the command finds multiple user custom actions with the specified title, it will prompt you to disambiguate which user custom action it should use, listing the discovered IDs.



---

## customaction-set

### Syntax
```
m365 spo customaction set [options]
```

### Example
```
m365 spo customaction set --webUrl https://contoso.sharepoint.com/sites/test --id EXAMPLE-GUID-PLACEHOLDER --clientSideComponentProperties '{"testMessage":"Test message"}'```

### Remarks
Running this command from the Windows Command Shell (cmd.exe) or PowerShell for Windows OS XP, 7, 8, 8.1 without bash installed might require additional formatting for command options that have JSON, XML or JavaScript values because the command shell treats quotes differently. For example, this is how ApplicationCustomizer user custom action can be created from the Windows cmd.exe:

The `--rights` option accepts **case-sensitive** values.

Note, specifying the scope option might speed up the execution of the command, but would not update the scope. If the scope has to be changed, then the existing custom action should be removed and new should be added with different scope.

:::warning[Escaping JSON in PowerShell]

When using the `--clientSideComponentProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::



---

## eventreceiver-get

### Syntax
```
m365 spo eventreceiver get [options]
```

### Example
```
m365 spo eventreceiver get --webUrl https://contoso.sharepoint.com/sites/contoso-sales --name 'PnP Test Receiver'```

---

## eventreceiver-list

### Syntax
```
m365 spo eventreceiver list [options]
```

### Example
```
m365 spo eventreceiver list --webUrl https://contoso.sharepoint.com/sites/contoso-sales```

---

## eventreceiver-remove

### Syntax
```
m365 spo eventreceiver remove [options]
```

### Example
```
m365 spo eventreceiver remove --webUrl https://contoso.sharepoint.com/sites/contoso-sales --name 'PnP Test Receiver'```

### Remarks
:::warning

You can only remove an event receiver if it has been registered by an app with the same ID.

:::



---

## externaluser-list

### Syntax
```
m365 spo externaluser list [options]
```

### Example
```
m365 spo externaluser list --pageSize 50 --position 0

m365 spo externaluser list --pageSize 50 --position 0 --filter Vesa

m365 spo externaluser list --pageSize 50 --position 0 --siteUrl https://contoso.sharepoint.com

m365 spo externaluser list --pageSize 50 --position 0 --sortOrder desc

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## feature-disable

### Syntax
```
m365 spo feature disable [options]
```

### Example
```
m365 spo feature disable --webUrl https://contoso.sharepoint.com/sites/salis --id EXAMPLE-GUID-PLACEHOLDER --scope Site

m365 spo feature disable --webUrl https://contoso.sharepoint.com/sites/salis --id EXAMPLE-GUID-PLACEHOLDER --scope Web --force

```

### Remarks
If the specified url doesn't refer to an existing site collection, you will get a `"404 FILE NOT FOUND"` error.



---

## feature-enable

### Syntax
```
m365 spo feature enable [options]
```

### Example
```
m365 spo feature enable --webUrl https://contoso.sharepoint.com/sites/sales --id EXAMPLE-GUID-PLACEHOLDER --scope Site

m365 spo feature enable --webUrl https://contoso.sharepoint.com/sites/sales --id EXAMPLE-GUID-PLACEHOLDER --scope Web --force

```

### Remarks
If the specified url doesn't refer to an existing site collection, you will get a `"404 FILE NOT FOUND"` error.



---

## feature-list

### Syntax
```
m365 spo feature list [options]
```

### Example
```
m365 spo feature list --webUrl https://contoso.sharepoint.com/sites/test --scope Site

m365 spo feature list --webUrl https://contoso.sharepoint.com/sites/test --scope Web

```

---

## field-add

### Syntax
```
m365 spo field add [options]
```

### Example
```
m365 spo field add --webUrl https://contoso.sharepoint.com/sites/contoso-sales --xml '`<Field Type="DateTime" DisplayName="Start date-time" Required="FALSE" EnforceUniqueValues="FALSE" Indexed="FALSE" Format="DateTime" Group="PnP Columns" FriendlyDisplayFormat="Disabled" ID="{EXAMPLE-GUID-PLACEHOLDER}" SourceID="{EXAMPLE-GUID-PLACEHOLDER}" StaticName="PnPAlertStartDateTime" Name="PnPAlertStartDateTime"><Default>[today]</Default></Field>`'```

### Remarks
If the specified field already exists, you will get a _A duplicate field name "your-field" was found._ error.



---

## field-get

### Syntax
```
m365 spo field get [options]
```

### Example
```
m365 spo field get --webUrl https://contoso.sharepoint.com/sites/contoso-sales --id EXAMPLE-GUID-PLACEHOLDER```

---

## field-list

### Syntax
```
m365 spo field list [options]
```

### Example
```
m365 spo field list --webUrl https://contoso.sharepoint.com/sites/contoso-sales

m365 spo field list --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listTitle Events

m365 spo field list --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listId 'EXAMPLE-GUID-PLACEHOLDER'

m365 spo field list --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listUrl '/sites/contoso-sales/lists/Events'

```

---

## field-remove

### Syntax
```
m365 spo field remove [options]
```

### Example
```
m365 spo field remove --webUrl https://contoso.sharepoint.com/sites/contoso-sales --id EXAMPLE-GUID-PLACEHOLDER```

---

## field-set

### Syntax
```
m365 spo field set [options]
```

### Example
```
m365 spo field set --webUrl https://contoso.sharepoint.com/sites/project-x --internalName 'MyColumn' --updateExistingLists --Title 'My column'```

### Remarks
Specify properties to update using their names, eg. `--Title 'New Title' --JSLink jslink.js`.

:::warning[Escaping JSON in PowerShell]

When updating column formatting for a field with the `--CustomFormatter` option, it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::



---

## file-add

### Syntax
```
m365 spo file add [options]
```

### Example
```
m365 spo file add --webUrl https://contoso.sharepoint.com/sites/project-x --folder 'Shared Documents' --path 'C:\MS365.jpg'```

### Remarks
This command allows using unknown properties. Each property corresponds to the list item field that should be set when uploading the file.



---

## file-checkin

### Syntax
```
m365 spo file checkin [options]
```

### Example
```
m365 spo file checkin --webUrl https://contoso.sharepoint.com/sites/project-x --id 'EXAMPLE-GUID-PLACEHOLDER'```

---

## file-checkout

### Syntax
```
m365 spo file checkout [options]
```

### Example
```
m365 spo file checkout --webUrl https://contoso.sharepoint.com/sites/project-x --id 'EXAMPLE-GUID-PLACEHOLDER'

m365 spo file checkout --webUrl https://contoso.sharepoint.com/sites/project-x --url '/sites/project-x/documents/Test1.docx'

```

---

## file-checkout-undo

### Syntax
```
m365 spo file checkout undo [options]
```

### Example
```
m365 spo file checkout undo --webUrl https://contoso.sharepoint.com/sites/project-x --fileId 'EXAMPLE-GUID-PLACEHOLDER'

m365 spo file checkout undo --webUrl https://contoso.sharepoint.com/sites/project-x --fileUrl '/sites/project-x/documents/Test1.docx' --force

```

---

## file-copy

### Syntax
```
m365 spo file copy [options]
```

### Example
```
m365 spo file copy --webUrl https://contoso.sharepoint.com/sites/project --sourceUrl "/sites/project/Shared Documents/Document.pdf" --targetUrl "/sites/IT/Shared Documents"```

### Remarks
When you specify a value for `nameConflictBehavior`, consider the following:



---

## file-get

### Syntax
```
m365 spo file get [options]
```

### Example
```
m365 spo file get --webUrl https://contoso.sharepoint.com/sites/project-x --id 'EXAMPLE-GUID-PLACEHOLDER'```

---

## file-list

### Syntax
```
m365 spo file list [options]
```

### Example
```
m365 spo file list --webUrl https://contoso.sharepoint.com/sites/project-x --folderUrl 'Shared Documents'```

### Remarks
When the `fields` option includes values with a `/`, for example: `ListItemAllFields/Id`, an additional `$expand` query parameter will be included on `ListItemAllFields`.



---

## file-move

### Syntax
```
m365 spo file move [options]
```

### Example
```
m365 spo file move --webUrl https://contoso.sharepoint.com/sites/project-x --sourceUrl "/sites/project-x/Shared Documents/sp1.pdf" --targetUrl "/sites/project-y/Archived documents"```

### Remarks
When you specify a value for `nameConflictBehavior`, consider the following:



---

## file-remove

### Syntax
```
m365 spo file remove [options]
```

### Example
```
m365 spo file remove --webUrl https://contoso.sharepoint.com/sites/project-x --id EXAMPLE-GUID-PLACEHOLDER```

---

## file-rename

### Syntax
```
m365 spo file rename [options]
```

### Example
```
m365 spo file rename --webUrl https://contoso.sharepoint.com/sites/project-x --sourceUrl '/Shared Documents/Test1.docx' --targetFileName 'Test2.docx'

m365 spo file rename --webUrl https://contoso.sharepoint.com/sites/project-x --sourceUrl '/Shared Documents/Test1.docx' --targetFileName 'Test2.docx' --force

```

### Remarks
If you try to rename a file without the `--force` flag and a file with this name already exists, the operation will be cancelled.



---

## file-retentionlabel-ensure

### Syntax
```
m365 spo file retentionlabel ensure [options]
```

### Example
```
m365 spo file retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --fileUrl '/Shared Documents/Document.docx' --name 'Some label'

m365 spo file retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --fileId 'EXAMPLE-GUID-PLACEHOLDER' --name 'Some label'

m365 spo file retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --fileId 'EXAMPLE-GUID-PLACEHOLDER' --name 'Some label' --assetId 'XYZ'

```

### Remarks
You can also use [spo listitem retentionlabel remove](./../../../cmd/spo/listitem/listitem-retentionlabel-remove.mdx) for removing the retention label from a list item.

The `--assetId` option has to do with event-based retention. Event-based retention is about starting a retention period when a specific event occurs, instead of the moment a document was labeled or created.



---

## file-retentionlabel-remove

### Syntax
```
m365 spo file retentionlabel remove [options]
```

### Example
```
m365 spo file retentionlabel remove --webUrl https://contoso.sharepoint.com/sites/project-x --fileId EXAMPLE-GUID-PLACEHOLDER

m365 spo file retentionlabel remove --webUrl https://contoso.sharepoint.com/sites/project-x --fileUrl /sites/project-x/Shared Documents/Document.docx --id 1

```

---

## file-roleassignment-add

### Syntax
```
m365 spo file roleassignment add [options]
```

### Example
```
m365 spo file roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --fileId "EXAMPLE-GUID-PLACEHOLDER" --principalId 11 --roleDefinitionId 1073741829```

---

## file-roleassignment-remove

### Syntax
```
m365 spo file roleassignment remove [options]
```

### Example
```
m365 spo file roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --fileId "EXAMPLE-GUID-PLACEHOLDER" --principalId 2```

---

## file-roleinheritance-break

### Syntax
```
m365 spo file roleinheritance break [options]
```

### Example
```
m365 spo file roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --fileId "EXAMPLE-GUID-PLACEHOLDER"```

---

## file-roleinheritance-reset

### Syntax
```
m365 spo file roleinheritance reset [options]
```

### Example
```
m365 spo file roleinheritance reset --webUrl "https://contoso.sharepoint.com/sites/project-x" --fileId "EXAMPLE-GUID-PLACEHOLDER"

m365 spo file roleinheritance reset --webUrl "https://contoso.sharepoint.com/sites/project-x" --fileUrl "/sites/project-x/documents/Test1.docx" --force

```

---

## file-sharinginfo-get

### Syntax
```
m365 spo file sharinginfo get [options]
```

### Example
```
m365 spo file sharinginfo get --webUrl https://contoso.sharepoint.com/sites/project-x --fileUrl "/sites/M365CLI/Shared Documents/SharedFile.docx"

m365 spo file sharinginfo get --webUrl https://contoso.sharepoint.com/sites/project-x --fileId "EXAMPLE-GUID-PLACEHOLDER"

```

---

## file-sharinglink-add

### Syntax
```
m365 spo file sharinglink add [options]
```

### Example
```
m365 spo file sharinglink add --webUrl https://contoso.sharepoint.com --fileId EXAMPLE-GUID-PLACEHOLDER --type view

m365 spo file sharinglink add --webUrl https://contoso.sharepoint.com --fileUrl "/sites/demo/Shared Documents/Test1.docx" --type edit

m365 spo file sharinglink add --webUrl https://contoso.sharepoint.com --fileUrl "/sites/demo/Shared Documents/Test1.docx" --type edit --scope anonymous --expirationDateTime "2023-01-09T16:20:00Z"

```

---

## file-sharinglink-clear

### Syntax
```
m365 spo file sharinglink clear [options]
```

### Example
```
m365 spo file sharinglink clear --webUrl https://contoso.sharepoint.com/sites/demo --fileId EXAMPLE-GUID-PLACEHOLDER --force

m365 spo file sharinglink clear --webUrl https://contoso.sharepoint.com/sites/demo --fileUrl '/sites/demo/Shared Documents/document.docx' --scope anonymous

```

---

## file-sharinglink-get

### Syntax
```
m365 spo file sharinglink get [options]
```

### Example
```
m365 spo file sharinglink get --webUrl 'https://contoso.sharepoint.com/sites/demo' --fileId EXAMPLE-GUID-PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER```

---

## file-sharinglink-list

### Syntax
```
m365 spo file sharinglink list [options]
```

### Example
```
m365 spo file sharinglink list --webUrl https://contoso.sharepoint.com/sites/demo --fileId EXAMPLE-GUID-PLACEHOLDER

m365 spo file sharinglink list --webUrl https://contoso.sharepoint.com/sites/demo --fileUrl "/sites/demo/shared documents/document.docx"

m365 spo file sharinglink list --webUrl https://contoso.sharepoint.com/sites/demo --fileUrl "/sites/demo/shared documents/document.docx" --scope anonymous

```

---

## file-sharinglink-remove

### Syntax
```
m365 spo file sharinglink remove [options]
```

### Example
```
m365 spo file sharinglink remove --webUrl https://contoso.sharepoint.com/sites/demo --fileId EXAMPLE-GUID-PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER --force```

---

## file-sharinglink-set

### Syntax
```
m365 spo file sharinglink set [options]
```

### Example
```
m365 spo file sharinglink set --webUrl https://contoso.sharepoint.com --fileUrl "/sites/demo/Shared Documents/Document.docx" --id EXAMPLE-GUID-PLACEHOLDER --expirationDateTime "2023-01-09T16:57:00.000Z"

m365 spo file sharinglink set --webUrl https://contoso.sharepoint.com --fileId EXAMPLE-GUID-PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER --expirationDateTime "2023-01-09T16:57:00.000Z"

```

---

## file-version-clear

### Syntax
```
m365 spo file version clear [options]
```

### Example
```
m365 spo file version clear --webUrl https://contoso.sharepoint.com --fileId 'EXAMPLE-GUID-PLACEHOLDER'

m365 spo file version clear --webUrl https://contoso.sharepoint.com --fileUrl '/Shared Documents/Document.docx'

m365 spo file version clear --webUrl https://contoso.sharepoint.com --fileId 'EXAMPLE-GUID-PLACEHOLDER' --force

m365 spo file version clear --webUrl https://contoso.sharepoint.com --fileUrl '/Shared Documents/Document.docx' --force

```

---

## file-version-get

### Syntax
```
m365 spo file version get [options]
```

### Example
```
m365 spo file version get --webUrl https://contoso.sharepoint.com --label "1.0" --fileId 'EXAMPLE-GUID-PLACEHOLDER'

m365 spo file version get --webUrl https://contoso.sharepoint.com --label "1.0" --fileUrl '/Shared Documents/Document.docx'

```

---

## file-version-list

### Syntax
```
m365 spo file version list [options]
```

### Example
```
m365 spo file version list --webUrl https://contoso.sharepoint.com --fileId 'EXAMPLE-GUID-PLACEHOLDER'

m365 spo file version list --webUrl https://contoso.sharepoint.com --fileUrl '/Shared Documents/Document.docx'

m365 spo file version list --webUrl https://contoso.sharepoint.com/sites/project-x --fileUrl '/sites/project-x/Shared Documents/Document.docx'

```

---

## file-version-remove

### Syntax
```
m365 spo file version remove [options]
```

### Example
```
m365 spo file version remove --webUrl https://contoso.sharepoint.com --label "1.0" --fileId 'EXAMPLE-GUID-PLACEHOLDER'```

---

## file-version-restore

### Syntax
```
m365 spo file version restore [options]
```

### Example
```
m365 spo file version restore --webUrl https://contoso.sharepoint.com --label "1.0" --fileId 'EXAMPLE-GUID-PLACEHOLDER'```

---

## folder-add

### Syntax
```
m365 spo folder add [options]
```

### Example
```
m365 spo folder add --webUrl https://contoso.sharepoint.com/sites/project-x --parentFolderUrl '/Shared Documents' --name 'My Folder Name'```

### Remarks
When you specify a value for `color`, consider the following:



---

## folder-copy

### Syntax
```
m365 spo folder copy [options]
```

### Example
```
m365 spo folder copy --webUrl https://contoso.sharepoint.com/sites/project-x --sourceUrl "/sites/project-x/Shared Documents/Reports" --targetUrl "/sites/project-y/Shared Documents/Project files"```

### Remarks
When you specify a value for `nameConflictBehavior`, consider the following:



---

## folder-get

### Syntax
```
m365 spo folder get [options]
```

### Example
```
m365 spo folder get --webUrl https://contoso.sharepoint.com/sites/project-x --url "/Shared Documents"

m365 spo folder get --webUrl https://contoso.sharepoint.com/sites/project-x --id "EXAMPLE-GUID-PLACEHOLDER"

m365 spo folder get --webUrl https://contoso.sharepoint.com/sites/test --url "/sites/test/Shared Documents/Test1" --withPermissions

```

### Remarks
If no folder exists at the specified URL, you will get a `Please check the folder URL. Folder might not exist on the specified URL` error.

If root level folder is passed, you will get a `Please ensure the specified folder URL or folder Id does not refer to a root folder. Use \'spo list get\' with withPermissions instead' error.` Please use the command 'spo list get'.



---

## folder-list

### Syntax
```
m365 spo folder list [options]
```

### Example
```
m365 spo folder list --webUrl https://contoso.sharepoint.com/sites/project-x --parentFolderUrl '/Shared Documents'

m365 spo folder list --webUrl https://contoso.sharepoint.com/sites/project-x --parentFolderUrl '/sites/project-x/Shared Documents' --recursive

m365 spo folder list --webUrl https://contoso.sharepoint.com/sites/project-x --parentFolderUrl '/Shared Documents' --fields ListItemAllFields/Id --filter "startswith(Name,'Folder')"

```

---

## folder-move

### Syntax
```
m365 spo folder move [options]
```

### Example
```
m365 spo folder move --webUrl https://contoso.sharepoint.com/sites/project-x --sourceUrl "/sites/project-x/Shared Documents/Reports" --targetUrl "/sites/project-y/Shared Documents/Reports January"```

### Remarks
When you specify a value for `nameConflictBehavior`, consider the following:



---

## folder-remove

### Syntax
```
m365 spo folder remove [options]
```

### Example
```
m365 spo folder remove --webUrl https://contoso.sharepoint.com/sites/project-x --url '/Shared Documents/My Folder'

m365 spo folder remove --webUrl https://contoso.sharepoint.com/sites/project-x --url '/sites/project-x/Shared Documents/My Folder' --recycle

```

### Remarks
The `spo folder remove` command will remove folder only if it is empty. If the folder contains any files, deleting the folder will fail.



---

## folder-retentionlabel-ensure

### Syntax
```
m365 spo folder retentionlabel ensure [options]
```

### Example
```
m365 spo folder retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --folderUrl '/Shared Documents' --name 'Some label'

m365 spo folder retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --folderId 'EXAMPLE-GUID-PLACEHOLDER'  --name 'Some label'

```

### Remarks
You can also use [spo listitem retentionlabel remove](./../../../cmd/spo/listitem/listitem-retentionlabel-remove.mdx) for removing the retention label from a list item.



---

## folder-retentionlabel-remove

### Syntax
```
m365 spo folder retentionlabel remove [options]
```

### Example
```
m365 spo folder retentionlabel remove --webUrl https://contoso.sharepoint.com/sites/project-x --folderId EXAMPLE-GUID-PLACEHOLDER

m365 spo folder retentionlabel remove --webUrl https://contoso.sharepoint.com/sites/project-x --folderUrl /sites/project-x/Shared Documents/Folder --id 1

```

---

## folder-roleassignment-add

### Syntax
```
m365 spo folder roleassignment add [options]
```

### Example
```
m365 spo folder roleassignment add --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --folderUrl  "/Shared Documents/FolderPermission" --groupName "saleGroup" --roleDefinitionName "Edit"```

---

## folder-roleassignment-remove

### Syntax
```
m365 spo folder roleassignment remove [options]
```

### Example
```
m365 spo folder roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --folderUrl  "/Shared Documents/FolderPermission" --groupName "saleGroup"```

---

## folder-roleinheritance-break

### Syntax
```
m365 spo folder roleinheritance break [options]
```

### Example
```
m365 spo folder roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --folderUrl "Shared Documents/TestFolder"```

---

## folder-roleinheritance-reset

### Syntax
```
m365 spo folder roleinheritance reset [options]
```

### Example
```
m365 spo folder roleinheritance reset --webUrl "https://contoso.sharepoint.com/sites/project-x" --folderUrl "Shared Documents/TestFolder"

m365 spo folder roleinheritance reset --webUrl "https://contoso.sharepoint.com/sites/project-x" --folderUrl "/sites/project-x/Shared Documents/TestFolder" --force

m365 spo folder roleinheritance reset --webUrl "https://contoso.sharepoint.com/sites/project-x" --folderUrl "/sites/project-x/Shared Documents" --force

```

---

## folder-set

### Syntax
```
m365 spo folder set [options]
```

### Example
```
m365 spo folder set --webUrl https://contoso.sharepoint.com/sites/project-x --url '/Shared Documents/My Folder 1' --name 'My Folder 2'```

### Remarks
When you specify a value for `color`, consider the following:



---

## folder-sharinglink-add

### Syntax
```
m365 spo folder sharinglink add [options]
```

### Example
```
m365 spo folder sharinglink add --webUrl https://contoso.sharepoint.com/sites/demo --folderId EXAMPLE-GUID-PLACEHOLDER --type view --scope anonymous```

---

## folder-sharinglink-clear

### Syntax
```
m365 spo folder sharinglink clear [options]
```

### Example
```
m365 spo folder sharinglink clear --webUrl https://contoso.sharepoint.com/sites/demo --folderId EXAMPLE-GUID-PLACEHOLDER --force

m365 spo folder sharinglink clear --webUrl https://contoso.sharepoint.com/sites/demo --folderUrl '/sites/demo/Shared Documents/folder1' --scope anonymous

```

---

## folder-sharinglink-get

### Syntax
```
m365 spo folder sharinglink get [options]
```

### Example
```
m365 spo folder sharinglink get --webUrl https://contoso.sharepoint.com/sites/demo --id EXAMPLE-GUID-PLACEHOLDER --folderId EXAMPLE-GUID-PLACEHOLDER

m365 spo folder sharinglink get --webUrl https://contoso.sharepoint.com/sites/demo --id EXAMPLE-GUID-PLACEHOLDER --folderUrl "/sites/demo/shared documents/folder"

```

---

## folder-sharinglink-list

### Syntax
```
m365 spo folder sharinglink list [options]
```

### Example
```
m365 spo folder sharinglink list --webUrl https://contoso.sharepoint.com/sites/demo --folderId EXAMPLE-GUID-PLACEHOLDER

m365 spo folder sharinglink list --webUrl https://contoso.sharepoint.com/sites/demo --folderUrl "/sites/demo/shared documents/folder"

m365 spo folder sharinglink list --webUrl https://contoso.sharepoint.com/sites/demo --folderUrl "/sites/demo/shared documents/folder" --scope anonymous

```

---

## folder-sharinglink-remove

### Syntax
```
m365 spo folder sharinglink remove [options]
```

### Example
```
m365 spo folder sharinglink remove --webUrl https://contoso.sharepoint.com/sites/demo --folderId EXAMPLE-GUID-PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER --force

m365 spo folder sharinglink remove --webUrl https://contoso.sharepoint.com/sites/demo --folderUrl /sites/demo/shared%20documents/Folder --id EXAMPLE-GUID-PLACEHOLDER

```

---

## folder-sharinglink-set

### Syntax
```
m365 spo folder sharinglink set [options]
```

### Example
```
m365 spo folder sharinglink set --webUrl https://contoso.sharepoint.com/sites/demo --folderId EXAMPLE-GUID-PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER --expirationDateTime '2022-11-30T00:00:00Z'

m365 spo folder sharinglink set --webUrl https://contoso.sharepoint.com/sites/demo --folderUrl /sites/demo/shared%20documents/Folder --id EXAMPLE-GUID-PLACEHOLDER --expirationDateTime '2022-11-30T00:00:00Z'

```

---

## group-add

### Syntax
```
m365 spo group add [options]
```

### Example
```
m365 spo group add --webUrl https://contoso.sharepoint.com/sites/project-x --name "Project leaders" --description "This group contains all project leaders"

m365 spo group add --webUrl https://contoso.sharepoint.com/sites/project-x --name "Project leaders" --allowRequestToJoinLeave true --requestToJoinLeaveEmailSetting john.doe@contoso.com

```

---

## group-get

### Syntax
```
m365 spo group get [options]
```

### Example
```
m365 spo group get --webUrl https://contoso.sharepoint.com/sites/project-x --id 7

m365 spo group get --webUrl https://contoso.sharepoint.com/sites/project-x --name "Team Site Members"

m365 spo group get --webUrl https://contoso.sharepoint.com/sites/project-x --associatedGroup Owner

```

---

## group-list

### Syntax
```
m365 spo group list [options]
```

### Example
```
m365 spo group list --webUrl "https://contoso.sharepoint.com/sites/contoso"

m365 spo group list --webUrl "https://contoso.sharepoint.com/sites/contoso" --associatedGroupsOnly

```

---

## group-member-add

### Syntax
```
m365 spo group member add [options]
```

### Example
```
m365 spo group member add --webUrl https://contoso.sharepoint.com/sites/SiteA --groupId 5 --userNames "Alex.Wilber@contoso.com"```

### Remarks
For the `userIds`, `userNames`, `emails`, `entraGroupIds`, or `entraGroupNames` options you can specify multiple values by separating them with a comma. If one of the specified entries is not valid, the command will fail with an error message showing the list of invalid values.



---

## group-member-list

### Syntax
```
m365 spo group member list [options]
```

### Example
```
m365 spo group member list --webUrl https://contoso.sharepoint.com/sites/SiteA --groupId 5

m365 spo group member list --webUrl https://contoso.sharepoint.com/sites/SiteA --groupName "Contoso Site Members"

```

---

## group-member-remove

### Syntax
```
m365 spo group member remove [options]
```

### Example
```
m365 spo group member remove --webUrl https://contoso.sharepoint.com/sites/SiteA --groupId 5 --userName "Alex.Wilber@contoso.com"```

---

## group-remove

### Syntax
```
m365 spo group remove [options]
```

### Example
```
m365 spo group remove --webUrl https://contoso.sharepoint.com/sites/mysite --id 5

m365 spo group remove --webUrl https://contoso.sharepoint.com/sites/mysite --name "Team Site Owners"

```

---

## group-set

### Syntax
```
m365 spo group set [options]
```

### Example
```
m365 spo group set --webUrl https://contoso.sharepoint.com/sites/project-x --id 18 --newName "Project leaders" --description "This group contains all project leaders"

m365 spo group set --webUrl https://contoso.sharepoint.com/sites/project-x --name "Project leaders" --allowRequestToJoinLeave true --requestToJoinLeaveEmailSetting john.doe@contoso.com

m365 spo group set --webUrl https://contoso.sharepoint.com/sites/project-x --id 18 --ownerEmail john.doe@contoso.com

```

---

## hidedefaultthemes-get

### Syntax
```
m365 spo hidedefaultthemes get [options]
```

### Example
```
m365 spo hidedefaultthemes get

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## hidedefaultthemes-set

### Syntax
```
m365 spo hidedefaultthemes set [options]
```

### Example
```
m365 spo hidedefaultthemes set --hideDefaultThemes true

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## homesite-add

### Syntax
```
m365 spo homesite add [options]
```

### Example
```
m365 spo homesite add --url "https://contoso.sharepoint.com/sites/testcomms"

m365 spo homesite add --url "https://contoso.sharepoint.com/sites/testcomms" --isInDraftMode true --vivaConnectionsDefaultStart false --audiences "EXAMPLE-GUID-PLACEHOLDER,EXAMPLE-GUID-PLACEHOLDER" --order 2 

```

---

## homesite-get

### Syntax
```
m365 spo homesite get [options]
```

### Example
```
m365 spo homesite get

```

---

## homesite-list

### Syntax
```
m365 spo homesite list [options]
```

### Example
```
m365 spo homesite list

```

---

## homesite-remove

### Syntax
```
m365 spo homesite remove [options]
```

### Example
```
m365 spo homesite remove --force

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## homesite-set

### Syntax
```
m365 spo homesite set [options]
```

### Example
```
m365 spo homesite set --siteUrl https://contoso.sharepoint.com/sites/comms

m365 spo homesite set --siteUrl https://contoso.sharepoint.com/sites/comms --vivaConnectionsDefaultStart true

m365 spo homesite set --siteUrl https://contoso.sharepoint.com/sites/comms --vivaConnectionsDefaultStart false

```

### Remarks
:::info

To use this command you must be a Global or SharePoint administrator.

:::



---

## hubsite-connect

### Syntax
```
m365 spo hubsite connect [options]
```

### Example
```
m365 spo hubsite connect --id EXAMPLE-GUID-PLACEHOLDER --parentId EXAMPLE-GUID-PLACEHOLDER

m365 spo hubsite connect --url https://contoso.sharepoint.com/sites/project-x --parentUrl https://contoso.sharepoint.com/sites/projects

m365 spo hubsite connect --title "My hub site" --parentId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::info

To use this command you must be a Global or SharePoint administrator.

:::

To connect a regular site to a hub site, use command [spo site hubsite connect](../site/site-hubsite-connect.mdx).



---

## hubsite-data-get

### Syntax
```
m365 spo hubsite data get [options]
```

### Example
```
m365 spo hubsite data get --webUrl https://contoso.sharepoint.com/sites/project-x

```

### Remarks
By default, the hub site data is returned from the server's cache. To refresh the data with the latest updates, use the `--forceRefresh` option. Use this option, if you just made changes and need to see them right away.

If the specified site is not connected to a hub site site and is not a hub site itself, no data will be retrieved.



---

## hubsite-disconnect

### Syntax
```
m365 spo hubsite disconnect [options]
```

### Example
```
m365 spo hubsite disconnect --id EXAMPLE-GUID-PLACEHOLDER

m365 spo hubsite disconnect --url https://contoso.sharepoint.com/sites/project-x

m365 spo hubsite disconnect --title "My hub site"

```

### Remarks
:::info

To use this command you must be a Global or SharePoint administrator.

:::

To disconnect a regular site from a hub site, use command [spo site hubsite disconnect](../site/site-hubsite-disconnect.mdx).

If the specified id doesn't point to a valid hub site, you will get a ResourceNotFoundException error.



---

## hubsite-get

### Syntax
```
m365 spo hubsite get [options]
```

### Example
```
m365 spo hubsite get --id EXAMPLE-GUID-PLACEHOLDER

m365 spo hubsite get --title 'My Hub Site'

m365 spo hubsite get --url 'https://contoso.sharepoint.com/sites/HubSite'

m365 spo hubsite get --id EXAMPLE-GUID-PLACEHOLDER --includeAssociatedSites --output json

```

---

## hubsite-list

### Syntax
```
m365 spo hubsite list [options]
```

### Example
```
m365 spo hubsite list

m365 spo hubsite list --includeAssociatedSites --output json

```

### Remarks
When using the text or csv output type, the command lists only the values of the `ID`, `SiteUrl` and `Title` properties of the hub site. With the output type as JSON, all available properties are included in the command output.



---

## hubsite-register

### Syntax
```
m365 spo hubsite register [options]
```

### Example
```
m365 spo hubsite register --siteUrl https://contoso.sharepoint.com/sites/sales

```

### Remarks
:::info

To use this command you must be a Global or SharePoint administrator.

:::

If the specified site collection is already registered as a hub site, you will get a `This site is already a HubSite.` error.



---

## hubsite-rights-grant

### Syntax
```
m365 spo hubsite rights grant [options]
```

### Example
```
m365 spo hubsite rights grant --hubSiteUrl https://contoso.sharepoint.com/sites/sales --principals PattiF --rights Join

m365 spo hubsite rights grant --hubSiteUrl https://contoso.sharepoint.com/sites/sales --principals "PattiF,AdeleV" --rights Join

m365 spo hubsite rights grant --hubSiteUrl https://contoso.sharepoint.com/sites/sales --principals PattiF@contoso.com --rights Join

```

### Remarks
:::info

To use this command you must be a Global or SharePoint administrator.

:::



---

## hubsite-rights-revoke

### Syntax
```
m365 spo hubsite rights revoke [options]
```

### Example
```
m365 spo hubsite rights revoke --hubSiteUrl https://contoso.sharepoint.com/sites/sales --principals PattiF

m365 spo hubsite rights revoke --hubSiteUrl https://contoso.sharepoint.com/sites/sales --principals "PattiF,AdeleV" --force

```

### Remarks
:::info

To use this command you must be a Global or SharePoint administrator.

:::



---

## hubsite-set

### Syntax
```
m365 spo hubsite set [options]
```

### Example
```
m365 spo hubsite set --id EXAMPLE-GUID-PLACEHOLDER --title Sales

m365 spo hubsite set --id EXAMPLE-GUID-PLACEHOLDER --title Sales --description "All things sales"

```

### Remarks
:::info

To use this command you must be a Global or SharePoint administrator.

:::

If the specified `id` doesn't refer to an existing hub site, you will get an `Unknown Error` error.



---

## hubsite-unregister

### Syntax
```
m365 spo hubsite unregister [options]
```

### Example
```
m365 spo hubsite unregister --url https://contoso.sharepoint.com/sites/sales

m365 spo hubsite unregister --url https://contoso.sharepoint.com/sites/sales --force

```

### Remarks
:::info

To use this command you must be a Global or SharePoint administrator.

:::

If the specified site collection is not registered as a hub site, you will get a `hubSiteId` error.



---

## knowledgehub-get

### Syntax
```
m365 spo knowledgehub get [options]
```

### Example
```
m365 spo knowledgehub get

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## knowledgehub-remove

### Syntax
```
m365 spo knowledgehub remove [options]
```

### Example
```
m365 spo knowledgehub remove

m365 spo knowledgehub remove --force

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## knowledgehub-set

### Syntax
```
m365 spo knowledgehub set [options]
```

### Example
```
m365 spo knowledgehub set --siteUrl https://contoso.sharepoint.com/sites/knowledgesite

```

### Remarks
If the specified url doesn't refer to an existing site collection, you will get a `404 - "404 FILE NOT FOUND"` error.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## list-add

### Syntax
```
m365 spo list add [options]
```

### Example
```
m365 spo list add --title Announcements --baseTemplate Announcements --webUrl https://contoso.sharepoint.com/sites/project-x

m365 spo list add --webUrl https://contoso.sharepoint.com/sites/project-x --title Announcements --baseTemplate Announcements --contentTypesEnabled true --enableVersioning true --majorVersionLimit 50

```

---

## list-contenttype-add

### Syntax
```
m365 spo list contenttype add [options]
```

### Example
```
m365 spo list contenttype add --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER --id 0x0120

m365 spo list contenttype add --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle Documents --id 0x0120

m365 spo list contenttype add --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl 'sites/project-x/Documents' --id 0x0120

```

---

## list-contenttype-default-set

### Syntax
```
m365 spo list contenttype default set [options]
```

### Example
```
m365 spo list contenttype default set --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER --contentTypeId 0x0120

m365 spo list contenttype default set --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle Documents --contentTypeId 0x0120

m365 spo list contenttype default set --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl 'sites/project-x/Documents' --contentTypeId 0x0120

```

---

## list-contenttype-list

### Syntax
```
m365 spo list contenttype list [options]
```

### Example
```
m365 spo list contenttype list --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER

m365 spo list contenttype list --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle Documents

m365 spo list contenttype list --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl 'sites/project-x/Documents'

```

---

## list-contenttype-remove

### Syntax
```
m365 spo list contenttype remove [options]
```

### Example
```
m365 spo list contenttype remove --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER --id EXAMPLE_SECRET_VALUE_PLACEHOLDER

m365 spo list contenttype remove --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle Documents --id EXAMPLE_SECRET_VALUE_PLACEHOLDER

m365 spo list contenttype remove --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl 'sites/project-x/Documents' --id EXAMPLE_SECRET_VALUE_PLACEHOLDER --force

```

---

## list-defaultvalue-clear

### Syntax
```
m365 spo list defaultvalue clear [options]
```

### Example
```
m365 spo list defaultvalue clear --webUrl https://contoso.sharepoint.com/sites/Marketing --listTitle Logos

m365 spo list defaultvalue clear --webUrl https://contoso.sharepoint.com/sites/Marketing --listTitle Logos --field Company

m365 spo list defaultvalue clear --webUrl https://contoso.sharepoint.com/sites/Marketing --listTitle Logos --folderUrl "/sites/Marketing/Logos/Contoso"

```

---

## list-defaultvalue-list

### Syntax
```
m365 spo list defaultvalue list [options]
```

### Example
```
m365 spo list defaultvalue list --webUrl https://contoso.sharepoint.com/sites/marketing --listTitle "Project Documents"```

---

## list-defaultvalue-remove

### Syntax
```
m365 spo list defaultvalue remove [options]
```

### Example
```
m365 spo list defaultvalue remove --webUrl https://contoso.sharepoint.com/sites/Marketing --listTitle Logos --fieldName Company

m365 spo list defaultvalue remove --webUrl https://contoso.sharepoint.com/sites/Marketing --listUrl '/Logos' --fieldName Company --folderUrl '/Logos/Branding'

m365 spo list defaultvalue remove --webUrl https://contoso.sharepoint.com/sites/Marketing --listId EXAMPLE-GUID-PLACEHOLDER --field Company --folderUrl '/sites/Marketing/Logos/Branding'

```

---

## list-defaultvalue-set

### Syntax
```
m365 spo list defaultvalue set [options]
```

### Example
```
m365 spo list defaultvalue set --webUrl https://contoso.sharepoint.com/sites/Marketing --listTitle Logos --fieldName Company --fieldValue Contoso```

### Remarks
:::note

Due to limitations in SharePoint Online, setting default column values for folders with a `#` or `%` character in their path is not supported.

:::



---

## list-get

### Syntax
```
m365 spo list get [options]
```

### Example
```
m365 spo list get --webUrl https://contoso.sharepoint.com/sites/project-x --default  ```

### Remarks
When the `properties` option includes values with a `/`, for example: `ListItemAllFields/Id`, an additional `$expand` query parameter will be included on `ListItemAllFields`.



---

## listitem-add

### Syntax
```
m365 spo listitem add [options]
```

### Example
```
m365 spo listitem add --contentType Item --listTitle "Demo List" --webUrl https://contoso.sharepoint.com/sites/project-x --Title "Demo Item"```

### Remarks
:::warning[When using DateTime fields]

When creating a list item with a DateTime field, use the timezone and the format that the site expects, based on its regional settings. Alternatively, a format which works on all regions is the following: `yyyy-MM-dd HH:mm:ss`. However, you should use the local timezone in all situations. UTC date/time or ISO 8601 formatted date/time is not supported.

:::



---

## listitem-attachment-add

### Syntax
```
m365 spo listitem attachment add [options]
```

### Example
```
m365 spo listitem attachment add --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "DemoList" --listItemId 147 --filePath "C:/Reports/File1.jpg"

m365 spo listitem attachment add --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl "/sites/project-x/Lists/DemoList" --listItemId 147 --filePath "C:/Reports/File1.jpg" --fileName "File2"

```

---

## listitem-attachment-get

### Syntax
```
m365 spo listitem attachment get [options]
```

### Example
```
m365 spo listitem attachment get --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Demo List" --listItemId 147 --fileName "File1.jpg"

m365 spo listitem attachment get --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl "/sites/project-x/Lists/DemoList" --listItemId 147 --fileName "File1.jpg"

```

---

## listitem-attachment-list

### Syntax
```
m365 spo listitem attachment list [options]
```

### Example
```
m365 spo listitem attachment list --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Demo List" --listItemId 147

m365 spo listitem attachment list --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER --listItemId 147

m365 spo listitem attachment list --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl /sites/project-x/Documents --listItemId 147

```

---

## listitem-attachment-remove

### Syntax
```
m365 spo listitem attachment remove [options]
```

### Example
```
m365 spo listitem attachment remove --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Demo List" --listItemId 147 --fileName "File1.jpg"

m365 spo listitem attachment remove --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl "/sites/project-x/Lists/DemoList" --listItemId 147 --fileName "File1.jpg"

```

---

## listitem-attachment-set

### Syntax
```
m365 spo listitem attachment set [options]
```

### Example
```
m365 spo listitem attachment set --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Demo List" --listItemId 147 --fileName "File1.jpg" --filePath "C:/Reports/File2.jpg"

m365 spo listitem attachment set --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl "/sites/project-x/Lists/DemoList" --listItemId 147 --fileName "File1.jpg" --filePath "C:/Reports/File2.jpg"

```

---

## listitem-batch-add

### Syntax
```
m365 spo listitem batch add [options]
```

### Example
```
m365 spo listitem batch add --filePath "C:\Path\To\Csv\CsvFile.csv" --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Demo List"```

### Remarks
A sample CSV can be found below. The first line of the CSV-file should contain the internal column names that you wish to set.

:::warning[When using DateTime fields]

When creating list items with a DateTime field, use the timezone and the format that the site expects, based on its regional settings. Alternatively, a format which works on all regions is the following: `yyyy-MM-dd HH:mm:ss`. However, you should use the local timezone in all situations. UTC date/time or ISO 8601 formatted date/time is not supported.

:::



---

## listitem-batch-remove

### Syntax
```
m365 spo listitem batch remove [options]
```

### Example
```
m365 spo listitem batch remove --filePath ./IDlist.csv --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Demo List"

m365 spo listitem batch remove --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Demo List" --ids "123,234,345"

```

### Remarks
A sample CSV can be found below. The first line of the CSV-file should contain the internal column name of the ID-column.



---

## listitem-batch-set

### Syntax
```
m365 spo listitem batch set [options]
```

### Example
```
m365 spo listitem batch set --filePath "C:\Path\To\Csv\CsvFile.csv" --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Demo List"```

### Remarks
A sample CSV can be found below. The first line of the CSV-file should contain the internal column names that you wish to set.



---

## listitem-get

### Syntax
```
m365 spo listitem get [options]
```

### Example
```
m365 spo listitem get --listTitle "Demo List" --id 147 --webUrl https://contoso.sharepoint.com/sites/project-x```

### Remarks
If you want to specify a lookup type in the `properties` option, define which columns from the related list should be returned.



---

## listitem-isrecord

### Syntax
```
m365 spo listitem isrecord [options]
```

### Example
```
m365 spo listitem isrecord --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'Documents' --id 1

m365 spo listitem isrecord --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER --id 1

m365 spo listitem isrecord --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl /sites/project-x/documents --id 1

```

---

## listitem-list

### Syntax
```
m365 spo listitem list [options]
```

### Example
```
m365 spo listitem list --listTitle "Demo List" --webUrl https://contoso.sharepoint.com/sites/project-x```

### Remarks
This command retrieves all items in the list, even if there are more than 5000. Use the `pageSize` and `pageNumber` options if you only want a specific amount of items. When using a CAML query, include a `RowLimit`-node to get all items. If you run into list view threshold exceptions, remove any Query-conditions or filters and also include a `RowLimit`-node.

`pageNumber` is specified as a 0-based index. A value of `2` returns the third page of items.

If you want to specify a lookup type in the `properties` option, define which columns from the related list should be returned.



---

## listitem-record-declare

### Syntax
```
m365 spo listitem record declare [options]
```

### Example
```
m365 spo listitem record declare --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Demo List" --listItemId 1```

---

## listitem-record-lock

### Syntax
```
m365 spo listitem record lock [options]
```

### Example
```
m365 spo listitem record lock --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER --listItemId 1

m365 spo listitem record lock --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'List 1' --listItemId 1

m365 spo listitem record lock --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl /sites/project-x/lists/TestList --listItemId 1

```

---

## listitem-record-undeclare

### Syntax
```
m365 spo listitem record undeclare [options]
```

### Example
```
spo listitem record undeclare --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER --listItemId 1

m365 spo listitem record undeclare --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'List 1' --listItemId 1

m365 spo listitem record undeclare --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl '/sites/project-x/Lists/Lists 1' --id 1

```

---

## listitem-record-unlock

### Syntax
```
m365 spo listitem record unlock [options]
```

### Example
```
m365 spo listitem record unlock --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER --listItemId 1

m365 spo listitem record unlock --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'List 1' --listItemId 1

m365 spo listitem record unlock --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl /sites/project-x/lists/TestList --listItemId 1

```

---

## listitem-remove

### Syntax
```
m365 spo listitem remove [options]
```

### Example
```
m365 spo listitem remove --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER --id 1

m365 spo listitem remove --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'List 1' --id 1

m365 spo listitem remove --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl /sites/project-x/lists/TestList --id 1

```

---

## listitem-retentionlabel-ensure

### Syntax
```
m365 spo listitem retentionlabel ensure [options]
```

### Example
```
m365 spo listitem retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER --listItemId 1 --name 'Some label'```

### Remarks
The `--assetId` option has to do with event-based retention. Event-based retention is about starting a retention period when a specific event occurs, instead of the moment a document was labeled or created.



---

## listitem-retentionlabel-remove

### Syntax
```
m365 spo listitem retentionlabel remove [options]
```

### Example
```
m365 spo listitem retentionlabel remove --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER --listItemId 1

m365 spo listitem retentionlabel remove --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'List 1' --listItemId 1

m365 spo listitem retentionlabel remove --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl /sites/project-x/lists/TestList --listItemId 1

```

---

## listitem-roleassignment-add

### Syntax
```
m365 spo listitem roleassignment add [options]
```

### Example
```
m365 spo listitem roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList" --listItemId 1 --principalId 11 --roleDefinitionId 1073741829```

---

## listitem-roleassignment-remove

### Syntax
```
m365 spo listitem roleassignment remove [options]
```

### Example
```
m365 spo listitem roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --listTitle "someList" --listItemId 1 --groupName "saleGroup"```

---

## listitem-roleinheritance-break

### Syntax
```
m365 spo listitem roleinheritance break [options]
```

### Example
```
m365 spo listitem roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "_someList_" --listItemId 1```

### Remarks
By default, when breaking permissions inheritance, the list item will retain existing permissions. To remove existing permissions, use the `--clearExistingPermissions` option.



---

## listitem-roleinheritance-reset

### Syntax
```
m365 spo listitem roleinheritance reset [options]
```

### Example
```
m365 spo listitem roleinheritance reset --webUrl https://contoso.sharepoint.com/sites/project-x --listItemId 8 --listId EXAMPLE-GUID-PLACEHOLDER

m365 spo listitem roleinheritance reset --webUrl https://contoso.sharepoint.com/sites/project-x --listItemId 8 --listTitle test

m365 spo listitem roleinheritance reset --webUrl https://contoso.sharepoint.com/sites/project-x --listItemId 8 --listUrl /sites/project-x/lists/test --force

```

---

## listitem-set

### Syntax
```
m365 spo listitem set [options]
```

### Example
```
m365 spo listitem set --contentType Item --listTitle "Demo List" --id 147 --webUrl https://contoso.sharepoint.com/sites/project-x --Title "Demo Item"```

### Remarks
:::warning[When using DateTime fields]

When updating a list item with a DateTime field, use the timezone and the format that the site expects, based on its regional settings. Alternatively, a format which works on all regions is the following: `yyyy-MM-dd HH:mm:ss`. However, you should use the local timezone in all situations. UTC date/time or ISO 8601 formatted date/time is not supported.

:::



---

## list-list

### Syntax
```
m365 spo list list [options]
```

### Example
```
m365 spo list list --webUrl https://contoso.sharepoint.com/sites/project-x

m365 spo list list --webUrl https://contoso.sharepoint.com/sites/project-x --properties "BaseTemplate,ParentWebUrl"

m365 spo list list --webUrl https://contoso.sharepoint.com/sites/project-x --properties "Id,Title,RootFolder/ServerRelativeUrl"

m365 spo list list --webUrl https://contoso.sharepoint.com/sites/project-x --filter "BaseTemplate eq 100"

```

### Remarks
When the `--properties` option includes values with a `/`, for example: `RootFolder/ServerRelativeUrl`, an additional `$expand` query parameter should be included on `RootFolder`.



---

## list-remove

### Syntax
```
m365 spo list remove [options]
```

### Example
```
m365 spo list remove --webUrl https://contoso.sharepoint.com/sites/project-x --id EXAMPLE-GUID-PLACEHOLDER

m365 spo list remove --webUrl https://contoso.sharepoint.com/sites/project-x --title 'List 1'

m365 spo list remove --webUrl https://contoso.sharepoint.com/sites/project-x --id EXAMPLE-GUID-PLACEHOLDER --recycle

```

---

## list-retentionlabel-ensure

### Syntax
```
m365 spo list retentionlabel ensure [options]
```

### Example
```
m365 spo list retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl 'Shared Documents' --name 'Some label'

m365 spo list retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'Documents' --name 'Some label' --syncToItems

```

### Remarks
A list retention label is a default label that will be applied to all new items in the list. If you specify `syncToItems`, it is also synced to existing items. 



---

## list-retentionlabel-get

### Syntax
```
m365 spo list retentionlabel get [options]
```

### Example
```
m365 spo list retentionlabel get --listTitle ContosoList --webUrl https://contoso.sharepoint.com/sites/project-x

m365 spo list retentionlabel get --listId EXAMPLE-GUID-PLACEHOLDER --webUrl https://contoso.sharepoint.com/sites/project-x

m365 spo list retentionlabel get --listUrl 'sites/project-x/Documents' --webUrl https://contoso.sharepoint.com/sites/project-x

m365 spo list retentionlabel get --listUrl 'Shared Documents' --webUrl https://contoso.sharepoint.com/sites/project-x

```

---

## list-retentionlabel-remove

### Syntax
```
m365 spo list retentionlabel remove [options]
```

### Example
```
m365 spo list retentionlabel remove --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl 'Shared Documents'

m365 spo list retentionlabel remove --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'Documents'

m365 spo list retentionlabel remove --webUrl https://contoso.sharepoint.com/sites/project-x --listId 'Documents' --force

```

---

## list-roleassignment-add

### Syntax
```
m365 spo list roleassignment add [options]
```

### Example
```
m365 spo list roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList" --principalId 11 --roleDefinitionId 1073741829```

---

## list-roleassignment-remove

### Syntax
```
m365 spo list roleassignment remove [options]
```

### Example
```
m365 spo list roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --listTitle "someList" --groupName "saleGroup"```

---

## list-roleinheritance-break

### Syntax
```
m365 spo list roleinheritance break [options]
```

### Example
```
m365 spo list roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList"```

### Remarks
By default, when breaking permissions inheritance, the list will retain existing permissions. To remove existing permissions, use the `--clearExistingPermissions` option.



---

## list-roleinheritance-reset

### Syntax
```
m365 spo list roleinheritance reset [options]
```

### Example
```
m365 spo list roleinheritance reset --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER```

---

## list-sensitivitylabel-ensure

### Syntax
```
m365 spo list sensitivitylabel ensure [options]
```

### Example
```
m365 spo list sensitivitylabel ensure --webUrl 'https://contoso.sharepoint.com' --listTitle 'Shared Documents' --id 'EXAMPLE-GUID-PLACEHOLDER'```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reaches general availability.

:::



---

## list-set

### Syntax
```
m365 spo list set [options]
```

### Example
```
m365 spo list set --webUrl https://contoso.sharepoint.com/sites/project-x --id EXAMPLE-GUID-PLACEHOLDER --contentTypesEnabled true```

---

## list-sitescript-get

### Syntax
```
m365 spo list sitescript get [options]
```

### Example
```
m365 spo list sitescript get --listTitle ContosoList --webUrl https://contoso.sharepoint.com/sites/project-x

m365 spo list sitescript get --listId EXAMPLE-GUID-PLACEHOLDER --webUrl https://contoso.sharepoint.com/sites/project-x

m365 spo list sitescript get --listUrl 'sites/project-x/Documents' --webUrl https://contoso.sharepoint.com/sites/project-x

m365 spo list sitescript get --listUrl 'Shared Documents' --webUrl https://contoso.sharepoint.com/sites/project-x

```

---

## list-view-add

### Syntax
```
m365 spo list view add [options]
```

### Example
```
m365 spo list view add --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Test" --title "All events" --fields "FieldName1,FieldName2,Created,Author,Modified,Editor" --paged```

### Remarks
We recommend using the `paged` option. When specified, the view supports displaying more items page by page (default behavior). When not specified, the `rowLimit` is absolute, and there is no link to see more items.



---

## list-view-field-add

### Syntax
```
m365 spo list view field add [options]
```

### Example
```
m365 spo list view field add --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER --viewId EXAMPLE-GUID-PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER```

---

## list-view-field-remove

### Syntax
```
m365 spo list view field remove [options]
```

### Example
```
m365 spo list view field remove --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER --viewId EXAMPLE-GUID-PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER```

---

## list-view-field-set

### Syntax
```
m365 spo list view field set [options]
```

### Example
```
m365 spo list view field set --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER --viewId EXAMPLE-GUID-PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER --position 0```

---

## list-view-get

### Syntax
```
m365 spo list view get [options]
```

### Example
```
m365 spo list view get --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'My List' --title 'All Items'

m365 spo list view get --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl 'Lists/My List' --id EXAMPLE-GUID-PLACEHOLDER

m365 spo list view get --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER --title 'All Items'

```

---

## list-view-list

### Syntax
```
m365 spo list view list [options]
```

### Example
```
m365 spo list view list --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle Documents

m365 spo list view list --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER

m365 spo list view list --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl '/sites/project-x/lists/Events'

```

---

## list-view-remove

### Syntax
```
m365 spo list view remove [options]
```

### Example
```
m365 spo list view remove --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER```

---

## list-view-set

### Syntax
```
m365 spo list view set [options]
```

### Example
```
m365 spo list view set --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'My List' --title 'All items' --Title 'All events'```

### Remarks
Specify properties to update using their names, eg. `--Title 'New Title' --JSLink jslink.js`

When updating list formatting, the value of the CustomFormatter property must be XML-escaped, eg. `&lt;` instead of `<`.

:::warning[Escaping JSON in PowerShell]

When updating list view formatting for a view with the `--CustomFormatter` option, it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::



---

## list-webhook-add

### Syntax
```
m365 spo list webhook add [options]
```

### Example
```
m365 spo list webhook add --webUrl https://contoso.sharepoint.com/sites/ninja --listTitle Documents --notificationUrl https://contoso-funcions.azurewebsites.net/webhook```

---

## list-webhook-get

### Syntax
```
m365 spo list webhook get [options]
```

### Example
```
m365 spo list webhook get --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER

m365 spo list webhook get --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle Documents --id EXAMPLE-GUID-PLACEHOLDER

m365 spo list webhook get --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl '/sites/project-x/Documents' --id EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
If the specified `id` doesn't refer to an existing webhook, you will get a `404 - "404 FILE NOT FOUND"` error.



---

## list-webhook-list

### Syntax
```
m365 spo list webhook list [options]
```

### Example
```
m365 spo list webhook list --webUrl https://contoso.sharepoint.com/sites/project-x --listId EXAMPLE-GUID-PLACEHOLDER

m365 spo list webhook list --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle Documents

m365 spo list webhook list --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl '/sites/project-x/Documents'

```

---

## list-webhook-remove

### Syntax
```
m365 spo list webhook remove [options]
```

### Example
```
m365 spo list webhook remove --webUrl https://contoso.sharepoint.com/sites/ninja --listId EXAMPLE-GUID-PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER

m365 spo list webhook remove --webUrl https://contoso.sharepoint.com/sites/ninja --listTitle Documents --id EXAMPLE-GUID-PLACEHOLDER

m365 spo list webhook remove --webUrl https://contoso.sharepoint.com/sites/ninja --listUrl '/sites/ninja/Documents' --id EXAMPLE-GUID-PLACEHOLDER --force

```

### Remarks
If the specified id doesn't refer to an existing webhook, you will get a `404 - "404 FILE NOT FOUND"` error.



---

## list-webhook-set

### Syntax
```
m365 spo list webhook set [options]
```

### Example
```
m365 spo list webhook set --webUrl https://contoso.sharepoint.com/sites/ninja --listId EXAMPLE-GUID-PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER --notificationUrl https://contoso-functions.azurewebsites.net/webhook```

### Remarks
If the specified `id` doesn't refer to an existing webhook, you will get a `404 - "404 FILE NOT FOUND"` error.



---

## mail-send

### Syntax
```
m365 spo mail send [options]
```

### Example
```
m365 spo mail send --webUrl https://contoso.sharepoint.com/sites/project-x --to "user@contoso.com" --subject "Email sent via CLI for Microsoft 365" --body "<h1>CLI for Microsoft 365</h1>Email sent via <b>command</b>."```

### Remarks
All recipients (internal and external) have to have access to the target SharePoint site.



---

## navigation-node-add

### Syntax
```
m365 spo navigation node add [options]
```

### Example
```
m365 spo navigation node add --webUrl https://contoso.sharepoint.com/sites/team-a --location TopNavigationBar --title About --url /sites/team-s/sitepages/about.aspx```

### Remarks
To enable/disable audience targeting for the navigation bar, use the [`spo web set`](../web/web-set.mdx) command.



---

## navigation-node-get

### Syntax
```
m365 spo navigation node get [options]
```

### Example
```
m365 spo navigation node get --webUrl https://contoso.sharepoint.com/sites/team-a --id 2209

```

---

## navigation-node-list

### Syntax
```
m365 spo navigation node list [options]
```

### Example
```
m365 spo navigation node list --webUrl https://contoso.sharepoint.com/sites/team-a --location TopNavigationBar

m365 spo navigation node list --webUrl https://contoso.sharepoint.com/sites/team-a --location QuickLaunch

```

---

## navigation-node-remove

### Syntax
```
m365 spo navigation node remove [options]
```

### Example
```
m365 spo navigation node remove --webUrl https://contoso.sharepoint.com/sites/team-a --location TopNavigationBar --id 2003

m365 spo navigation node remove --webUrl https://contoso.sharepoint.com/sites/team-a --location QuickLaunch --id 2003 --force

```

---

## navigation-node-set

### Syntax
```
m365 spo navigation node set [options]
```

### Example
```
m365 spo navigation node set --webUrl https://contoso.sharepoint.com/sites/marketing --id 2209 --title "Pictures"```

### Remarks
To enable/disable audience targeting for the navigation bar, use the [`spo web set`](../web/web-set.mdx) command.



---

## orgassetslibrary-add

### Syntax
```
m365 spo orgassetslibrary add [options]
```

### Example
```
m365 spo orgassetslibrary add --libraryUrl "https://contoso.sharepoint.com/SiteAssets"

m365 spo orgassetslibrary --libraryUrl "https://contoso.sharepoint.com/SiteAssets" --thumbnailUrl "https://contoso.sharepoint.com/assets/logo.png"

m365 spo orgassetslibrary add --libraryUrl "https://contoso.sharepoint.com/SiteAssets" --orgAssetType "OfficeTemplateLibrary"

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

To enable CDN in your tenant use the [spo cdn set](../cdn/cdn-set.mdx) command.

The document library on which you run the command must at least have read permissions for all users, except external users.



---

## orgassetslibrary-list

### Syntax
```
m365 spo orgassetslibrary list [options]
```

### Example
```
m365 spo orgassetslibrary list

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## orgassetslibrary-remove

### Syntax
```
m365 spo orgassetslibrary remove [options]
```

### Example
```
m365 spo orgassetslibrary remove --libraryUrl "/sites/branding/assets" --force

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## orgnewssite-list

### Syntax
```
m365 spo orgnewssite list [options]
```

### Example
```
m365 spo orgnewssite list

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## orgnewssite-remove

### Syntax
```
m365 spo orgnewssite remove [options]
```

### Example
```
m365 spo orgnewssite remove --url https://contoso.sharepoint.com/sites/site1

m365 spo orgnewssite remove --url https://contoso.sharepoint.com/sites/site1 --force

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## orgnewssite-set

### Syntax
```
m365 spo orgnewssite set [options]
```

### Example
```
m365 spo orgnewssite set --url https://contoso.sharepoint.com/sites/site1

```

### Remarks
Using the `-u, --url` option you can specify which site to add to the list of organizational news sites.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## page-add

### Syntax
```
m365 spo page add [options]
```

### Example
```
m365 spo page add --name new-page.aspx --webUrl https://contoso.sharepoint.com/sites/a-team```

### Remarks
If you try to create a page with a name of a page that already exists, you will get a `The file exists` error.

If you choose to promote the page using the `promoteAs` option or enable page comments, you will see the result only after publishing the page.



---

## page-clientsidewebpart-add

### Syntax
```
m365 spo page clientsidewebpart add [options]
```

### Example
```
m365 spo page clientsidewebpart add --webUrl https://contoso.sharepoint.com/sites/a-team --pageName page.aspx --standardWebPart BingMap```

### Remarks
If the specified `pageName` doesn't refer to an existing modern page, you will get a _File doesn't exists_ error.

To add a standard web part to the page, specify one of the following values: _ContentRollup, BingMap, ContentEmbed, DocumentEmbed, Image, ImageGallery, LinkPreview, NewsFeed, NewsReel, PowerBIReportEmbed, QuickChart, SiteActivity, VideoEmbed, YammerEmbed, Events, GroupCalendar, Hero, List, PageTitle, People, QuickLinks, CustomMessageRegion, Divider, MicrosoftForms, Spacer_.

:::warning[Escaping JSON in PowerShell]

When using the `--webPartProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::



---

## page-column-get

### Syntax
```
m365 spo page column get [options]
```

### Example
```
m365 spo page column get --webUrl https://contoso.sharepoint.com/sites/team-a --pageName home.aspx --section 1 --column 1

```

### Remarks
If the specified `pageName` doesn't refer to an existing modern page, you will get a _File doesn't exists_ error.



---

## page-column-list

### Syntax
```
m365 spo page column list [options]
```

### Example
```
m365 spo page column list --webUrl https://contoso.sharepoint.com/sites/team-a --pageName home.aspx --section 1

```

### Remarks
If the specified `pageName` doesn't refer to an existing modern page, you will get a _File doesn't exists_ error.



---

## page-control-get

### Syntax
```
m365 spo page control get [options]
```

### Example
```
m365 spo page control get --id EXAMPLE-GUID-PLACEHOLDER --webUrl https://contoso.sharepoint.com/sites/team-a --pageName home.aspx

```

### Remarks
If the specified `pageName` doesn't refer to an existing modern page, you will get a `File doesn't exists` error.



---

## page-control-list

### Syntax
```
m365 spo page control list [options]
```

### Example
```
m365 spo page control list --webUrl https://contoso.sharepoint.com/sites/team-a --pageName home.aspx

```

### Remarks
If the specified `pageName` doesn't refer to an existing modern page, you will get a `File doesn't exists` error.



---

## page-control-set

### Syntax
```
m365 spo page control set [options]
```

### Example
```
m365 spo page control set --id EXAMPLE-GUID-PLACEHOLDER --webUrl https://contoso.sharepoint.com/sites/team-a --pageName home.aspx --webPartData '{"title":"New WP Title","properties": {"description": "New description"}}'

m365 spo page control set --id EXAMPLE-GUID-PLACEHOLDER --webUrl https://contoso.sharepoint.com/sites/team-a --pageName home.aspx --webPartProperties '{"description": "New description"}'

```

### Remarks
If the specified `pageName` doesn't refer to an existing modern page, you will get a `File doesn't exists` error.

:::warning[Escaping JSON in PowerShell]

When using the `--webPartProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::



---

## page-copy

### Syntax
```
m365 spo page copy [options]
```

### Example
```
m365 spo page copy --webUrl https://contoso.sharepoint.com/sites/team-a --sourceName "home.aspx" --targetUrl "home-copy.aspx"```

### Remarks
If another page exists at the specified target location, copying the page will fail, unless you include the `--overwrite` option.



---

## page-get

### Syntax
```
m365 spo page get [options]
```

### Example
```
m365 spo page get --webUrl https://contoso.sharepoint.com/sites/team-a --name home.aspx

m365 spo page get --webUrl https://contoso.sharepoint.com/sites/team-a --default

m365 spo page get --webUrl https://contoso.sharepoint.com/sites/team-a --name home.aspx --metadataOnly

```

### Remarks
If the specified name doesn't refer to an existing modern page, you will get a `File doesn't exists` error.



---

## page-header-set

### Syntax
```
m365 spo page header set [options]
```

### Example
```
m365 spo page header set --webUrl https://contoso.sharepoint.com/sites/team-a --pageName home.aspx```

### Remarks
If the specified `name` doesn't refer to an existing modern page, you will get a `File doesn't exists` error.



---

## page-list

### Syntax
```
m365 spo page list [options]
```

### Example
```
m365 spo page list --webUrl https://contoso.sharepoint.com/sites/team-a

```

---

## page-publish

### Syntax
```
m365 spo page publish [options]
```

### Example
```
m365 spo page publish --webUrl https://contoso.sharepoint.com/sites/Marketing --name "Style guide.aspx"

m365 spo page publish --webUrl https://contoso.sharepoint.com/sites/Marketing --name "/Styles/Guide.aspx"

```

---

## page-remove

### Syntax
```
m365 spo page remove [options]
```

### Example
```
m365 spo page remove --name HR.aspx --webUrl https://contoso.sharepoint.com/sites/Marketing```

---

## page-section-add

### Syntax
```
m365 spo page section add [options]
```

### Example
```
m365 spo page section add --pageName home.aspx --webUrl https://contoso.sharepoint.com/sites/newsletter --sectionTemplate OneColumn --order 1```

### Remarks
If the specified `pageName` doesn't refer to an existing modern page, you will get a _File doesn't exists_ error.



---

## page-section-get

### Syntax
```
m365 spo page section get [options]
```

### Example
```
m365 spo page section get --webUrl https://contoso.sharepoint.com/sites/team-a --pageName home.aspx --section 1

```

### Remarks
If the specified `pageName` doesn't refer to an existing modern page, you will get a _File doesn't exists_ error.



---

## page-section-list

### Syntax
```
m365 spo page section list [options]
```

### Example
```
m365 spo page section list --webUrl https://contoso.sharepoint.com/sites/team-a --pageName home.aspx

```

### Remarks
If the specified `pageName` doesn't refer to an existing modern page, you will get a _File doesn't exists_ error.



---

## page-section-remove

### Syntax
```
m365 spo page section remove [options]
```

### Example
```
m365 spo page section remove --webUrl https://contoso.sharepoint.com/sites/team-a --pageName home.aspx --section 1

```

### Remarks
If the specified `pageName` doesn't refer to an existing modern page, you will get a _File doesn't exists_ error.



---

## page-set

### Syntax
```
m365 spo page set [options]
```

### Example
```
m365 spo page set --name page.aspx --webUrl https://contoso.sharepoint.com/sites/a-team --layoutType Article```

### Remarks
If you try to create a page with a name of a page that already exists, you will get a `The file doesn't exists` error.

If you choose to promote the page using the `promoteAs` option or enable page comments, you will see the result only after publishing the page.

Running this command from the Windows Command Shell (cmd.exe) or PowerShell for Windows OS XP, 7, 8, 8.1 without bash installed might require additional formatting for command options that have JSON, XML or JavaScript values because the command shell treat quotes differently. For example, this is how you can add page content from the Windows cmd.exe:

Note, how the content option has escaped double quotes `'[{\"controlType\": 4,\"id\": \"EXAMPLE-GUID-PLACEHOLDER\",\"position\": {\"layoutIndex\": 1,\"zoneIndex\": 1,\"sectionIndex\": 1,\"sectionFactor\": 12,\"controlIndex\": 1},\"addedFromPersistedData\": true,\"innerHTML\":\"<p>Hello World</p>\"}]'` compared to execution from bash `''[{"controlType": 4,"id": "EXAMPLE-GUID-PLACEHOLDER","position": {"layoutIndex": 1,"zoneIndex": 1,"sectionIndex": 1,"sectionFactor": 12,"controlIndex": 1},"addedFromPersistedData": true,"innerHTML":"<p>Hello World</p>"}]'`.

:::warning[Escaping JSON in PowerShell]

When using the `--content` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::



---

## page-template-list

### Syntax
```
m365 spo page template list [options]
```

### Example
```
m365 spo page template list --webUrl https://contoso.sharepoint.com/sites/team-a

```

---

## page-text-add

### Syntax
```
m365 spo page text add [options]
```

### Example
```
m365 spo page text add --webUrl https://contoso.sharepoint.com/sites/a-team --pageName page.aspx --text 'Hello world'

m365 spo page text add --webUrl https://contoso.sharepoint.com/sites/a-team --pageName page.aspx --text 'Hello world' --section 2 --column 3

m365 spo page text add --webUrl https://contoso.sharepoint.com/sites/a-team --pageName page.aspx --text 'Hello world' --order 1

```

### Remarks
If the specified `pageName` doesn't refer to an existing modern page, you will get a _File doesn't exists_ error.



---

## propertybag-get

### Syntax
```
m365 spo propertybag get [options]
```

### Example
```
m365 spo propertybag get --webUrl https://contoso.sharepoint.com/sites/test --key key1```

---

## propertybag-list

### Syntax
```
m365 spo propertybag list [options]
```

### Example
```
m365 spo propertybag list --webUrl https://contoso.sharepoint.com/sites/test

m365 spo propertybag list --webUrl https://contoso.sharepoint.com/sites/test --folder /

m365 spo propertybag list --webUrl https://contoso.sharepoint.com/sites/test --folder '/Shared Documents'

m365 spo propertybag list --webUrl https://contoso.sharepoint.com/sites/test --folder '/Shared Documents/MyFolder'

m365 spo propertybag list --webUrl https://contoso.sharepoint.com/sites/test --folder /Lists/MyList

```

---

## propertybag-remove

### Syntax
```
m365 spo propertybag remove [options]
```

### Example
```
m365 spo propertybag remove --webUrl https://contoso.sharepoint.com/sites/test --key key1```

---

## propertybag-set

### Syntax
```
m365 spo propertybag set [options]
```

### Example
```
m365 spo propertybag set --webUrl https://contoso.sharepoint.com/sites/test --key key1 --value value1```

### Remarks
SharePoint Online supports setting property bag values only in classic sites. On modern sites you will get a _Site has NoScript enabled, and setting property bag values is not supported_ error.



---

## report-activityfilecounts

### Syntax
```
m365 spo report activityfilecounts [options]
```

### Example
```
m365 spo report activityfilecounts --period D7

m365 spo report activityfilecounts --period D7 --output text > "activityfilecounts.txt"

m365 spo report activityfilecounts --period D7 --output json > "activityfilecounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-activitypages

### Syntax
```
m365 spo report activitypages [options]
```

### Example
```
m365 spo report activitypages --period D7

m365 spo report activitypages --period D7 --output text > "activitypages.txt"

m365 spo report activitypages --period D7 --output json > "activitypages.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-activityusercounts

### Syntax
```
m365 spo report activityusercounts [options]
```

### Example
```
m365 spo report activityusercounts --period D7

m365 spo report activityusercounts --period D7 --output text > "activityusercounts.txt"

m365 spo report activityusercounts --period D7 --output json > "activityusercounts.json"

```

### Remarks
A user is considered active if he or she has executed a file activity (save, sync, modify, or share) or visited a page within the specified time period

:::info

This command supports only csv and json output.

:::



---

## report-activityuserdetail

### Syntax
```
m365 spo report activityuserdetail [options]
```

### Example
```
m365 spo report activityuserdetail --period D7

m365 spo report activityuserdetail --date 2019-05-01

m365 spo report activityuserdetail --period D7 --output text > "activityuserdetail.txt"

m365 spo report activityuserdetail --period D7 --output json > "activityuserdetail.json"

```

### Remarks
As this report is only available for the past 28 days, date parameter value should be a date from that range.

:::info

This command supports only csv and json output.

:::



---

## report-siteusagedetail

### Syntax
```
m365 spo report siteusagedetail [options]
```

### Example
```
m365 spo report siteusagedetail --period D7

m365 spo report siteusagedetail --date 2019-05-01

m365 spo report siteusagedetail --period D7 --output text > "siteusagedetail.txt"

m365 spo report siteusagedetail --period D7 --output json > "siteusagedetail.json"

```

### Remarks
As this report is only available for the past 28 days, date parameter value should be a date from that range.

:::info

This command supports only csv and json output.

:::



---

## report-siteusagefilecounts

### Syntax
```
m365 spo report siteusagefilecounts [options]
```

### Example
```
m365 spo report siteusagefilecounts --period D7

m365 spo report siteusagefilecounts --period D7 --output text > "siteusagefilecounts.txt"

m365 spo report siteusagefilecounts --period D7 --output json > "siteusagefilecounts.json"

```

### Remarks
A file (user or system) is considered active if it has been saved, synced, modified, or shared within the specified time period.

:::info

This command supports only csv and json output.

:::



---

## report-siteusagepages

### Syntax
```
m365 spo report siteusagepages [options]
```

### Example
```
m365 spo report siteusagepages --period D7

m365 spo report siteusagepages --period D7 --output text > "siteusagepages.txt"

m365 spo report siteusagepages --period D7 --output json > "siteusagepages.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-siteusagesitecounts

### Syntax
```
m365 spo report siteusagesitecounts [options]
```

### Example
```
m365 spo report siteusagesitecounts --period D7

m365 spo report siteusagesitecounts --period D7 --output text > "siteusagesitecounts.txt"

m365 spo report siteusagesitecounts --period D7 --output json > "siteusagesitecounts.json"

```

### Remarks
A file (user or system) is considered active if it has been saved, synced, modified, or shared within the specified time period.

:::info

This command supports only csv and json output.

:::



---

## report-siteusagestorage

### Syntax
```
m365 spo report siteusagestorage [options]
```

### Example
```
m365 spo report siteusagestorage --period D7

m365 spo report siteusagestorage --period D7 --output text > "siteusagestorage.txt"

m365 spo report siteusagestorage --period D7 --output json > "siteusagestorage.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## roledefinition-add

### Syntax
```
m365 spo roledefinition add [options]
```

### Example
```
m365 spo roledefinition add --webUrl https://contoso.sharepoint.com/sites/project-x --name test

m365 spo roledefinition add --webUrl https://contoso.sharepoint.com/sites/project-x --name test --description "test description" --rights "ViewListItems,AddListItems,EditListItems,DeleteListItems"

```

### Remarks
The `--rights` option accepts **case-sensitive** values.



---

## roledefinition-get

### Syntax
```
m365 spo roledefinition get [options]
```

### Example
```
m365 spo roledefinition get --webUrl https://contoso.sharepoint.com/sites/project-x --id 1

```

---

## roledefinition-list

### Syntax
```
m365 spo roledefinition list [options]
```

### Example
```
m365 spo roledefinition list --webUrl https://contoso.sharepoint.com/sites/project-x

```

---

## roledefinition-remove

### Syntax
```
m365 spo roledefinition remove [options]
```

### Example
```
m365 spo roledefinition remove --webUrl https://contoso.sharepoint.com/sites/project-x --id 1

m365 spo roledefinition remove --webUrl https://contoso.sharepoint.com/sites/project-x --id 1 --force

```

---

## serviceprincipal-grant-add

### Syntax
```
m365 spo serviceprincipal grant add [options]
```

### Example
```
m365 spo serviceprincipal grant add --resource 'Microsoft Graph' --scope 'Mail.Read'

m365 spo serviceprincipal grant add --resource 'contoso-api' --scope 'user_impersonation'

```

### Remarks
:::info

To use this command you must be a Global administrator.

:::



---

## serviceprincipal-grant-list

### Syntax
```
m365 spo serviceprincipal grant list [options]
```

### Example
```
m365 spo serviceprincipal grant list

```

### Remarks
:::info

To use this command you must be a Global administrator.

:::



---

## serviceprincipal-grant-revoke

### Syntax
```
m365 spo serviceprincipal grant revoke [options]
```

### Example
```
m365 spo serviceprincipal grant revoke --id EXAMPLE_SECRET_VALUE_PLACEHOLDER

m365 spo serviceprincipal grant revoke --id EXAMPLE_SECRET_VALUE_PLACEHOLDER --scope "Mail.Read"

```

### Remarks
:::info

To use this command you must be a Global administrator.

:::

The permission grant you want to revoke is denoted using its `ObjectId`. You can retrieve it using the [spo serviceprincipal grant list](./serviceprincipal-grant-list.mdx) command.



---

## EXAMPLE_SECRET_VALUE_PLACEHOLDER

### Syntax
```
m365 spo serviceprincipal permissionrequest approve [options]
```

### Example
```
m365 spo serviceprincipal permissionrequest approve --id EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::info

The admin role that's required to approve permissions depends on the API. To approve permissions to any of the third-party APIs registered in the tenant, the application administrator role is sufficient. To approve permissions for Microsoft Graph or any other Microsoft API, the Global Administrator role is required.

:::

The permission request you want to approve is denoted using its `ID`. You can retrieve it using the [spo serviceprincipal permissionrequest list](./EXAMPLE_SECRET_VALUE_PLACEHOLDER) command.



---

## serviceprincipal-permissionrequest-deny

### Syntax
```
m365 spo serviceprincipal permissionrequest deny [options]
```

### Example
```
m365 spo serviceprincipal permissionrequest deny --id EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::info

The admin role that's required to deny permissions depends on the API. To approve permissions to any of the third-party APIs registered in the tenant, the application administrator role is sufficient. To approve permissions for Microsoft Graph or any other Microsoft API, the Global Administrator role is required.

:::

The permission request you want to approve is denoted using its `ID`. You can retrieve it using the [spo serviceprincipal permissionrequest list](./EXAMPLE_SECRET_VALUE_PLACEHOLDER) command.



---

## serviceprincipal-permissionrequest-list

### Syntax
```
m365 spo serviceprincipal permissionrequest list [options]
```

### Example
```
m365 spo serviceprincipal permissionrequest list

```

### Remarks
:::info

The admin role that's required to list permissions depends on the API. To approve permissions to any of the third-party APIs registered in the tenant, the application administrator role is sufficient. To approve permissions for Microsoft Graph or any other Microsoft API, the Global Administrator role is required.

:::



---

## serviceprincipal-set

### Syntax
```
m365 spo serviceprincipal set [options]
```

### Example
```
m365 spo serviceprincipal set --enabled true

m365 spo serviceprincipal set --enabled false

m365 spo serviceprincipal set --enabled true --force

```

### Remarks
:::info

To use this command you must be a Global administrator.

:::

Using the `-e, --enabled` option you can specify whether the service principal should be enabled or disabled. Use `true` to enable the service principal and `false` to disable it.



---

## site-add

### Syntax
```
m365 spo site add [options]
```

### Example
```
m365 spo site add --alias team1 --title "Team 1"```

### Remarks
Using the `-z, --timeZone` option you have to specify the time zone of the site. For more information about the valid values see [https://msdn.microsoft.com/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER](https://msdn.microsoft.com/library/EXAMPLE_SECRET_VALUE_PLACEHOLDER).

The value of the `--resourceQuota` option must not exceed the company's aggregate available Sandboxed Solutions quota. For more information, see Resource Usage Limits on Sandboxed Solutions in SharePoint 2010: [http://msdn.microsoft.com/en-us/library/gg615462.aspx](http://msdn.microsoft.com/en-us/library/gg615462.aspx).

The value of the `--resourceQuotaWarningLevel` option must not exceed the value of the `--resourceQuota` option.

The value of the `--storageQuota` option must not exceed the company's available quota.

The value of the `--storageQuotaWarningLevel` option must not exceed the the value of the `--storageQuota` option.

If you try to create a site with the same URL as a site that has been previously moved to the recycle bin, you will get an error. To avoid this error, you can use the `--removeDeletedSite` option. Prior to creating the site, the spo site add command will check if the site with the specified URL has been previously moved to the recycle bin and if so, will remove it. Because removing sites from the recycle bin might take a moment, it should be used in conjunction with the `--wait` option so that the new site is not created before the old site is fully removed.

Deleting and creating classic site collections is by default asynchronous and depending on the current state of Office 365, might take up to few minutes. If you're building a script with steps that require the site to be fully provisioned, you should use the `--wait` flag. When using this flag, the spo site add command will keep running until it received confirmation from Office 365 that the site has been fully provisioned.

The `--owners` option is mandatory for creating `CommunicationSite` sites with app-only permissions.

When trying to create a team site using app-only permissions, you will get an _Insufficient privileges to complete the operation._ error. As a workaround, you can use the [`entra m365group add`](../../entra/m365group/m365group-add.mdx) command, followed by [`spo site set`](./site-set.mdx) to further configure the Team site.



---

## site-admin-add

### Syntax
```
m365 spo site admin add [options]
```

### Example
```
m365 spo site admin add --siteUrl https://contoso.sharepoint.com --userId EXAMPLE-GUID-PLACEHOLDER --primary

m365 spo site admin add --siteUrl https://contoso.sharepoint.com --groupName SP_Administrators --asAdmin

```

### Remarks
:::info

To use this command with the `--asAdmin` mode, you have to have permissions to access the tenant admin site.

Without this parameter, you have to have site collection admin permissions for the requested site.

:::



---

## site-admin-list

### Syntax
```
m365 spo site admin list [options]
```

### Example
```
m365 spo site admin list --siteUrl https://contoso.sharepoint.com

m365 spo site admin list --siteUrl https://contoso.sharepoint.com --asAdmin

```

### Remarks
:::info

To use this command with the `--asAdmin` mode, you must be at least SharePoint administrator.

Without this parameter, you must have site collection admin permissions for the requested site.

:::



---

## site-admin-remove

### Syntax
```
m365 spo site admin remove [options]
```

### Example
```
m365 spo site admin remove --siteUrl https://contoso.sharepoint.com --userId EXAMPLE-GUID-PLACEHOLDER

m365 spo site admin remove --siteUrl https://contoso.sharepoint.com --groupName SP_Administrators --force --asAdmin

```

### Remarks
:::info

To use this command with the `--asAdmin` mode, you have to have permissions to access the tenant admin site.

Without this parameter, you have to have site collection admin permissions for the requested site.

:::



---

## site-appcatalog-add

### Syntax
```
m365 spo site appcatalog add [options]
```

### Example
```
m365 spo site appcatalog add --siteUrl https://contoso.sharepoint.com/sites/site

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## site-appcatalog-list

### Syntax
```
m365 spo site appcatalog list [options]
```

### Example
```
m365 spo site appcatalog list

```

### Remarks
:::info

To use this command you need to have at least read permissions on the SharePoint root site.

:::



---

## site-appcatalog-remove

### Syntax
```
m365 spo site appcatalog remove [options]
```

### Example
```
m365 spo site appcatalog remove --siteUrl https://contoso.sharepoint/sites/site

m365 spo site appcatalog remove --siteUrl https://contoso.sharepoint/sites/site --force

```

### Remarks
While the command uses the term *'remove'*, like its equivalent PowerShell cmdlet, it does not remove the special library **Apps for SharePoint** from the site collection. Instead, it disables the site collection app catalog in that site. Packages deployed to the app catalog are not available within the site collection.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## site-apppermission-add

### Syntax
```
m365 spo site apppermission add [options]
```

### Example
```
m365 spo site apppermission add --siteUrl https://contoso.sharepoint.com/sites/project-x --permission read --appDisplayName Foo

```

### Remarks
To set permissions, specify at minimum either `appId` or `appDisplayName`. For best performance specify both values to avoid extra lookup.



---

## site-apppermission-get

### Syntax
```
m365 spo site apppermission get [options]
```

### Example
```
m365 spo site apppermission get --siteUrl https://contoso.sharepoint.com/sites/project-x --id EXAMPLE_SECRET_VALUE_PLACEHOLDER

```

---

## site-apppermission-list

### Syntax
```
m365 spo site apppermission list [options]
```

### Example
```
m365 spo site apppermission list --siteUrl https://contoso.sharepoint.com/sites/project-x

m365 spo site apppermission list --siteUrl https://contoso.sharepoint.com/sites/project-x --appDisplayName Foo

```

### Remarks
To filter by an app, pass in either `appId` or `appDisplayName` not both



---

## site-apppermission-remove

### Syntax
```
m365 spo site apppermission remove [options]
```

### Example
```
m365 spo site apppermission remove --siteUrl https://contoso.sharepoint.com/sites/project-x --appId EXAMPLE-GUID-PLACEHOLDER

m365 spo site apppermission remove --siteUrl https://contoso.sharepoint.com/sites/project-x --appDisplayName Foo

m365 spo site apppermission remove --siteUrl https://contoso.sharepoint.com/sites/project-x --id EXAMPLE_SECRET_VALUE_PLACEHOLDER

```

---

## site-apppermission-set

### Syntax
```
m365 spo site apppermission set [options]
```

### Example
```
m365 spo site apppermission set --siteUrl https://contoso.sharepoint.com/sites/project-x --id EXAMPLE_SECRET_VALUE_PLACEHOLDER --permission read

m365 spo site apppermission set --siteUrl https://contoso.sharepoint.com/sites/project-x --appDisplayName Foo --permission read

m365 spo site apppermission set --siteUrl https://contoso.sharepoint.com/sites/project-x --appId EXAMPLE-GUID-PLACEHOLDER --permission read

```

---

## site-chrome-set

### Syntax
```
m365 spo site chrome set [options]
```

### Example
```
m365 spo site chrome set --siteUrl https://contoso.sharepoint.com/sites/project-x --headerLayout Compact

m365 spo site chrome set --siteUrl https://contoso.sharepoint.com/sites/project-x  --headerLayout Extended --logoAlignment Right

m365 spo site chrome set --siteUrl https://contoso.sharepoint.com/sites/project-x --disableFooter true

```

---

## site-commsite-enable

### Syntax
```
m365 spo site commsite enable [options]
```

### Example
```
m365 spo site commsite enable --url https://contoso.sharepoint.com

m365 spo site commsite enable --url https://contoso.sharepoint.com --designPackageId EXAMPLE-GUID-PLACEHOLDER

m365 spo site commsite enable --url https://contoso.sharepoint.com --designPackage Showcase

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## sitedesign-add

### Syntax
```
m365 spo sitedesign add [options]
```

### Example
```
m365 spo sitedesign add --title "Contoso team site" --webTemplate TeamSite --siteScripts "EXAMPLE-GUID-PLACEHOLDER,EXAMPLE-GUID-PLACEHOLDER"

m365 spo sitedesign add --title "Contoso communication site" --webTemplate CommunicationSite --siteScripts "EXAMPLE-GUID-PLACEHOLDER" --isDefault

```

### Remarks
Each time you execute the `spo sitedesign add` command, it will create a new site design with a unique ID. Before creating a site design, be sure that another design with the same name doesn't already exist.

When specifying IDs of site scripts to use with your site design, ensure that the IDs refer to existing site scripts or provisioning sites using the design will lead to unexpected results.



---

## sitedesign-apply

### Syntax
```
m365 spo sitedesign apply [options]
```

### Example
```
m365 spo sitedesign apply --id EXAMPLE-GUID-PLACEHOLDER --webUrl https://contoso.sharepoint.com/sites/project-x

m365 spo sitedesign apply --id EXAMPLE-GUID-PLACEHOLDER --webUrl https://contoso.sharepoint.com/sites/project-x --asTask

```

---

## sitedesign-get

### Syntax
```
m365 spo sitedesign get [options]
```

### Example
```
m365 spo sitedesign get --id EXAMPLE-GUID-PLACEHOLDER

m365 spo sitedesign get --title "Contoso Site Design"

```

### Remarks
If the specified `id` or `title` doesn't refer to an existing site design, you will get a `File not found` error.



---

## sitedesign-list

### Syntax
```
m365 spo sitedesign list [options]
```

### Example
```
m365 spo sitedesign list

```

---

## sitedesign-remove

### Syntax
```
m365 spo sitedesign remove [options]
```

### Example
```
m365 spo sitedesign remove --id EXAMPLE-GUID-PLACEHOLDER

m365 spo sitedesign remove --id EXAMPLE-GUID-PLACEHOLDER --force

```

### Remarks
If the specified `id` doesn't refer to an existing site design, you will get a `File not found` error.



---

## sitedesign-rights-grant

### Syntax
```
m365 spo sitedesign rights grant [options]
```

### Example
```
m365 spo sitedesign rights grant --siteDesignId EXAMPLE-GUID-PLACEHOLDER --principals PattiF --rights View

m365 spo sitedesign rights grant --siteDesignId EXAMPLE-GUID-PLACEHOLDER --principals "PattiF,AdeleV" --rights View

m365 spo sitedesign rights grant --siteDesignId EXAMPLE-GUID-PLACEHOLDER --principals PattiF@contoso.com --rights View

```

---

## sitedesign-rights-list

### Syntax
```
m365 spo sitedesign rights list [options]
```

### Example
```
m365 spo sitedesign rights list --siteDesignId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
If the specified `siteDesignId` doesn't refer to an existing site script, you will get a `File not found` error.

If no permissions are listed, it means that the particular site design is visible to everyone.



---

## sitedesign-rights-revoke

### Syntax
```
m365 spo sitedesign rights revoke [options]
```

### Example
```
m365 spo sitedesign rights revoke --siteDesignId EXAMPLE-GUID-PLACEHOLDER --principals PattiF

m365 spo sitedesign rights revoke --siteDesignId EXAMPLE-GUID-PLACEHOLDER --principals "PattiF,AdeleV" --force

```

### Remarks
If the specified id doesn't refer to an existing site design, you will get a `File not found` error.

If all principals have rights revoked on the site design, the site design becomes viewable to everyone.

If you try to revoke access for a user that doesn't have access granted to the specified site design you will get a `The specified user or domain group was not found error`.



---

## sitedesign-run-list

### Syntax
```
m365 spo sitedesign run list [options]
```

### Example
```
m365 spo sitedesign run list --webUrl https://contoso.sharepoint.com/sites/team-a

m365 spo sitedesign run list --webUrl https://contoso.sharepoint.com/sites/team-a --siteDesignId EXAMPLE-GUID-PLACEHOLDER

```

---

## sitedesign-run-status-get

### Syntax
```
m365 spo sitedesign run status get [options]
```

### Example
```
m365 spo sitedesign run status get --webUrl https://contoso.sharepoint.com/sites/team-a --runId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
For text output mode, displays the name of the action, site script and the outcome of the action. For JSON output mode, displays all available information.



---

## sitedesign-set

### Syntax
```
m365 spo sitedesign set [options]
```

### Example
```
m365 spo sitedesign set --id EXAMPLE-GUID-PLACEHOLDER --title "Contoso site design" --version 2

m365 spo sitedesign set --id EXAMPLE-GUID-PLACEHOLDER --webTemplate CommunicationSite  --isDefault true

m365 spo sitedesign set --id EXAMPLE-GUID-PLACEHOLDER --webTemplate CommunicationSite  --isDefault true --siteScripts "EXAMPLE-GUID-PLACEHOLDER,EXAMPLE-GUID-PLACEHOLDER"

```

### Remarks
If you had previously set the `isDefault` option to `true`, and wish for it to remain `true`, you must pass in this option again or it will be reset to `false`.

When specifying IDs of site scripts to use with your site design, ensure that the IDs refer to existing site scripts or provisioning sites using the design will lead to unexpected results.



---

## sitedesign-task-get

### Syntax
```
m365 spo sitedesign task get [options]
```

### Example
```
m365 spo sitedesign task get --id EXAMPLE-GUID-PLACEHOLDER

```

---

## sitedesign-task-list

### Syntax
```
m365 spo sitedesign task list [options]
```

### Example
```
m365 spo sitedesign task list --webUrl https://contoso.sharepoint.com/sites/team-a

```

---

## sitedesign-task-remove

### Syntax
```
m365 spo sitedesign task remove [options]
```

### Example
```
m365 spo sitedesign task remove --id EXAMPLE-GUID-PLACEHOLDER --force

m365 spo sitedesign task remove --id EXAMPLE-GUID-PLACEHOLDER

```

---

## site-ensure

### Syntax
```
m365 spo site ensure [options]
```

### Example
```
m365 spo site ensure --url https://contoso.sharepoint.com/teams/team1 --alias team1 --title "Team 1"

m365 spo site ensure --url https://contoso.sharepoint.com/sites/comms --title Comms --type CommunicationSite

m365 spo site ensure --url https://contoso.sharepoint.com/sites/classic --title Classic --type ClassicSite

m365 spo site ensure --url https://contoso.sharepoint.com/sites/team1 --alias team1 --title "Team 1" --isPublic --shareByEmailEnabled

```

### Remarks
This command checks if a site collection exists at the specified URL.

If no site is found, this command will create one using the specified options. For more information about creating site collections and things that you should into account, see the [`spo site add`](./site-add.mdx) command.

If a site is found at the specified URL, this command will update its properties using the specified values. For more information about updating site collections and things that you should take into account see the [`spo site set`](./site-set.mdx) command.

If another site exists at the specified URL and you haven't specified the `type` option, this command will proceed with updating its properties. If you specified the `type` and it doesn't match the type of the existing site, this command will return an error.

If you set the type to `ClassicSite`, you should also set a value of the `webTemplate` option. If you don't, checking the type of existing site will be skipped. If no site exists at the specified URL, creating the site will fail.



---

## site-get

### Syntax
```
m365 spo site get [options]
```

### Example
```
m365 spo site get -u https://contoso.sharepoint.com/sites/project-x

```

### Remarks
This command can retrieve information for both classic and modern sites.



---

## site-groupify

### Syntax
```
m365 spo site groupify [options]
```

### Example
```
m365 spo site groupify --url https://contoso.sharepoin.com/sites/team-a --alias team-a --displayName 'Team A'

m365 spo site groupify --url https://contoso.sharepoin.com/sites/team-a --alias team-a --displayName 'Team A' --isPublic

m365 spo site groupify --url https://contoso.sharepoin.com/sites/team-a --alias team-a --displayName 'Team A' --classification HBI

m365 spo site groupify --url https://contoso.sharepoin.com/sites/team-a --alias team-a --displayName 'Team A' --keepOldHomepage

```

### Remarks
:::warning

This command is based on a SharePoint API that is currently in preview and is subject to change once the API reached general availability.

:::

When connecting site collection to an Microsoft 365 Group, SharePoint will create a new group using the specified information. If a group with the same name already exists, you will get a `The group alias already exists.` error.



---

## site-hubsite-connect

### Syntax
```
m365 spo site hubsite connect [options]
```

### Example
```
m365 spo site hubsite connect --siteUrl https://contoso.sharepoint.com/sites/contoso-sales --id EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
If the specified site collection is already connected to a hub site, it will be disconnected and connected to the newly specified hub site.

If the specified `id` doesn't point to a valid hub site, you will get a `ResourceNotFoundException` error.



---

## site-hubsite-disconnect

### Syntax
```
m365 spo site hubsite disconnect [options]
```

### Example
```
m365 spo site hubsite disconnect --siteUrl https://contoso.sharepoint.com/sites/sales

m365 spo site hubsite disconnect --siteUrl https://contoso.sharepoint.com/sites/sales --force

```

---

## site-hubsite-theme-sync

### Syntax
```
m365 spo site hubsite theme sync [options]
```

### Example
```
m365 spo site hubsite theme sync --webUrl https://contoso.sharepoint.com/sites/project-x

```

---

## site-inplacerecordsmanagement-set

### Syntax
```
m365 spo site inplacerecordsmanagement set [options]
```

### Example
```
m365 spo site inplacerecordsmanagement set --siteUrl https://contoso.sharepoint.com/sites/team-a --enabled true

m365 spo site inplacerecordsmanagement set --siteUrl https://contoso.sharepoint.com/sites/team-a --enabled false

```

---

## site-recyclebinitem-clear

### Syntax
```
m365 spo site recyclebinitem clear [options]
```

### Example
```
m365 spo site recyclebinitem clear --siteUrl https://contoso.sharepoint.com/sites/sales

m365 spo site recyclebinitem clear --siteUrl https://contoso.sharepoint.com/sites/sales --secondary

```

### Remarks
:::warning

Items in the recycle bin will be permanently removed without the ability to restore them.

:::



---

## site-recyclebinitem-list

### Syntax
```
m365 spo site recyclebinitem list [options]
```

### Example
```
m365 spo site recyclebinitem list --siteUrl https://contoso.sharepoint.com/site

m365 spo site recyclebinitem list --siteUrl https://contoso.sharepoint.com/site --type files

```

### Remarks
When type is not specified then the command will return all items in the recycle bin



---

## site-recyclebinitem-move

### Syntax
```
m365 spo site recyclebinitem move [options]
```

### Example
```
m365 spo site recyclebinitem move --siteUrl https://contoso.sharepoint.com/sites/sales --ids "EXAMPLE-GUID-PLACEHOLDER,EXAMPLE-GUID-PLACEHOLDER"

m365 spo site recyclebinitem move --siteUrl https://contoso.sharepoint.com/sites/sales --all

```

---

## site-recyclebinitem-remove

### Syntax
```
m365 spo site recyclebinitem remove [options]
```

### Example
```
m365 spo site recyclebinitem remove --siteUrl https://contoso.sharepoint.com/sites/sales --ids "EXAMPLE-GUID-PLACEHOLDER,EXAMPLE-GUID-PLACEHOLDER"

m365 spo site recyclebinitem remove --siteUrl https://contoso.sharepoint.com/sites/sales --ids "EXAMPLE-GUID-PLACEHOLDER,EXAMPLE-GUID-PLACEHOLDER" --force

```

### Remarks
:::warning

Items in the recycle bin will be permanently removed without the ability to restore them.

:::



---

## site-recyclebinitem-restore

### Syntax
```
m365 spo site recyclebinitem restore [options]
```

### Example
```
m365 spo site recyclebinitem restore --siteUrl https://contoso.sharepoint.com/sites/project --ids "EXAMPLE-GUID-PLACEHOLDER,EXAMPLE-GUID-PLACEHOLDER"

m365 spo site recyclebinitem restore --siteUrl https://contoso.sharepoint.com/sites/project --allPrimary

m365 spo site recyclebinitem restore --siteUrl https://contoso.sharepoint.com --allSecondary

m365 spo site recyclebinitem restore --siteUrl https://contoso.sharepoint.com --allPrimary --allSecondary

```

---

## site-remove

### Syntax
```
m365 spo site remove [options]
```

### Example
```
m365 spo site remove --url https://contoso.sharepoint.com/sites/demosite

m365 spo site remove --url https://contoso.sharepoint.com/sites/demosite --skipRecycleBin

m365 spo site remove --url https://contoso.sharepoint.com/sites/demosite --fromRecycleBin

```

### Remarks
If the argument `--fromRecycleBin` is passed, the selected site will be permanently removed even if it's a groupified one.

:::info

To use this command you must be a Global or SharePoint administrator.

:::



---

## sitescript-add

### Syntax
```
m365 spo sitescript add [options]
```

### Example
```
m365 spo sitescript add --title "Contoso" --description "Contoso theme script" --content $script

```

### Remarks
Each time you execute the `spo sitescript add` command, it will create a new site script with a unique ID. Before creating a site script, be sure that another script with the same name doesn't already exist.



---

## sitescript-get

### Syntax
```
m365 spo sitescript get [options]
```

### Example
```
m365 spo sitescript get --id EXAMPLE-GUID-PLACEHOLDER

m365 spo sitescript get --id EXAMPLE-GUID-PLACEHOLDER --content

```

### Remarks
If the specified `id` doesn't refer to an existing site script, you will get a `File not found` error.



---

## sitescript-list

### Syntax
```
m365 spo sitescript list [options]
```

### Example
```
m365 spo sitescript list

```

---

## sitescript-remove

### Syntax
```
m365 spo sitescript remove [options]
```

### Example
```
m365 spo sitescript remove --id EXAMPLE-GUID-PLACEHOLDER

m365 spo sitescript remove --id EXAMPLE-GUID-PLACEHOLDER --force

```

### Remarks
If the specified `id` doesn't refer to an existing site script, you will get a `File not found` error.



---

## sitescript-set

### Syntax
```
m365 spo sitescript set [options]
```

### Example
```
m365 spo sitescript set --id EXAMPLE-GUID-PLACEHOLDER --title "Contoso"

```

### Remarks
If the specified `id` doesn't refer to an existing site script, you will get a `File not found` error.



---

## site-set

### Syntax
```
m365 spo site set [options]
```

### Example
```
m365 spo site set --url https://contoso.sharepoint.com/sites/sales --classification MBI```

### Remarks
If the specified url doesn't refer to an existing site collection, you will get a `404 - "404 FILE NOT FOUND"` error.

The `isPublic` property can be set only on groupified site collections. If you try to set it on a site collection without a group, you will get an error.

When setting owners, the specified owners will be added to the already configured owners. Existing owners will not be removed.

The value of the `--resourceQuota` option must not exceed the company's aggregate available Sandboxed Solutions quota. For more information, see Resource Usage Limits on Sandboxed Solutions in SharePoint 2010: [http://msdn.microsoft.com/en-us/library/gg615462.aspx](http://msdn.microsoft.com/en-us/library/gg615462.aspx).

The value of the `--resourceQuotaWarningLevel` option must not exceed the value of the `--resourceQuota` option or the current value of the _UserCodeMaximumLevel_ property.

The value of the `--storageQuota` option must not exceed the company's available quota.

The value of the `--storageQuotaWarningLevel` option must not exceed the the value of the `--storageQuota` option or the current value of the _StorageMaximumLevel_ property.

For more information on locking sites see [https://technet.microsoft.com/en-us/library/cc263238.aspx](https://technet.microsoft.com/en-us/library/cc263238.aspx).

For more information on configuring no script sites see [https://support.office.com/en-us/article/EXAMPLE_SECRET_VALUE_PLACEHOLDER](https://support.office.com/en-us/article/EXAMPLE_SECRET_VALUE_PLACEHOLDER).

Setting site properties is by default asynchronous and depending on the current state of Microsoft 365, might take up to few minutes. If you're building a script with steps that require the site to be fully configured, you should use the `--wait` flag. When using this flag, the `spo site set` command will keep running until it received confirmation from Microsoft 365 that the site has been fully configured.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## site-sharingpermission-set

### Syntax
```
m365 spo site sharingpermission set [options]
```

### Example
```
m365 spo site sharingpermission set --siteUrl https://siteaddress.com/sites/sitename  --capability ownersOnly

m365 spo site sharingpermission set --siteUrl https://siteaddress.com/sites/sitename  --capability full

m365 spo site sharingpermission set --siteUrl https://siteaddress.com/sites/sitename --capability limited

```

### Remarks
When specifying `capability`, consider the following:



---

## spo-get

### Syntax
```
m365 spo get [options]
```

### Example
```
m365 spo get --output json

```

### Remarks
CLI for Microsoft 365 automatically discovers the URL of the root SharePoint site collection/SharePoint tenant admin site (whichever is needed to run the particular command). Using this command you can see which URLs the CLI has discovered.



---

## spo-search

### Syntax
```
m365 spo search [options]
```

### Example
```
m365 spo search --queryText "ContentTypeId:0x0120D520" --culture 1033

m365 spo search --queryText "IsDocument:1" --selectProperties "Path,Author,FileType" --allResults

m365 spo search --queryText "Title:Marketing*" --rowLimit=50 --trimDuplicates

m365 spo search --queryText "*" --sourceId "EXAMPLE-GUID-PLACEHOLDER"

```

### Remarks
When using the `--allResults` option, you cannot use the `--startRow` option. Only use `--startRow` for manual paging purposes.



---

## spo-set

### Syntax
```
m365 spo set [options]
```

### Example
```
m365 spo set --url https://contoso.sharepoint.com

```

### Remarks
CLI for Microsoft 365 automatically discovers the URL of the root SharePoint site collection/SharePoint tenant admin site (whichever is needed to run the particular command). In specific cases, like when managing multi-geo Microsoft 365 tenants, it could be desirable to make the CLI manage the specific geography. For such cases, you can use this command to explicitly specify the SPO URL that should be used when executing SPO commands.



---

## storageentity-get

### Syntax
```
m365 spo storageentity get [options]
```

### Example
```
m365 spo storageentity get -k AnalyticsId

```

### Remarks
Tenant properties are stored in the app catalog site associated with the site to which you are currently connected. When retrieving the specified tenant property, SharePoint will automatically find the associated app catalog and try to retrieve the property from it.



---

## storageentity-list

### Syntax
```
m365 spo storageentity list [options]
```

### Example
```
m365 spo storageentity list -u https://contoso.sharepoint.com/sites/appcatalog

```

### Remarks
Tenant properties are stored in the app catalog site. To list all tenant properties, you have to specify the absolute URL of the app catalog site. If you specify an incorrect URL, or the site at the given URL is not an app catalog site, no properties will be retrieved.



---

## storageentity-remove

### Syntax
```
m365 spo storageentity remove [options]
```

### Example
```
m365 spo storageentity remove -k AnalyticsId -u https://contoso.sharepoint.com/sites/appcatalog

m365 spo storageentity remove -k AnalyticsId --force -u https://contoso.sharepoint.com/sites/appcatalog

```

### Remarks
Tenant properties are stored in the app catalog site associated with that tenant. To remove a property, you have to specify the absolute URL of the app catalog site. If you specify the URL of a site different than the app catalog, you will get an access denied error.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## storageentity-set

### Syntax
```
m365 spo storageentity set [options]
```

### Example
```
m365 spo storageentity set -k AnalyticsId -v 123 -d 'Web analytics ID' -c 'Use on all sites' -u https://contoso.sharepoint.com/sites/appcatalog

```

### Remarks
Tenant properties are stored in the app catalog site associated with that tenant. To set a property, you have to specify the absolute URL of the app catalog site without a trailing slash. If you specify the URL with trailing slash you get the error `The managed path sites/apps is not a managed path in this tenant.`

If you specify the URL of a site different than the app catalog, you will get an access denied error.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## tenant-appcatalog-add

### Syntax
```
m365 spo tenant appcatalog add [options]
```

### Example
```
m365 spo tenant appcatalog add --url https://contoso.sharepoint.com/sites/apps --owner admin@contoso.com --timeZone 4

m365 spo tenant appcatalog add --url https://contoso.sharepoint.com/sites/apps --owner admin@contoso.com --timeZone 4 --wait

m365 spo tenant appcatalog add --url https://contoso.sharepoint.com/sites/apps --owner admin@contoso.com --timeZone 4 --force

```

### Remarks
If there is an app catalog registered in your tenant, creating a new app catalog using this command will fail, unless you use the `force` option.

If you use the `force` option, and either the app catalog or the site at the specified URL exists (or both), this command will delete both sites bypassing the recycle bin.

Creating an app catalog site might take a while. If you need to wait for the site to be created before continuing, use the `wait` option.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## tenant-appcatalogurl-get

### Syntax
```
m365 spo tenant appcatalogurl get [options]
```

### Example
```
m365 spo tenant appcatalogurl get

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## tenant-applicationcustomizer-add

### Syntax
```
m365 spo tenant applicationcustomizer add [options]
```

### Example
```
m365 spo tenant applicationcustomizer add --title "Some customizer" --clientSideComponentId  EXAMPLE-GUID-PLACEHOLDER 

m365 spo tenant applicationcustomizer add --title "Some customizer" --clientSideComponentId  EXAMPLE-GUID-PLACEHOLDER --webTemplate "SITEPAGEPUBLISHING#0"

```

### Remarks
Running this command from the Windows Command Shell (cmd.exe) or PowerShell for Windows OS XP, 7, 8, 8.1 without bash installed might require additional formatting for command options that have JSON, XML or JavaScript values because the command shell treats quotes differently. For example, this is how ApplicationCustomizer user custom action can be created from the Windows cmd.exe:

Note, how the clientSideComponentProperties option has escaped double quotes `'{\"testMessage\":\"Test message\"}'` compared to execution from bash `'{"testMessage":"Test message"}'`.

:::warning[Escaping JSON in PowerShell]

When using the `--clientSideComponentProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

:::info

To use this command, you need to be a SharePoint Admin.

:::

This command can be used for configuring a tenant-wide application customizer. To configure an application customizer on a specific site, view our dedicated [spo applicationcustomizer add](../applicationcustomizer/applicationcustomizer-add.mdx) command.



---

## tenant-applicationcustomizer-get

### Syntax
```
m365 spo tenant applicationcustomizer get [options]
```

### Example
```
m365 spo tenant applicationcustomizer get --title "Some customizer"

m365 spo tenant applicationcustomizer get --id 3

m365 spo tenant applicationcustomizer get --clientSideComponentId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
This command can be used for retrieving an application customizer that's installed tenant-wide. To retrieve an application customizer from a specific site, view our dedicated [spo applicationcustomizer get](../applicationcustomizer/applicationcustomizer-get.mdx) command.



---

## tenant-applicationcustomizer-list

### Syntax
```
m365 spo tenant applicationcustomizer list [options]
```

### Example
```
m365 spo tenant applicationcustomizer list

```

### Remarks
This command can be used for retrieving a list of tenant-wide installed application customizers. To retrieve a list of application customizers from a specific site, view our dedicated [spo applicationcustomizer list](../applicationcustomizer/applicationcustomizer-list.mdx) command.



---

## tenant-applicationcustomizer-remove

### Syntax
```
m365 spo tenant applicationcustomizer remove [options]
```

### Example
```
m365 spo tenant applicationcustomizer remove --title "Some customizer"

m365 spo tenant applicationcustomizer remove --id 3

m365 spo tenant applicationcustomizer remove --clientSideComponentId "EXAMPLE-GUID-PLACEHOLDER"

```

### Remarks
This command can be used for removing an application customizer that's installed tenant-wide. To remove an application customizer from a specific site, view our dedicated [spo applicationcustomizer remove](../applicationcustomizer/applicationcustomizer-remove.mdx) command.



---

## tenant-applicationcustomizer-set

### Syntax
```
m365 spo tenant applicationcustomizer set [options]
```

### Example
```
m365 spo tenant applicationcustomizer set --id 3 --newTitle "Some customizer" ```

### Remarks
Running this command from the Windows Command Shell (cmd.exe) or PowerShell for Windows OS XP, 7, 8, 8.1 without bash installed might require additional formatting for clientSideComponentProperties option that has JSON value because the command shell treats quotes differently. For example, this is how Application Customizer can be updated from the Windows cmd.exe:

Note, how the clientSideComponentProperties option (--clientSideComponentProperties) has escaped double quotes `'{\"someProperty\":\"Some value\"}'` compared to execution from bash `'{"someProperty": "Some value"}'`.

:::warning[Escaping JSON in PowerShell]

When using the `--clientSideComponentProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

This command can be used for updating an application customizer that's installed tenant-wide. To update an application customizer from a specific site, view our dedicated [spo applicationcustomizer set](../applicationcustomizer/applicationcustomizer-set.mdx) command.



---

## tenant-commandset-add

### Syntax
```
m365 spo tenant commandset add [options]
```

### Example
```
m365 spo tenant commandset add --title "Some customizer" --clientSideComponentId  EXAMPLE-GUID-PLACEHOLDER --listType List

m365 spo tenant commandset  add --title "Some customizer" --clientSideComponentId  EXAMPLE-GUID-PLACEHOLDER --webTemplate "SITEPAGEPUBLISHING#0" --listType Library --location ContextMenu

```

### Remarks
Running this command from the Windows Command Shell (cmd.exe) or PowerShell for Windows OS XP, 7, 8, 8.1 without bash installed might require additional formatting for command options that have JSON, XML, or JavaScript values because the command shell treats quotes differently. For example, this is how commandset user custom action can be created from the Windows cmd.exe:

Note, how the clientSideComponentProperties option has escaped double quotes `'{\"testMessage\":\"Test message\"}'` compared to execution from bash `'{"testMessage":"Test message"}'`.

:::warning[Escaping JSON in PowerShell]

When using the `--clientSideComponentProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

:::info

To use this command, you need to be a SharePoint Admin.

:::

This command can be used for configuring a tenant-wide ListView Command Set. To configure a ListView Command Set on a specific site, view our dedicated [spo commandset add](../commandset/commandset-add.mdx) command.



---

## tenant-commandset-get

### Syntax
```
m365 spo tenant commandset get [options]
```

### Example
```
m365 spo tenant commandset get --title "Some customizer"

m365 spo tenant commandset get --id 3

m365 spo tenant commandset get --clientSideComponentId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
This command can be used for retrieving a ListView Command Set that's installed tenant-wide. To retrieve a ListView Command Set from a specific site, view our dedicated [spo commandset get](../commandset/commandset-get.mdx) command.



---

## tenant-commandset-list

### Syntax
```
m365 spo tenant commandset list [options]
```

### Example
```
m365 spo tenant commandset list

```

### Remarks
This command can be used for retrieving a list of ListView Command Sets that are installed tenant-wide. To retrieve a list of ListView Command Sets added to a specific site, view our dedicated [spo commandset list](../commandset/commandset-list.mdx) command.



---

## tenant-commandset-remove

### Syntax
```
m365 spo tenant commandset remove [options]
```

### Example
```
m365 spo tenant commandset remove --title "Some command set"

m365 spo tenant commandset remove --id 3

m365 spo tenant commandset remove --clientSideComponentId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
This command can be used for removing a ListView Command Set that's installed tenant-wide. To remove a ListView Command Set from a specific site, view our dedicated [spo commandset remove](../commandset/commandset-remove.mdx) command.



---

## tenant-commandset-set

### Syntax
```
m365 spo tenant commandset set [options]
```

### Example
```
m365 spo tenant commandset set --id 4 --newTitle "Some customizer"

m365 spo tenant commandset set --title "Some Command Set" --clientSideComponentProperties '{ "someProperty": "Some value" }'

m365 spo tenant commandset set --clientSideComponentId "EXAMPLE-GUID-PLACEHOLDER" --newClientSideComponentId "EXAMPLE-GUID-PLACEHOLDER"

```

### Remarks
:::warning[Escaping JSON in PowerShell]

When using the `--clientSideComponentProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

This command can be used for updating a ListView Command Set that's installed tenant-wide. To update a ListView Command Set on a specific site, view our dedicated [spo commandset set](../commandset/commandset-set.mdx) command.



---

## tenant-recyclebinitem-list

### Syntax
```
m365 spo tenant recyclebinitem list [options]
```

### Example
```
m365 spo tenant recyclebinitem list

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## tenant-recyclebinitem-remove

### Syntax
```
m365 spo tenant recyclebinitem remove [options]
```

### Example
```
m365 spo tenant recyclebinitem remove --siteUrl https://contoso.sharepoint.com/sites/team

m365 spo tenant recyclebinitem remove --siteUrl https://contoso.sharepoint.com/sites/team --wait

```

### Remarks
Removing a site collection is by default asynchronous and depending on the current state of Microsoft 365, might take up to few minutes. If you're building a script with steps that require the site to be fully removed, you should use the `--wait` flag. When using this flag, the `m365 spo tenant recyclebinitem remove` command will keep running until it received confirmation from Microsoft 365 that the site has been fully removed.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## tenant-recyclebinitem-restore

### Syntax
```
m365 spo tenant recyclebinitem restore [options]
```

### Example
```
m365 spo tenant recyclebinitem restore --siteUrl https://contoso.sharepoint.com/sites/team

```

### Remarks
:::info

To use this command you must be a Global or SharePoint administrator.

:::



---

## tenant-settings-list

### Syntax
```
m365 spo tenant settings list [options]
```

### Example
```
m365 spo tenant settings list

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## tenant-settings-set

### Syntax
```
m365 spo tenant settings set [options]
```

### Example
```
m365 spo tenant settings set --UserVoiceForFeedbackEnabled true```

### Remarks
:::info

To use this command you have to have permission to access the tenant admin site.

:::



---

## tenant-site-archive

### Syntax
```
m365 spo tenant site archive [options]
```

### Example
```
m365 spo tenant site archive --url "https://contoso.sharepoint.com/sites/Marketing"

m365 spo tenant site archive --url "https://contoso.sharepoint.com/sites/Marketing" --force

```

### Remarks
:::info

To use this command, you must be a Global or SharePoint administrator.

:::

:::note

After running this command, it may take a few minutes for the site to be fully archived.

:::



---

## tenant-site-list

### Syntax
```
m365 spo tenant site list [options]
```

### Example
```
m365 spo tenant site list

m365 spo tenant site list --type TeamSite

m365 spo tenant site list --type CommunicationSite

m365 spo tenant site list --type TeamSite --filter "Url -like 'project'"

m365 spo tenant site list --includeOneDriveSites

```

### Remarks
Using the `--filter` option you can specify which sites you want to retrieve. For example, to get sites with _project_ in their URL, use `Url -like 'project'` as the filter.

When using the text output type, the command lists only the values of the `Title`, and `Url` properties of the site. When setting the output type to JSON, all available properties are included in the command output.

If you wish to list deleted sites in your tenant, you should use the command [spo tenant recyclebinitem list](../tenant/tenant-recyclebinitem-list.mdx)

:::info

To use this command you have to have permissions to access the tenant admin site.

:::



---

## tenant-site-membership-list

### Syntax
```
m365 spo tenant site membership list [options]
```

### Example
```
m365 spo tenant site membership list --siteUrl https://contoso.sharepoint.com

m365 spo tenant site membership list --siteUrl https://contoso.sharepoint.com --role Owner

```

### Remarks
:::info

To use this command, you must be a Global or SharePoint administrator.

:::

For other scenarios, refer to the [spo web get --withGroups](../web/web-get.mdx) and [spo group member list](../group/group-member-list.mdx) commands.



---

## tenant-site-rename

### Syntax
```
m365 spo tenant site rename [options]
```

### Example
```
m365 spo tenant site rename --url http://contoso.sharepoint.com/samplesite --newUrl http://contoso.sharepoint.com/renamed

m365 spo tenant site rename --url http://contoso.sharepoint.com/samplesite --newUrl http://contoso.sharepoint.com/renamed --newTitle "New Title"

m365 spo tenant site rename --url http://contoso.sharepoint.com/samplesite --newUrl http://contoso.sharepoint.com/renamed --newTitle "New Title" --wait

```

### Remarks
Renaming site collections is by default asynchronous and depending on the current state of Microsoft 365, might take up to few minutes. If you're building a script with steps that require the operation to complete fully, you should use the `--wait` flag. When using this flag, the `spo tenant site rename` command  will keep running until it receives confirmation from Microsoft 365 that the site rename operation has completed.

:::info

To use this command you must have permissions to access the tenant admin site.

:::



---

## tenant-site-unarchive

### Syntax
```
m365 spo tenant site unarchive [options]
```

### Example
```
m365 spo tenant site unarchive --url "https://contoso.sharepoint.com/sites/Marketing"

m365 spo tenant site unarchive --url "https://contoso.sharepoint.com/sites/Marketing" --force

```

### Remarks
:::info

To use this command, you must be a Global or SharePoint administrator.

:::

:::warning

If a site remains archived for more than **seven days**, the reactivation fee will be calculated based on the entire storage capacity of the site.

:::

:::note

After running this command, it may take a few minutes for the site to be fully restored.

:::



---

## term-add

### Syntax
```
m365 spo term add [options]
```

### Example
```
m365 spo term add --name IT --termSetName Department --termGroupName People```

### Remarks
:::warning[Escaping JSON in PowerShell]

When using the `--customProperties` and/or `--localCustomProperties` options it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

:::info

To use this command without the `--webUrl` option you have to have permissions to access the tenant admin site.

:::

When using the `--webUrl` option you can connect to the term store with limited permissions, and do not need the SharePoint Administrator role. It allows you to add a term to a term set in the tenant term store if you are listed as a term store administrator. It allows you to add terms to a term set in the sitecollection term store if you are a site owner.



---

## term-get

### Syntax
```
m365 spo term get [options]
```

### Example
```
m365 spo term get --webUrl https://contoso.sharepoint.com/sites/project-x --id EXAMPLE-GUID-PLACEHOLDER

m365 spo term get --id EXAMPLE-GUID-PLACEHOLDER

m365 spo term get --name IT --termGroupName People --termSetName Department

m365 spo term get --name IT --termGroupId EXAMPLE-GUID-PLACEHOLDER --termSetId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
When retrieving term by its ID, it's sufficient to specify just the ID. When retrieving it by its name however, you need to specify the parent term group and term set using either their names or IDs.

:::info

To use this command without the --webUrl option you have to have permissions to access the tenant admin site.

:::

When using the `--webUrl` option you can connect to the term store with limited permissions, and do not need the SharePoint Administrator role. You need to be a site visitor or more. It allows you to get a term from the tenant term store as well as a term from the sitecollection term store.



---

## term-group-add

### Syntax
```
m365 spo term group add [options]
```

### Example
```
m365 spo term group add --name PnPTermSets

m365 spo term group add --name PnPTermSets --id EXAMPLE-GUID-PLACEHOLDER

m365 spo term group add --name PnPTermSets --description 'Term sets for PnP' --webUrl 'https://contoso.sharepoint.com'

```

### Remarks
:::warning

To use this command without the `--webUrl` option you must have permissions to access the tenant admin site.

When using the `--webUrl` option you can connect to the term store with limited permissions, and do not need the SharePoint Adminstrator role. It allows you to add a term group to the tenant term store if you are listed as a term store administrator.

This command does not create a sitecollection specific term store/group when using the `--webUrl` option.

:::



---

## term-group-get

### Syntax
```
m365 spo term group get [options]
```

### Example
```
m365 spo term group get --id EXAMPLE-GUID-PLACEHOLDER

m365 spo term group get --name PnPTermSets

m365 spo term group get --id EXAMPLE-GUID-PLACEHOLDER --webUrl https://contoso.sharepoint.com/sites/project-x

```

### Remarks
:::info

To use this command without the `--webUrl` option you have to have permissions to access the tenant admin site.

:::

When using the `--webUrl` option you can connect to the term store with limited permissions, and do not need the SharePoint Administrator role. You need to be a site visitor or more. It allows you to get a term group from the tenant term store as well as a term group from the sitecollection term store.



---

## term-group-list

### Syntax
```
m365 spo term group list [options]
```

### Example
```
m365 spo term group list

m365 spo term group list --webUrl https://contoso.sharepoint.com/sites/project-x

```

### Remarks
:::info

To use this command without the --webUrl option you have to have permissions to access the tenant admin site.

:::

When using the `--webUrl` option you can connect to the term store with limited permissions, and do not need the SharePoint Administrator role. You need to be a site visitor or more. It allows you to list term groups from the tenant term store as well as term groups from the sitecollection term store.



---

## term-list

### Syntax
```
m365 spo term list [options]
```

### Example
```
m365 spo term list --webUrl https://contoso.sharepoint.com/sites/project-x --termGroupName PnPTermSets --termSetName PnP-Organizations

m365 spo term list --termGroupName PnPTermSets --termSetName PnP-Organizations

m365 spo term list --termGroupId EXAMPLE-GUID-PLACEHOLDER --termSetId EXAMPLE-GUID-PLACEHOLDER

m365 spo term list --termGroupId EXAMPLE-GUID-PLACEHOLDER --termSetId EXAMPLE-GUID-PLACEHOLDER --includeChildTerms

```

### Remarks
:::info

To use this command without the --webUrl option you have to have permissions to access the tenant admin site.

:::

When using the `--webUrl` option you can connect to the term store with limited permissions, and do not need the SharePoint Administrator role. You need to be a site visitor or more. It allows you to list terms from the tenant term store as well as terms from the sitecollection term store.



---

## term-set-add

### Syntax
```
m365 spo term set add [options]
```

### Example
```
m365 spo term set add --name PnP-Organizations --termGroupId EXAMPLE-GUID-PLACEHOLDER```

### Remarks
:::warning[Escaping JSON in PowerShell]

When using the `--customProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

:::info

To use this command without the `--webUrl` option you have to have permissions to access the tenant admin site.

:::

When using the `--webUrl` option you can connect to the term store with limited permissions, and do not need the SharePoint Administrator role. You need to be a site visitor or more. It allows you to add a term set to a term group in the tenant term store if you are listed as a term store administrator. It allows you to add a term set to a term group in the sitecollection term store if you are a site owner.



---

## term-set-get

### Syntax
```
m365 spo term set get [options]
```

### Example
```
m365 spo term set get --id EXAMPLE-GUID-PLACEHOLDER --termGroupName PnPTermSets

m365 spo term set get --name PnP-Organizations --termGroupId EXAMPLE-GUID-PLACEHOLDER

m365 spo term set get --id EXAMPLE-GUID-PLACEHOLDER --termGroupName PnPTermSets --webUrl https://contoso.sharepoint.com/sites/project-x

```

### Remarks
:::info

To use this command without the --webUrl option you have to have permissions to access the tenant admin site.

:::

When using the `--webUrl` option you can connect to the term store with limited permissions, and do not need the SharePoint Administrator role. You need to be a site visitor or more. It allows you to get a term set from the tenant term store as well as a term set from the sitecollection term store.



---

## term-set-list

### Syntax
```
m365 spo term set list [options]
```

### Example
```
m365 spo term set list --termGroupName PnPTermSets

m365 spo term set list --termGroupId EXAMPLE-GUID-PLACEHOLDER

m365 spo term set list --termGroupName PnPTermSets --webUrl https://contoso.sharepoint.com/sites/project-x

```

### Remarks
:::info

To use this command without the --webUrl option you have to have permissions to access the tenant admin site.

:::

When using the `--webUrl` option you can connect to the term store with limited permissions, and do not need the SharePoint Administrator role. You need to be a site visitor or more. It allows you to list term sets from the tenant term store as well as term sets from the sitecollection term store.



---

## theme-apply

### Syntax
```
m365 spo theme apply [options]
```

### Example
```
m365 spo theme apply --name Contoso-Blue --webUrl https://contoso.sharepoint.com/sites/project-x

m365 spo theme apply --name Blue --webUrl https://contoso.sharepoint.com/sites/project-x --sharePointTheme

```

### Remarks
Following standard SharePoint themes are supported by the CLI for Microsoft 365: Blue, Orange, Red, Purple, Green, Gray, Dark Yellow and Dark Blue.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## theme-get

### Syntax
```
m365 spo theme get [options]
```

### Example
```
m365 spo theme get --name Contoso-Blue

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## theme-list

### Syntax
```
m365 spo theme list [options]
```

### Example
```
m365 spo theme list

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## theme-remove

### Syntax
```
m365 spo theme remove [options]
```

### Example
```
m365 spo theme remove --name Contoso-Blue

m365 spo theme remove --name Contoso-Blue --force

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## theme-set

### Syntax
```
m365 spo theme set [options]
```

### Example
```
m365 spo theme set --name Contoso-Blue --theme @/Users/user/themes/contoso-blue.json```

### Remarks
To prevent the accidental creation of invalid themes the CLI for Microsoft 365 implements a set of checks. These checks are executed against the provided json file. A valid theme JSON file is as follows:

When executing the `m365 spo theme set` command the following checks are executed:

If any of these checks fails you are presented with a `The specified theme is not valid` error.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## user-ensure

### Syntax
```
m365 spo user ensure [options]
```

### Example
```
m365 spo user ensure --webUrl https://contoso.sharepoint.com/sites/project --entraId EXAMPLE-GUID-PLACEHOLDER```

---

## user-get

### Syntax
```
m365 spo user get [options]
```

### Example
```
m365 spo user get --webUrl https://contoso.sharepoint.com/sites/project-x --email john.doe@mytenant.onmicrosoft.com```

---

## user-list

### Syntax
```
m365 spo user list [options]
```

### Example
```
m365 spo user list --webUrl https://contoso.sharepoint.com/sites/project-x

```

---

## userprofile-get

### Syntax
```
m365 spo userprofile get [options]
```

### Example
```
m365 spo userprofile get --userName 'john.doe@mytenant.onmicrosoft.com'

```

### Remarks
You have to have tenant admin permissions in order to use this command to get profile properties of other users.



---

## userprofile-set

### Syntax
```
m365 spo userprofile set [options]
```

### Example
```
m365 spo userprofile set --userName 'john.doe@mytenant.onmicrosoft.com' --propertyName 'AboutMe' --propertyValue 'Working as a Microsoft 365 developer'

m365 spo userprofile set --userName 'john.doe@mytenant.onmicrosoft.com' --propertyName 'SPS-Skills' --propertyValue 'CSS, HTML'

```

### Remarks
You have to have tenant admin permissions in order to use this command to update profile properties of other users.



---

## user-remove

### Syntax
```
m365 spo user remove [options]
```

### Example
```
m365 spo user remove --webUrl "https://contoso.sharepoint.com/sites/HR" --id 10 --force```

---

## web-add

### Syntax
```
m365 spo web add [options]
```

### Example
```
m365 spo web add --title Subsite --description Subsite --url subsite --webTemplate STS#0 --parentWebUrl https://contoso.sharepoint.com --locale 1033

m365 spo web add --title Subsite --url subsite --webTemplate STS#0 --parentWebUrl https://contoso.sharepoint.com --breakInheritance

m365 spo web add --title Subsite --url subsite --webTemplate STS#0 --parentWebUrl https://contoso.sharepoint.com --inheritNavigation

```

---

## web-clientsidewebpart-list

### Syntax
```
m365 spo web clientsidewebpart list [options]
```

### Example
```
m365 spo web clientsidewebpart list --webUrl https://contoso.sharepoint.com

```

---

## web-get

### Syntax
```
m365 spo web get [options]
```

### Example
```
m365 spo web get --url https://contoso.sharepoint.com/subsite

m365 spo web get --url https://contoso.sharepoint.com/subsite --withGroups

m365 spo web get --url https://contoso.sharepoint.com/subsite --withPermissions

```

---

## web-installedlanguage-list

### Syntax
```
m365 spo web installedlanguage list [options]
```

### Example
```
m365 spo web installedlanguage list --webUrl https://contoso.sharepoint.com

```

---

## web-list

### Syntax
```
m365 spo web list [options]
```

### Example
```
m365 spo web list --url https://contoso.sharepoint.com

```

---

## web-reindex

### Syntax
```
m365 spo web reindex [options]
```

### Example
```
m365 spo web reindex --url https://contoso.sharepoint.com/subsite

```

### Remarks
If the subsite to be reindexed is a no-script site, the command will request reindexing all lists from the subsite that haven't been excluded from the search index.



---

## web-remove

### Syntax
```
m365 spo web remove [options]
```

### Example
```
m365 spo web remove --url https://contoso.sharepoint.com/subsite --force

```

---

## web-retentionlabel-list

### Syntax
```
m365 spo web retentionlabel list [options]
```

### Example
```
m365 spo web retentionlabel list --webUrl 'https://contoso.sharepoint.com/sites/sales'

```

---

## web-roleassignment-add

### Syntax
```
m365 spo web roleassignment add [options]
```

### Example
```
m365 spo web roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --principalId 11 --roleDefinitionId 1073741829```

---

## web-roleassignment-remove

### Syntax
```
m365 spo web roleassignment remove [options]
```

### Example
```
m365 spo web roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales"  --groupName "saleGroup"```

---

## web-roleinheritance-break

### Syntax
```
m365 spo web roleinheritance break [options]
```

### Example
```
m365 spo web roleinheritance break --webUrl https://contoso.sharepoint.com/sites/project-x

m365 spo web roleinheritance break --webUrl https://contoso.sharepoint.com/sites/project-x --clearExistingPermissions

```

### Remarks
By default, when breaking permissions inheritance, the web will retain existing permissions. To remove existing permissions, use the `--clearExistingPermissions` option.



---

## web-roleinheritance-reset

### Syntax
```
m365 spo web roleinheritance reset [options]
```

### Example
```
m365 spo web roleinheritance reset --webUrl https://contoso.sharepoint.com/sites/project-x

m365 spo web roleinheritance reset --webUrl https://contoso.sharepoint.com/sites/project-x --force

```

---

## web-set

### Syntax
```
m365 spo web set [options]
```

### Example
```
m365 spo web set --url https://contoso.sharepoint.com/sites/team-a --title Team-a```

### Remarks
Next to updating web properties corresponding to the options of this command, you can update the value of any other web property using its CSOM name, eg. `--AllowAutomaticASPXPageIndexing`. At this moment, the CLI supports properties of types `Boolean`, `String` and `Int32`.



---
