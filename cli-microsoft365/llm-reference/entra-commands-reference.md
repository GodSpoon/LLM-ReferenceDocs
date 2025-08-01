<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - ENTRA Commands Reference

*This is an automatically generated condensed reference of all ENTRA commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-08-01*

---

## Table of Contents

- [administrativeunit-add](#administrativeunit-add)
- [administrativeunit-get](#administrativeunit-get)
- [administrativeunit-list](#administrativeunit-list)
- [administrativeunit-member-add](#administrativeunit-member-add)
- [administrativeunit-member-get](#administrativeunit-member-get)
- [administrativeunit-member-list](#administrativeunit-member-list)
- [administrativeunit-member-remove](#administrativeunit-member-remove)
- [administrativeunit-remove](#administrativeunit-remove)
- [administrativeunit-roleassignment-add](#administrativeunit-roleassignment-add)
- [app-add](#app-add)
- [app-get](#app-get)
- [app-list](#app-list)
- [app-permission-add](#app-permission-add)
- [app-permission-list](#app-permission-list)
- [app-permission-remove](#app-permission-remove)
- [app-remove](#app-remove)
- [app-role-add](#app-role-add)
- [approleassignment-add](#approleassignment-add)
- [approleassignment-list](#approleassignment-list)
- [approleassignment-remove](#approleassignment-remove)
- [app-role-list](#app-role-list)
- [app-role-remove](#app-role-remove)
- [app-set](#app-set)
- [enterpriseapp-add](#enterpriseapp-add)
- [enterpriseapp-get](#enterpriseapp-get)
- [enterpriseapp-list](#enterpriseapp-list)
- [enterpriseapp-remove](#enterpriseapp-remove)
- [group-add](#group-add)
- [group-get](#group-get)
- [group-list](#group-list)
- [group-member-add](#group-member-add)
- [group-member-list](#group-member-list)
- [group-member-remove](#group-member-remove)
- [group-member-set](#group-member-set)
- [group-remove](#group-remove)
- [group-set](#group-set)
- [groupsetting-add](#groupsetting-add)
- [groupsetting-get](#groupsetting-get)
- [groupsetting-list](#groupsetting-list)
- [groupsetting-remove](#groupsetting-remove)
- [groupsetting-set](#groupsetting-set)
- [groupsettingtemplate-get](#groupsettingtemplate-get)
- [groupsettingtemplate-list](#groupsettingtemplate-list)
- [license-list](#license-list)
- [m365group-add](#m365group-add)
- [m365group-conversation-list](#m365group-conversation-list)
- [m365group-conversation-post-list](#m365group-conversation-post-list)
- [m365group-get](#m365group-get)
- [m365group-list](#m365group-list)
- [m365group-recyclebinitem-clear](#m365group-recyclebinitem-clear)
- [m365group-recyclebinitem-list](#m365group-recyclebinitem-list)
- [m365group-recyclebinitem-remove](#m365group-recyclebinitem-remove)
- [m365group-recyclebinitem-restore](#m365group-recyclebinitem-restore)
- [m365group-remove](#m365group-remove)
- [m365group-renew](#m365group-renew)
- [m365group-report-activitycounts](#m365group-report-activitycounts)
- [m365group-report-activitydetail](#m365group-report-activitydetail)
- [m365group-report-activityfilecounts](#m365group-report-activityfilecounts)
- [m365group-report-activitygroupcounts](#m365group-report-activitygroupcounts)
- [m365group-report-activitystorage](#m365group-report-activitystorage)
- [m365group-set](#m365group-set)
- [m365group-teamify](#m365group-teamify)
- [m365group-user-add](#m365group-user-add)
- [m365group-user-list](#m365group-user-list)
- [m365group-user-remove](#m365group-user-remove)
- [m365group-user-set](#m365group-user-set)
- [multitenant-add](#multitenant-add)
- [multitenant-get](#multitenant-get)
- [multitenant-remove](#multitenant-remove)
- [multitenant-set](#multitenant-set)
- [oauth2grant-add](#oauth2grant-add)
- [oauth2grant-list](#oauth2grant-list)
- [oauth2grant-remove](#oauth2grant-remove)
- [oauth2grant-set](#oauth2grant-set)
- [organization-list](#organization-list)
- [organization-set](#organization-set)
- [pim-role-assignment-add](#pim-role-assignment-add)
- [pim-role-assignment-eligibility-list](#pim-role-assignment-eligibility-list)
- [pim-role-assignment-list](#pim-role-assignment-list)
- [pim-role-assignment-remove](#pim-role-assignment-remove)
- [pim-role-request-list](#pim-role-request-list)
- [policy-list](#policy-list)
- [resourcenamespace-list](#resourcenamespace-list)
- [roledefinition-add](#roledefinition-add)
- [roledefinition-get](#roledefinition-get)
- [roledefinition-list](#roledefinition-list)
- [roledefinition-remove](#roledefinition-remove)
- [roledefinition-set](#roledefinition-set)
- [rolepermission-list](#rolepermission-list)
- [siteclassification-disable](#siteclassification-disable)
- [siteclassification-enable](#siteclassification-enable)
- [siteclassification-get](#siteclassification-get)
- [siteclassification-set](#siteclassification-set)
- [user-add](#user-add)
- [user-get](#user-get)
- [user-groupmembership-list](#user-groupmembership-list)
- [user-guest-add](#user-guest-add)
- [user-hibp](#user-hibp)
- [user-license-add](#user-license-add)
- [user-license-list](#user-license-list)
- [user-license-remove](#user-license-remove)
- [user-list](#user-list)
- [user-password-validate](#user-password-validate)
- [user-recyclebinitem-clear](#user-recyclebinitem-clear)
- [user-recyclebinitem-list](#user-recyclebinitem-list)
- [user-recyclebinitem-remove](#user-recyclebinitem-remove)
- [user-recyclebinitem-restore](#user-recyclebinitem-restore)
- [user-registrationdetails-list](#user-registrationdetails-list)
- [user-remove](#user-remove)
- [user-session-revoke](#user-session-revoke)
- [user-set](#user-set)
- [user-signin-list](#user-signin-list)

---

## administrativeunit-add

### Syntax
```
m365 entra administrativeunit add [options]
```

### Example
```
m365 entra administrativeunit add --displayName 'Marketing Division'

m365 entra administrativeunit add --displayName 'Marketing Division' --description 'Marketing department administration'

m365 entra administrativeunit add --displayName 'Marketing Division' --hiddenMembership

```

### Remarks
:::info

To use this command you must be either **Global Administrator** or **Privileged Role Administrator**.

:::



---

## administrativeunit-get

### Syntax
```
m365 entra administrativeunit get [options]
```

### Example
```
m365 entra administrativeunit get --id EXAMPLE-GUID-PLACEHOLDER

m365 entra administrativeunit get --displayName "Marketing Division" --properties "id,displayName"

```

### Remarks
Using the `--properties` option, you can specify a comma-separated list of administrative unit properties to retrieve from the Microsoft Graph. If you don't specify any properties, the command will output the default properties returned by Graph.



---

## administrativeunit-list

### Syntax
```
m365 entra administrativeunit list [options]
```

### Example
```
m365 entra administrativeunit list

m365 entra administrativeunit list --properties "id,displayName"

```

### Remarks
Using the `--properties` option, you can specify a comma-separated list of administrative unit properties to retrieve from the Microsoft Graph. If you don't specify any properties, the command will output the default properties returned by Graph.



---

## administrativeunit-member-add

### Syntax
```
m365 entra administrativeunit member add [options]
```

### Example
```
m365 entra administrativeunit member add --administrativeUnitId EXAMPLE-GUID-PLACEHOLDER --userId EXAMPLE-GUID-PLACEHOLDER```

### Remarks
:::info

To use this command you must be either **Global Administrator** or **Privileged Role Administrator**.

:::



---

## administrativeunit-member-get

### Syntax
```
m365 entra administrativeunit member get [options]
```

### Example
```
m365 entra administrativeunit member get --id EXAMPLE-GUID-PLACEHOLDER --administrativeUnitId EXAMPLE-GUID-PLACEHOLDER 

m365 entra administrativeunit member get --id EXAMPLE-GUID-PLACEHOLDER --administrativeUnitName 'Marketing Division' 

```

### Remarks
To get the member of a hidden membership in an administrative unit, the `Member.Read.Hidden` permission is required.

When the `properties` option includes values with a `/`, for example: `manager/displayName`, an additional `$expand` query parameter will be included on manager.



---

## administrativeunit-member-list

### Syntax
```
m365 entra administrativeunit member list [options]
```

### Example
```
m365 entra administrativeunit member list --administrativeUnitId EXAMPLE-GUID-PLACEHOLDER```

### Remarks
To list the members of a hidden membership in an administrative unit, the `Member.Read.Hidden` permission is required.

When the `properties` option includes values with a `/`, for example: `manager/displayName`, an additional `$expand` query parameter will be included on manager.



---

## administrativeunit-member-remove

### Syntax
```
m365 entra administrativeunit member remove [options]
```

### Example
```
m365 entra administrativeunit member remove --id EXAMPLE-GUID-PLACEHOLDER --administrativeUnitId EXAMPLE-GUID-PLACEHOLDER```

### Remarks
:::info

To use this command you must be either **Global Administrator** or **Privileged Role Administrator**.

:::



---

## administrativeunit-remove

### Syntax
```
m365 entra administrativeunit remove [options]
```

### Example
```
m365 entra administrativeunit remove --id EXAMPLE-GUID-PLACEHOLDER

m365 entra administrativeunit remove --displayName 'Marketing Division'

```

### Remarks
:::info

To use this command you must be either **Global Administrator** or **Privileged Role Administrator**.

:::



---

## administrativeunit-roleassignment-add

### Syntax
```
m365 entra administrativeunit roleassignment add [options]
```

### Example
```
m365 entra administrativeunit roleassignment add --administrativeUnitId EXAMPLE-GUID-PLACEHOLDER --roleDefinitionId EXAMPLE-GUID-PLACEHOLDER --userId EXAMPLE-GUID-PLACEHOLDER

m365 entra administrativeunit roleassignment add --administrativeUnitName 'Marketing Division' --roleDefinitionName 'License Administrator' --userName 'john.doe@contoso.com'

```

### Remarks
:::info

To use this command you must be either **Global Administrator** or **Privileged Role Administrator**.

:::



---

## app-add

### Syntax
```
m365 entra app add [options]
```

### Example
```
m365 entra app add --name 'My Entra app'```

### Remarks
You can use this command to create a new Entra app registration either by specifying the different configuration settings through the corresponding options or by using the manifest.

If you don't use the manifest, you must specify the name of the Entra app registration using the `name` option. If you use the manifest, you can skip the `name` option assuming the manifest contains the `displayName` property.

You can also use the manifest to provision some of the configuration settings of your Entra app. All properties specified in the manifest are optional and will set if specified.

If you specify the manifest along with some options, values specified in the options will override settings from the manifest. One exception is the name specified in the `name` option which will be overridden by the `displayName` property from the manifest if specified.

The following properties specified in the manifest retrieved from Entra ID are not supported by this command:

When specifying the value for the `uri`, you can use the `_appId_` token, to include the ID of the newly generated Entra app registration in the Application ID URI, eg. URI `api://caf406b91cd4.ngrok.io/_appId_` will become `api://caf406b91cd4.ngrok.io/EXAMPLE-GUID-PLACEHOLDER` where the last portion is the app ID of the created Entra app registration.

When using the `withSecret` option, this command will automatically generate a secret named `Default` and set it to expire 1 year in the future.

After creating the Entra app registration, this command returns the app ID and object ID of the created app registration. If you used the `withSecret` option, it will also return the generated secret.

If you want to store the information about the created Entra app registration, use the `--save` option. This is useful when you build solutions connected to Microsoft 365 and want to easily manage app registrations used with your solution. When you use the `--save` option, after you create the app registration, the command will write its ID and name to the `.m365rc.json` file in the current directory. If the file already exists, it will add the information about the to it, allowing you to track multiple apps. If the file doesn't exist, the command will create it.

When specifying `--grantAdminConsent` option, an enterprise application will be created for the app registration.



---

## app-get

### Syntax
```
m365 entra app get [options]
```

### Example
```
m365 entra app get --appId EXAMPLE-GUID-PLACEHOLDER

m365 entra app get --objectId EXAMPLE-GUID-PLACEHOLDER

m365 entra app get --name "My app" --properties "appId,displayName"

m365 entra app get --name "My app" --save

```

### Remarks
For best performance use the `objectId` option to reference the Entra application registration to get. If you use `appId` or `name`, this command will first need to find the corresponding object ID for that application.

If the command finds multiple Entra application registrations with the specified app name, it will prompt you to disambiguate which app it should use, listing the discovered object IDs.

If you want to store the information about the Entra app registration, use the `--save` option. This is useful when you build solutions connected to Microsoft 365 and want to easily manage app registrations used with your solution. When you use the `--save` option, after you get the app registration, the command will write its ID and name to the `.m365rc.json` file in the current directory. If the file already exists, it will add the information about the App registration to it if it's not already present, allowing you to track multiple apps. If the file doesn't exist, the command will create it.

Using the `--properties` option, you can specify a comma-separated list of app properties to retrieve from the Microsoft Graph. If you don't specify any properties, the command will output the default properties returned by Graph.



---

## app-list

### Syntax
```
m365 entra app list [options]
```

### Example
```
m365 entra app list

m365 entra app list --properties "appId,displayName"

```

### Remarks
Using the `--properties` option, you can specify a comma-separated list of app properties to retrieve from the Microsoft Graph. If you don't specify any properties, the command will output the default properties returned by Graph.



---

## app-permission-add

### Syntax
```
m365 entra app permission add [options]
```

### Example
```
m365 entra app permission add --appId 'EXAMPLE-GUID-PLACEHOLDER' --delegatedPermissions 'https://management.azure.com/user_impersonation https://service.flow.microsoft.com/Flows.Read.All https://graph.microsoft.com/Agreement.Read.All'```

### Remarks
Scopes/Roles to grant must be fully-qualified so that we can disambiguate them between the different resources.



---

## app-permission-list

### Syntax
```
m365 entra app permission list [options]
```

### Example
```
m365 entra app permission list --appId 'EXAMPLE-GUID-PLACEHOLDER'

m365 entra app permission list --appName 'Contoso App'

m365 entra app permission list --appObjectId 'EXAMPLE-GUID-PLACEHOLDER' --type delegated

```

### Remarks
For best performance use the `objectId` option to reference the Entra application registration to get. If you use `appId`, this command will first need to find the corresponding object ID for that application.



---

## app-permission-remove

### Syntax
```
m365 entra app permission remove [options]
```

### Example
```
m365 entra app permission remove --appId 'EXAMPLE-GUID-PLACEHOLDER' --delegatedPermissions 'https://management.azure.com/user_impersonation https://service.flow.microsoft.com/Flows.Read.All https://graph.microsoft.com/Agreement.Read.All'

m365 entra app permission remove --appId 'EXAMPLE-GUID-PLACEHOLDER' --applicationPermissions 'https://graph.microsoft.com/Sites.FullControl.All https://microsoft.sharepoint-df.com/Sites.FullControl.All' --revokeAdminConsent

```

### Remarks
Removing permissions on App Registrations does not immediately remove consent given by an administrator. Explicitly instruct the CLI to revoke consent by using the `--revokeAdminConsent` flag.



---

## app-remove

### Syntax
```
m365 entra app remove [options]
```

### Example
```
m365 entra app remove --appId EXAMPLE-GUID-PLACEHOLDER

m365 entra app remove --objectId EXAMPLE-GUID-PLACEHOLDER

m365 entra app remove --name "My app" --force

```

### Remarks
For best performance use the `objectId` option to reference the Entra application registration to remove. If you use `appId` or `name`, this command will first need to find the corresponding object ID for that application.

If the command finds multiple Entra application registrations with the specified app name, it will prompt you to disambiguate which app it should use, listing the discovered object IDs.



---

## app-role-add

### Syntax
```
m365 entra app role add [options]
```

### Example
```
m365 entra app role add --appObjectId EXAMPLE-GUID-PLACEHOLDER --name Managers --description "Managers" --allowedMembers usersGroups --claim managers

m365 entra app role add --appId EXAMPLE-GUID-PLACEHOLDER --name Managers --description "Managers" --allowedMembers usersGroups --claim managers

m365 entra app role add --appName "My app" --name Managers --description "Managers" --allowedMembers usersGroups --claim managers

```

### Remarks
For best performance use the `appObjectId` option to reference the Entra application registration for which to add the role. If you use `appId` or `appName`, this command will first need to find the corresponding object ID for that application.

If the command finds multiple Entra application registrations with the specified app name, it will prompt you to disambiguate which app it should use, listing the discovered object IDs.



---

## approleassignment-add

### Syntax
```
m365 entra approleassignment add [options]
```

### Example
```
m365 entra approleassignment add --appId "EXAMPLE-GUID-PLACEHOLDER" --resource "SharePoint" --scopes "Sites.Read.All"

m365 entra approleassignment add --appDisplayName "MyAppName" --resource "Microsoft Graph" --scopes "Mail.Read,Mail.Send"

m365 entra approleassignment add --appObjectId "EXAMPLE-GUID-PLACEHOLDER" --resource "Microsoft Graph" --scopes "Mail.Read"

```

### Remarks
This command requires tenant administrator permissions.

Specify either the `appId`, `appObjectId` or `appDisplayName` but not multiple. If you specify more than one option value, the command will fail with an error.

Autocomplete values for the `resource` option do not mean allowed values. The autocomplete will just suggest some known names, but that doesn't restrict you to use the name of your own custom application or other application within your tenant.

This command can also be used to assign permissions to system or user-assigned managed identity.



---

## approleassignment-list

### Syntax
```
m365 entra approleassignment list [options]
```

### Example
```
m365 entra approleassignment list --appId EXAMPLE-GUID-PLACEHOLDER

m365 entra approleassignment list --appDisplayName 'MyAppName'

m365 entra approleassignment list --appObjectId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
Specify either the `appId`, `appObjectId` or `appDisplayName`. If you specify more than one option value, the command will fail with an error.



---

## approleassignment-remove

### Syntax
```
m365 entra approleassignment remove [options]
```

### Example
```
m365 entra approleassignment remove --appId "EXAMPLE-GUID-PLACEHOLDER" --resource "SharePoint" --scopes "Sites.Read.All"

m365 entra approleassignment remove --appDisplayName "MyAppName" --resource "Microsoft Graph" --scopes "Mail.Read,Mail.Send"

m365 entra approleassignment remove --appObjectId "EXAMPLE-GUID-PLACEHOLDER" --resource "Microsoft Graph" --scopes "Mail.Read"

```

### Remarks
This command requires tenant administrator permissions.

Specify either the `appId`, `appObjectId` or `appDisplayName` but not multiple. If you specify more than one option value, the command will fail with an error.

Autocomplete values for the `resource` option do not mean allowed values. The autocomplete will just suggest some known names, but that doesn't restrict you to use name of your own custom application or other application within your tenant.

This command can also be used to assign permissions to system- or user-assigned managed identity.



---

## app-role-list

### Syntax
```
m365 entra app role list [options]
```

### Example
```
m365 entra app role list --appObjectId EXAMPLE-GUID-PLACEHOLDER

m365 entra app role list --appId EXAMPLE-GUID-PLACEHOLDER

m365 entra app role list --appName "My app"

```

### Remarks
For best performance use the `appObjectId` option to reference the Entra application registration for which to retrieve roles. If you use `appId` or `appName`, this command will first need to find the corresponding object ID for that application.

If the command finds multiple Entra application registrations with the specified app name, it will prompt you to disambiguate which app it should use, listing the discovered object IDs.



---

## app-role-remove

### Syntax
```
m365 entra app role remove [options]
```

### Example
```
m365 entra app role remove --appObjectId EXAMPLE-GUID-PLACEHOLDER --name "Get Product"

m365 entra app role remove --appId EXAMPLE-GUID-PLACEHOLDER --claim "Product.Get"

m365 entra app role remove --appName "My app" --claim "Product.Get"

m365 entra app role remove --appObjectId EXAMPLE-GUID-PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER --force

```

### Remarks
For best performance use the `appObjectId` option to reference the Entra application registration from which to remove the role. If you use `appId` or `appName`, this command will first need to find the corresponding object ID for that application.

If the command finds multiple Entra application registrations with the specified app name, it will prompt you to disambiguate which app it should use, listing the discovered object IDs.

If the command finds multiple roles with the specified role name, it will prompt you to disambiguate which role it should use, listing the claim values.

If the role to be removed is 'Enabled', this command will disable the role first and then remove.



---

## app-set

### Syntax
```
m365 entra app set [options]
```

### Example
```
m365 entra app set --objectId EXAMPLE-GUID-PLACEHOLDER --uris https://contoso.com/EXAMPLE-GUID-PLACEHOLDER```

### Remarks
For best performance use the `objectId` option to reference the Entra application registration to update. If you use `appId` or `name`, this command will first need to find the corresponding object ID for that application.

If the command finds multiple Entra application registrations with the specified app name, it will prompt you to disambiguate which app it should use, listing the discovered object IDs.

When a certificate is specified it will be added to the list of certificates of the app without changing existing certificates.



---

## enterpriseapp-add

### Syntax
```
m365 entra enterpriseapp add [options]
```

### Example
```
m365 entra enterpriseapp add --id EXAMPLE-GUID-PLACEHOLDER

m365 entra enterpriseapp add --displayName "Microsoft Graph"

m365 entra enterpriseapp add --objectId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
Specify either the `id`, `displayName` or `objectId`. If you specify more than one option value, the command will fail with an error.

If you register an application in the portal, an application object as well as an enterprise application object are automatically created in your home tenant. If you register an application using CLI for Microsoft 365 or the Microsoft Graph, you'll need to create the enterprise application separately. To register/create an application using the CLI for Microsoft 365, use the [m365 entra app add](../app/app-add.mdx) command.



---

## enterpriseapp-get

### Syntax
```
m365 entra enterpriseapp get [options]
```

### Example
```
m365 entra enterpriseapp get --id EXAMPLE-GUID-PLACEHOLDER

m365 entra enterpriseapp get --displayName "Microsoft Graph"

m365 entra enterpriseapp get --objectId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
Specify either the `id`, `objectId` or `displayName`. If you specify more than one option value, the command will fail with an error.



---

## enterpriseapp-list

### Syntax
```
m365 entra enterpriseapp list [options]
```

### Example
```
m365 entra enterpriseapp list

m365 entra enterpriseapp list --displayName "My custom enterprise application" --tag "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

```

---

## enterpriseapp-remove

### Syntax
```
m365 entra enterpriseapp remove [options]
```

### Example
```
m365 entra enterpriseapp remove --id EXAMPLE-GUID-PLACEHOLDER --force

m365 entra enterpriseapp remove --displayName "Contoso app"

m365 entra enterpriseapp remove --objectId EXAMPLE-GUID-PLACEHOLDER

```

---

## group-add

### Syntax
```
m365 entra group add [options]
```

### Example
```
m365 entra group add --displayName Developers --type security

m365 entra group add --displayName Developers --type microsoft365 --mailNickname devs --ownerUserNames john.doe@contoso.com --memberUserNames "john.doe@contoso.com,adele.vance@contoso.com" --visibility Private

m365 entra group add --displayName Developers --type microsoft365 --description "This group is for all developers in the company." --visibility Public

```

### Remarks
The `visibility` option affects the behavior of the group.

With the `Public` visibility:

With the `Private` visibilty:

With the `HiddenMembership` visibility:

:::note

The `HiddenMembership` visibility can be set only for Microsoft 365 groups when the groups are created. It can't be updated later.

:::

This command allows using unknown options. For a comprehensive list of group properties, please refer to the [Graph documentation page](https://learn.microsoft.com/graph/api/resources/group?view=graph-rest-1.0#properties).

If the specified option is not found, you will receive a `Resource 'xyz' does not exist or one of its queried reference-property objects are not present.` error.



---

## group-get

### Syntax
```
m365 entra group get [options]
```

### Example
```
m365 entra group get --id EXAMPLE-GUID-PLACEHOLDER

m365 entra group get --displayName Finance --properties "mail,displayName"

```

### Remarks
Using the `--properties` option, you can specify a comma-separated list of group properties to retrieve from the Microsoft Graph. If you don't specify any properties, the command will output the default properties returned by Graph.



---

## group-list

### Syntax
```
m365 entra group list [options]
```

### Example
```
m365 entra group list

m365 entra group list --type security --properties "mail,displayName"

```

### Remarks
Using the `--properties` option, you can specify a comma-separated list of group properties to retrieve from the Microsoft Graph. If you don't specify any properties, the command will output the default properties returned by Graph.



---

## group-member-add

### Syntax
```
m365 entra group member add [options]
```

### Example
```
m365 entra group member add --groupDisplayName Developers --ids EXAMPLE-GUID-PLACEHOLDER --role Member```

---

## group-member-list

### Syntax
```
m365 entra group member list [options]
```

### Example
```
m365 entra group member list --groupId EXAMPLE-GUID-PLACEHOLDER

m365 entra group member list --groupName Developers --role Owner

m365 entra group member list --groupName Developers --properties "displayName,mail,manager/displayName"

m365 entra group member list --groupName Developers --properties "displayName,mail,manager/*"

m365 entra group member list --groupName Developers --filter "userType eq 'Guest'"

```

### Remarks
When the `properties` option includes values with a `/`, for example: `manager/displayName`, an additional `$expand` query parameter will be included on `manager`.



---

## group-member-remove

### Syntax
```
m365 entra group member remove [options]
```

### Example
```
m365 entra group member remove --groupName Developers --userIds EXAMPLE-GUID-PLACEHOLDER --role Member```

### Remarks
:::tip

When you use the `suppressNotFound` option, the command will not return an error if a user is not found as either an owner or a member of the group.
This feature proves useful when you need to remove a user from a group, but you are uncertain whether the user holds the role of a member or an owner within that group.
Without using this option, you would need to manually verify the user's role in the group before proceeding with removal.

:::



---

## group-member-set

### Syntax
```
m365 entra group member set [options]
```

### Example
```
m365 entra group member set --groupDisplayName Developers --ids EXAMPLE-GUID-PLACEHOLDER --role Member```

---

## group-remove

### Syntax
```
m365 entra group remove [options]
```

### Example
```
m365 entra group remove --displayName Developers

m365 entra group remove --id EXAMPLE-GUID-PLACEHOLDER

```

---

## group-set

### Syntax
```
m365 entra group set [options]
```

### Example
```
m365 entra group set --displayName Devs --newDisplayName Developers

m365 entra group set --id EXAMPLE-GUID-PLACEHOLDER --ownerUserNames "john.doe@contoso.com,adele.vance@contoso.com"

m365 entra group set --id EXAMPLE-GUID-PLACEHOLDER --description "All developers of the company" --mailNickname developers

```

### Remarks
The `visibility` option affects the behavior of the group.

With the `Public` visibility:

With the `Private` visibilty:

If the specified option is not found, you will receive a `Resource 'xyz' does not exist or one of its queried reference-property objects are not present.` error.

Specifying `memberIds` or `memberUserNames` will make only those users members, removing all others. Similarly, specifying `ownerIds` or `ownerUserNames` will make only those users owners, removing all others.



---

## groupsetting-add

### Syntax
```
m365 entra groupsetting add [options]
```

### Example
```
m365 entra groupsetting add --templateId EXAMPLE-GUID-PLACEHOLDER --UsageGuidelinesUrl https://contoso.sharepoint.com/sites/compliance --ClassificationList 'HBI, MBI, LBI, GDPR' --DefaultClassification MBI

```

### Remarks
To create a group setting, you have to specify the ID of the group setting template that should be used to create the setting. You can retrieve the ID of the template using the [entra groupsettingtemplate list](../groupsettingtemplate/groupsettingtemplate-list.mdx) command.

To specify values for the different properties specified in the group setting template, include additional options that match the property in the group setting template. For example `--ClassificationList 'HBI, MBI, LBI, GDPR'` will set the list of classifications to use on modern SharePoint sites.

Each group setting template specifies default value for each property. If you don't specify a value for the particular property yourself, the default value from the group setting template will be used. To find out which properties are available for the particular group setting template, use the [entra groupsettingtemplate get](../groupsettingtemplate/groupsettingtemplate-get.mdx) command.

If the specified templateId doesn't reference a valid group setting template, you will get a _Resource 'xyz' does not exist or one of its queried reference-property objects are not present._ error.

If you try to add a group setting using a template, for which a setting already exists, you will get a _A conflicting object with one or more of the specified property values is present in the directory._ error.



---

## groupsetting-get

### Syntax
```
m365 entra groupsetting get [options]
```

### Example
```
m365 entra groupsetting get --id EXAMPLE-GUID-PLACEHOLDER

```

---

## groupsetting-list

### Syntax
```
m365 entra groupsetting list [options]
```

### Example
```
m365 entra groupsetting list

```

---

## groupsetting-remove

### Syntax
```
m365 entra groupsetting remove [options]
```

### Example
```
m365 entra groupsetting remove --id EXAMPLE-GUID-PLACEHOLDER

m365 entra groupsetting remove --id EXAMPLE-GUID-PLACEHOLDER --force

```

### Remarks
If the specified _id_ doesn't refer to an existing group setting, you will get a `Resource does not exist` error.



---

## groupsetting-set

### Syntax
```
m365 entra groupsetting set [options]
```

### Example
```
m365 entra groupsetting set --id EXAMPLE-GUID-PLACEHOLDER --UsageGuidelinesUrl https://contoso.sharepoint.com/sites/compliance --ClassificationList 'HBI, MBI, LBI, GDPR' --DefaultClassification MBI

```

### Remarks
To update a group setting, you have to specify the ID of the group setting. You can retrieve the ID of the group setting using the [entra groupsetting list](./groupsetting-list.mdx) command.

To update values for the different properties specified in the group setting, include additional options that match the property in the group setting. For example `--ClassificationList 'HBI, MBI, LBI, GDPR'` will set the list of classifications to use on modern SharePoint sites.

If you don't specify a value for the particular property, it will remain unchanged. To find out which properties are available for the particular group setting, use the [entra groupsetting get](./groupsetting-get.mdx) command.

If the specified id doesn't reference a valid group setting, you will get a _Resource 'xyz' does not exist or one of its queried reference-property objects are not present._ error.



---

## groupsettingtemplate-get

### Syntax
```
m365 entra groupsettingtemplate get [options]
```

### Example
```
m365 entra groupsettingtemplate get --id EXAMPLE-GUID-PLACEHOLDER

m365 entra groupsettingtemplate get --displayName Group.Unified

```

---

## groupsettingtemplate-list

### Syntax
```
m365 entra groupsettingtemplate list [options]
```

### Example
```
m365 entra groupsettingtemplate list

```

---

## license-list

### Syntax
```
m365 entra license list [options]
```

### Example
```
m365 entra license list

```

---

## m365group-add

### Syntax
```
m365 entra m365group add [options]
```

### Example
```
m365 entra m365group add --displayName Finance --mailNickname finance```

### Remarks
You cannot change the group type when you choose `HiddenMembership` visibility. HiddenMembership can be set only for Microsoft 365 groups, when the groups are created. It can't be updated later.

When specifying the path to the logo image you can use both relative and absolute paths. Note, that ~ in the path, will not be resolved and will most likely result in an error.
If an invalid user is provided in the comma-separated list of Owners or Members, the command operation will fail and the Microsoft 365 Group will not be created.

Group visibility options:



---

## m365group-conversation-list

### Syntax
```
m365 entra m365group conversation list [options]
```

### Example
```
m365 entra m365group conversation list --groupId 'EXAMPLE-GUID-PLACEHOLDER'

m365 entra m365group conversation list --groupName Finance

```

---

## m365group-conversation-post-list

### Syntax
```
m365 entra m365group conversation post list [options]
```

### Example
```
m365 entra m365group conversation post list --groupId 'EXAMPLE-GUID-PLACEHOLDER' --threadId 'EXAMPLE_SECRET_VALUE_PLACEHOLDER='

m365 entra m365group conversation post list --groupName 'MyGroup' --threadId 'EXAMPLE_SECRET_VALUE_PLACEHOLDER='

```

---

## m365group-get

### Syntax
```
m365 entra m365group get [options]
```

### Example
```
m365 entra m365group get --id EXAMPLE-GUID-PLACEHOLDER

m365 entra m365group get --displayName Finance

m365 entra m365group get --id EXAMPLE-GUID-PLACEHOLDER --withSiteUrl

```

---

## m365group-list

### Syntax
```
m365 entra m365group list [options]
```

### Example
```
m365 entra m365group list

m365 entra m365group list --displayName Project

m365 entra m365group list --mailNickname team

m365 entra m365group list --displayName Project --withSiteUrl

m365 entra m365group list --orphaned

```

### Remarks
Using the `--withSiteUrl` option, you can retrieve the URL of the site associated with the particular Microsoft 365 Group. If you however retrieve too many groups and will try to get their site URLs, you will most likely get an error as the command will get throttled, issuing too many requests, too frequently. If you get an error, consider narrowing down the result set using the `--displayName` and `--mailNickname` filters.

Using the `--orphaned` option, you can retrieve Microsoft 365 Groups without owners.



---

## m365group-recyclebinitem-clear

### Syntax
```
m365 entra m365group recyclebinitem clear [options]
```

### Example
```
m365 entra m365group recyclebinitem clear

m365 entra m365group recyclebinitem clear --force

```

---

## m365group-recyclebinitem-list

### Syntax
```
m365 entra m365group recyclebinitem list [options]
```

### Example
```
m365 entra m365group recyclebinitem list

m365 entra m365group recyclebinitem list --groupName Project

m365 entra m365group recyclebinitem list --groupMailNickname team

m365 entra m365group recyclebinitem list --groupMailNickname team --groupName Project

```

---

## m365group-recyclebinitem-remove

### Syntax
```
m365 entra m365group recyclebinitem remove [options]
```

### Example
```
m365 entra m365group recyclebinitem remove --id "EXAMPLE-GUID-PLACEHOLDER"

m365 entra m365group recyclebinitem remove --displayName "My Group"

m365 entra m365group recyclebinitem remove --mailNickname "Mygroup" --force

```

---

## m365group-recyclebinitem-restore

### Syntax
```
m365 entra m365group recyclebinitem restore [options]
```

### Example
```
m365 entra m365group recyclebinitem restore --id EXAMPLE-GUID-PLACEHOLDER

m365 entra m365group recyclebinitem restore --displayName "My Group"

m365 entra m365group recyclebinitem restore --mailNickname "Mygroup"

```

---

## m365group-remove

### Syntax
```
m365 entra m365group remove [options]
```

### Example
```
m365 entra m365group remove --id EXAMPLE-GUID-PLACEHOLDER

m365 entra m365group remove --displayName Finance --force

m365 entra m365group remove --id EXAMPLE-GUID-PLACEHOLDER --force --skipRecycleBin

```

### Remarks
If the specified _id_ doesn't refer to an existing group, you will get a `Resource does not exist` error. Additionally, if you do not have access to the group or the associated group-connected site, you will get an `Access denied` error.

When you use `--skipRecycleBin` flag to remove a Microsoft 365 group permanently, the process involves deleting the associated group-connected site and the group, and then checking if the group has been moved to the deleted groups list. In some cases, it may take a few seconds for the group to appear in the deleted groups list.

To ensure a smooth deletion process, the command employs a retry mechanism with the following parameters:

If the group is successfully moved to the deleted groups list within the specified number of retries, the command will then proceed to permanently remove it from the tenant. If the group cannot be removed after all retries, it will remain in the deleted groups list.



---

## m365group-renew

### Syntax
```
m365 entra m365group renew [options]
```

### Example
```
m365 entra m365group renew --id EXAMPLE-GUID-PLACEHOLDER

m365 entra m365group renew --displayName Finance

```

### Remarks
If the specified _id_ doesn't refer to an existing group, you will get a `The remote server returned an error: (404) Not Found.` error.



---

## m365group-report-activitycounts

### Syntax
```
m365 entra m365group report activitycounts [options]
```

### Example
```
m365 entra m365group report activitycounts --period D7

m365 entra m365group report activitycounts --period D7 --output text > "m365groupactivitycounts.txt"

m365 entra m365group report activitycounts --period D7 --output json > "m365groupactivitycounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## m365group-report-activitydetail

### Syntax
```
m365 entra m365group report activitydetail [options]
```

### Example
```
m365 entra m365group report activitydetail --period D7

m365 entra m365group report activitydetail --date 2019-09-28

m365 entra m365group report activitydetail --period D7 --output text > "m365groupactivitydetail.txt"

m365 entra m365group report activitydetail --period D7 --output json > "m365groupactivitydetail.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## m365group-report-activityfilecounts

### Syntax
```
m365 entra m365group report activityfilecounts [options]
```

### Example
```
m365 entra m365group report activityfilecounts --period D7

m365 entra m365group report activityfilecounts --period D7 --output text > "m365groupactivityfilecounts.txt"

m365 entra m365group report activityfilecounts --period D7 --output json > "m365groupactivityfilecounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## m365group-report-activitygroupcounts

### Syntax
```
m365 entra m365group report activitygroupcounts [options]
```

### Example
```
m365 entra m365group report activitygroupcounts --period D7

m365 entra m365group report activitygroupcounts --period D7 --output text > "m365groupactivitygroupcounts.txt"

m365 entra m365group report activitygroupcounts --period D7 --output json > "m365groupactivitygroupcounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## m365group-report-activitystorage

### Syntax
```
m365 entra m365group report activitystorage [options]
```

### Example
```
m365 entra m365group report activitystorage --period D7

m365 entra m365group report activitystorage --period D7 --output text > "m365groupactivitystorage.txt"

m365 entra m365group report activitystorage --period D7 --output json > "m365groupactivitystorage.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## m365group-set

### Syntax
```
m365 entra m365group set [options]
```

### Example
```
m365 entra m365group set --id EXAMPLE-GUID-PLACEHOLDER --newDisplayName Finance```

### Remarks
When updating group's owners and members, the command will remove existing owners/members from the group, and the specified users will be added.

When specifying the path to the logo image you can use both relative and absolute paths. Note, that ~ in the path, will not be resolved and will most likely result in an error.

:::note

Options `allowExternalSenders` and `autoSubscribeNewMembers` can only be set using delegated permissions.  

:::



---

## m365group-teamify

### Syntax
```
m365 entra m365group teamify [options]
```

### Example
```
m365 entra m365group teamify --id EXAMPLE-GUID-PLACEHOLDER

m365 entra m365group teamify --displayName Finance

m365 entra m365group teamify --mailNickname GroupName

```

---

## m365group-user-add

### Syntax
```
m365 entra m365group user add [options]
```

### Example
```
m365 entra m365group user add --groupId 'EXAMPLE-GUID-PLACEHOLDER' --userNames 'anne.matthews@contoso.onmicrosoft.com'```

---

## m365group-user-list

### Syntax
```
m365 entra m365group user list [options]
```

### Example
```
m365 entra m365group user list --groupId 'EXAMPLE-GUID-PLACEHOLDER'

m365 entra m365group user list --groupDisplayName Developers --role Owner

m365 entra m365group user list --groupId EXAMPLE-GUID-PLACEHOLDER --properties "id,jobTitle,companyName,accountEnabled"

m365 entra m365group user list --groupDisplayName Developers --filter "userType eq 'Guest'"

```

### Remarks
When the `properties` option includes values with a `/`, for example: `manager/displayName`, an additional `$expand` query parameter will be included on `manager`.



---

## m365group-user-remove

### Syntax
```
m365 entra m365group user remove [options]
```

### Example
```
m365 entra m365group user remove --groupId 'EXAMPLE-GUID-PLACEHOLDER' --userNames 'anne.matthews@contoso.onmicrosoft.com'```

### Remarks
You can remove users from a Microsoft 365 Group or Microsoft Teams team if you are owner of that group or team.



---

## m365group-user-set

### Syntax
```
m365 entra m365group user set [options]
```

### Example
```
m365 entra m365group user set --groupId 'EXAMPLE-GUID-PLACEHOLDER' --userNames 'anne.matthews@contoso.onmicrosoft.com' --role Owner```

### Remarks
The command will return an error if the user already has the specified role in the given Microsoft 365 Group or Microsoft Teams team.



---

## multitenant-add

### Syntax
```
m365 entra multitenant add [options]
```

### Example
```
m365 entra multitenant add --displayName 'Contoso organization'

m365 entra multitenant add --displayName 'Contoso organization' --description 'Multitenant organization between Contoso, Fabrikam, and Woodgrove Bank'

```

### Remarks
:::info

To use this command you must be at least **Security Administrator**.

:::



---

## multitenant-get

### Syntax
```
m365 entra multitenant get [options]
```

### Example
```
m365 entra multitenant get

```

### Remarks
:::info

To use this command you must be at least **Security Administrator**.

:::



---

## multitenant-remove

### Syntax
```
m365 entra multitenant remove [options]
```

### Example
```
m365 entra multitenant remove

m365 entra multitenant remove --force

```

### Remarks
:::info

To use this command you must be at least **Security Administrator**.

:::

:::info

When removing a Multi-Tenant Organization, all associations with other tenants will be removed too.

The removing process can take up to 2 hours to complete.

:::



---

## multitenant-set

### Syntax
```
m365 entra multitenant set [options]
```

### Example
```
m365 entra multitenant set --displayName 'Fabrikam organization'

m365 entra multitenant set --displayName 'Fabrikam organization' --description 'Multitenant organization between Fabrikam and Contoso'

```

### Remarks
:::info

To use this command you must be at least **Security Administrator**.

:::



---

## oauth2grant-add

### Syntax
```
m365 entra oauth2grant add [options]
```

### Example
```
m365 entra oauth2grant add --clientId EXAMPLE-GUID-PLACEHOLDER --resourceId EXAMPLE-GUID-PLACEHOLDER --scope Calendars.Read

m365 entra oauth2grant add --clientId EXAMPLE-GUID-PLACEHOLDER --resourceId EXAMPLE-GUID-PLACEHOLDER --scope "Calendars.Read Mail.Read"

```

### Remarks
Before you can grant service principal OAuth2 permissions, you need its `objectId`. You can retrieve it using the [entra enterpriseapp get](../enterpriseapp/enterpriseapp-get.mdx) command.

The resource for which you want to grant permissions is designated using its `objectId`. You can retrieve it using the [entra enterpriseapp get](../enterpriseapp/enterpriseapp-get.mdx) command, the same way you would retrieve the `objectId` of the service principal.

When granting OAuth2 permissions, you have to specify which permission scopes you want to grant the service principal. You can get the list of available permission scopes either from the resource documentation or from the `appRoles` property when retrieving information about the service principal using the [entra enterpriseapp get](../enterpriseapp/enterpriseapp-get.mdx) command. Multiple permission scopes can be specified separated by a space.

When granting OAuth2 permissions, the values of the `clientId` and `resourceId` properties form a unique key. If a grant for the same `clientId`-`resourceId` pair already exists, running the `entra oauth2grant add` command will fail with an error. If you want to change permissions on an existing OAuth2 grant use the [entra oauth2grant set](./oauth2grant-set.mdx) command instead.



---

## oauth2grant-list

### Syntax
```
m365 entra oauth2grant list [options]
```

### Example
```
m365 entra oauth2grant list --spObjectId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
In order to list existing OAuth2 permissions granted to a service principal, you need its `objectId`. You can retrieve it using the [entra enterpriseapp get](../enterpriseapp/enterpriseapp-get.mdx) command.

When using the text output type (default), the command lists only the values of the `objectId`, `resourceId` and `scope` properties of the OAuth grant. When setting the output type to JSON, all available properties are included in the command output.



---

## oauth2grant-remove

### Syntax
```
m365 entra oauth2grant remove [options]
```

### Example
```
m365 entra oauth2grant remove --grantId EXAMPLE_SECRET_VALUE_PLACEHOLDER

m365 entra oauth2grant remove --grantId EXAMPLE_SECRET_VALUE_PLACEHOLDER --force

```

### Remarks
Before you can remove service principal's OAuth2 permissions, you need to get the `objectId` of the permissions grant to remove. You can retrieve it using the [entra oauth2grant list](./oauth2grant-list.mdx) command.

If the `objectId` listed when using the [entra oauth2grant list](./oauth2grant-list.mdx) command has a minus sign ('-') prefix, you may receive an error indicating `--grantId` is missing.  To resolve this issue simply escape the leading '-'.  



---

## oauth2grant-set

### Syntax
```
m365 entra oauth2grant set [options]
```

### Example
```
m365 entra oauth2grant set --grantId EXAMPLE_SECRET_VALUE_PLACEHOLDER --scope "Calendars.Read Mail.Read"

```

### Remarks
Before you can update service principal's OAuth2 permissions, you need to get the `objectId` of the permissions grant to update. You can retrieve it using the [entra oauth2grant list](./oauth2grant-list.mdx) command.

If the `objectId` listed when using the [entra oauth2grant list](./oauth2grant-list.mdx) command has a minus sign ('-') prefix, you may receive an error indicating `--grantId` is missing. To resolve this issue simply escape the leading '-'.  



---

## organization-list

### Syntax
```
m365 entra organization list [options]
```

### Example
```
m365 entra organization list

m365 entra organization list --properties 'id,displayName,tenantType'

```

### Remarks
:::info

Applications granted the `User.Read` permission are able to read only the id, displayName, and verifiedDomains properties of the organization. 
All other properties return with null values. To read all properties, use at least `Organization.Read.All`.

:::



---

## organization-set

### Syntax
```
m365 entra organization set [options]
```

### Example
```
m365 entra organization set --id EXAMPLE-GUID-PLACEHOLDER --marketingNotificationEmails 'marketing@contoso.com'

m365 entra organization set --displayName Contoso --marketingNotificationEmails 'marketing@contoso.com'

```

---

## pim-role-assignment-add

### Syntax
```
m365 entra pim role assignment add [options]
```

### Example
```
m365 entra pim role assignment add --roleDefinitionName 'SharePoint Administrator'```

### Remarks
:::info

When activating a role for other users, you must be **Privileged Role Administrator**.

:::



---

## pim-role-assignment-eligibility-list

### Syntax
```
m365 entra pim role assignment eligibility list [options]
```

### Example
```
m365 entra pim role assignment eligibility list

m365 entra pim role assignment eligibility list --userId '@meID'

m365 entra pim role assignment eligibility list --withPrincipalDetails

```

---

## pim-role-assignment-list

### Syntax
```
m365 entra pim role assignment list [options]
```

### Example
```
m365 entra pim role assignment list

m365 entra pim role assignment list --userId '@meID'

m365 entra pim role assignment list --startDateTime 2024-01-01T00:00:00Z

m365 entra pim role assignment list --withPrincipalDetails

```

---

## pim-role-assignment-remove

### Syntax
```
m365 entra pim role assignment remove [options]
```

### Example
```
m365 entra pim role assignment remove --roleDefinitionName 'SharePoint Administrator'```

### Remarks
:::info

When deactivating a role for other users, you must be **Privileged Role Administrator**.

:::



---

## pim-role-request-list

### Syntax
```
m365 entra pim role request list [options]
```

### Example
```
m365 entra pim role request list

m365 entra pim role request list --userId '@meID'

m365 entra pim role request list --createdDateTime 2024-01-01T00:00:00Z

m365 entra pim role request list --withPrincipalDetails

m365 entra pim role request list --status PendingApproval

```

---

## policy-list

### Syntax
```
m365 entra policy list [options]
```

### Example
```
m365 entra policy list

m365 entra policy list --type "claimsMapping"

```

---

## resourcenamespace-list

### Syntax
```
m365 entra resourcenamespace list [options]
```

### Example
```
m365 entra resourcenamespace list

```

### Remarks
:::warning

The command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## roledefinition-add

### Syntax
```
m365 entra roledefinition add [options]
```

### Example
```
m365 entra roledefinition add --displayName 'Application Remover' --description 'Allows to remove any Entra ID application' --allowedResourceActions 'microsoft.directory/applications/delete'

m365 entra roledefinition add --displayName 'Application Remover' --version '1.0' --enabled false --allowedResourceActions 'microsoft.directory/applications/delete,microsoft.directory/applications/owners/update'

```

### Remarks
Use the `m365 entra rolepermission list --resourceNamespace microsoft.directory` command to get a list of available resource actions.



---

## roledefinition-get

### Syntax
```
m365 entra roledefinition get [options]
```

### Example
```
m365 entra roledefinition get --id EXAMPLE-GUID-PLACEHOLDER

m365 entra roledefinition get --displayName 'Custom SharePoint Role' --properties 'description,isEnabled'

```

---

## roledefinition-list

### Syntax
```
m365 entra roledefinition list [options]
```

### Example
```
m365 entra roledefinition list

m365 entra roledefinition list --properties 'displayName'

m365 entra roledefinition list --filter 'isBuiltIn eq false'

```

---

## roledefinition-remove

### Syntax
```
m365 entra roledefinition remove [options]
```

### Example
```
m365 entra roledefinition remove --id EXAMPLE-GUID-PLACEHOLDER --force

m365 entra roledefinition remove --displayName 'Custom Role'

```

### Remarks
:::info

When the role definition is removed, all the associated role assignments are deleted.

:::



---

## roledefinition-set

### Syntax
```
m365 entra roledefinition set [options]
```

### Example
```
m365 entra roledefinition set --id EXAMPLE-GUID-PLACEHOLDER --newDisplayName 'Application Remover' --description 'Allows to remove any Entra ID application' --allowedResourceActions 'microsoft.directory/applications/delete'

m365 entra roledefinition set --displayName 'Application Remover' --version '1.0' --enabled true --allowedResourceActions 'microsoft.directory/applications/delete,microsoft.directory/applications/owners/update'

```

### Remarks
Use the `m365 entra rolepermission list --resourceNamespace microsoft.directory` command to get a list of available resource actions.



---

## rolepermission-list

### Syntax
```
m365 entra rolepermission list [options]
```

### Example
```
m365 entra rolepermission list --resourceNamespace 'microsoft.directory'

m365 entra rolepermission list --resourceNamespace 'microsoft.directory' --privileged

```

### Remarks
:::warning

The command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

Use the `m365 entra resourcenamespace list` command to get a list of available resource namespaces.



---

## siteclassification-disable

### Syntax
```
m365 entra siteclassification disable [options]
```

### Example
```
m365 entra siteclassification disable

m365 entra siteclassification disable --force

```

---

## siteclassification-enable

### Syntax
```
m365 entra siteclassification enable [options]
```

### Example
```
m365 entra siteclassification enable --classifications "High, Medium, Low" --defaultClassification "Medium"

m365 entra siteclassification enable --classifications "High, Medium, Low" --defaultClassification "Medium" --usageGuidelinesUrl "http://aka.ms/pnp"

m365 entra siteclassification enable --classifications "High, Medium, Low" --defaultClassification "Medium" --usageGuidelinesUrl "http://aka.ms/pnp" --guestUsageGuidelinesUrl "http://aka.ms/pnp"

```

---

## siteclassification-get

### Syntax
```
m365 entra siteclassification get [options]
```

### Example
```
m365 entra siteclassification get

```

---

## siteclassification-set

### Syntax
```
m365 entra siteclassification set [options]
```

### Example
```
m365 entra siteclassification set --classifications "High, Medium, Low" --defaultClassification "Medium"

m365 entra siteclassification set --defaultClassification "Low"

m365 entra siteclassification set --usageGuidelinesUrl "http://aka.ms/pnp"

m365 entra siteclassification set --usageGuidelinesUrl "http://aka.ms/pnp" --guestUsageGuidelinesUrl "http://aka.ms/pnp"

```

---

## user-add

### Syntax
```
m365 entra user add [options]
```

### Example
```
m365 entra user add --displayName "John Doe" --userName "john.doe@contoso.com" --password "SomePassw0rd" --forceChangePasswordNextSignIn```

### Remarks
:::info

To use this command you must be a Global administrator, User administrator or Privileged Authentication administrator.

:::

:::note

After running this command, it may take a minute before the user is effectively created in the tenant.

:::

This command allows using unknown options. For a comprehensive list of user properties, please refer to the [Graph documentation page](https://learn.microsoft.com/graph/api/resources/user?view=graph-rest-1.0#properties).

If the specified option is not found, you will receive a `Resource 'xyz' does not exist or one of its queried reference-property objects are not present.` error.



---

## user-get

### Syntax
```
m365 entra user get [options]
```

### Example
```
m365 entra user get --id EXAMPLE-GUID-PLACEHOLDER

m365 entra user get --userName AarifS@contoso.onmicrosoft.com

m365 entra user get --email AarifS@contoso.onmicrosoft.com

m365 entra user get --id EXAMPLE-GUID-PLACEHOLDER --properties "userPrincipalName,mail,displayName"

m365 entra user get --id "@meId"

m365 entra user get --userName "@meUserName"

m365 entra user get --userName AarifS@contoso.onmicrosoft.com --withManager

```

### Remarks
You can retrieve information about a user, either by specifying that user's id, user name (`userPrincipalName`), or email (`mail`), but not all.

If the user with the specified id, user name, or email doesn't exist, you will get a `Resource 'xyz' does not exist or one of its queried reference-property objects are not present.` error.



---

## user-groupmembership-list

### Syntax
```
m365 entra user groupmembership list [options]
```

### Example
```
m365 entra user groupmembership list --userId 'EXAMPLE-GUID-PLACEHOLDER'

m365 entra user groupmembership list --userName 'john.doe@contoso.com' --securityEnabledOnly

m365 entra user groupmembership list --userId '@meId'

m365 entra user groupmembership list --userName '@meUserName'

```

---

## user-guest-add

### Syntax
```
m365 entra user guest add [options]
```

### Example
```
m365 entra user guest add --emailAddress john.doe@contoso.com --displayName "John Doe" --sendInvitationMessage

m365 entra user guest add --emailAddress john.doe@contoso.com --welcomeMessage "Hi John, welcome to the organization!" --inviteRedirectUrl https://contoso.sharepoint.com --sendInvitationMessage

m365 entra user guest add --emailAddress john.doe@contoso.com --messageLanguage nl-BE --sendInvitationMessage

```

---

## user-hibp

### Syntax
```
m365 entra user hibp [options]
```

### Example
```
m365 entra user hibp --userName account-exists@hibp-integration-tests.com --apiKey _YOUR-API-KEY_

m365 entra user hibp --userName account-exists@hibp-integration-tests.com --apiKey _YOUR-API-KEY_ --domain adobe.com

```

### Remarks
If the user with the specified user name doesn't involved in any breach, you will get a `No pwnage found` message when running in debug or verbose mode.

If `API Key` is invalid, you will get a `Required option apiKey not specified` error.



---

## user-license-add

### Syntax
```
m365 entra user license add [options]
```

### Example
```
m365 entra user license add --userName "john.doe@contoso.com" --ids "EXAMPLE-GUID-PLACEHOLDER,EXAMPLE-GUID-PLACEHOLDER"

m365 entra user license add --userId "EXAMPLE-GUID-PLACEHOLDER" --ids "EXAMPLE-GUID-PLACEHOLDER,EXAMPLE-GUID-PLACEHOLDER"

```

### Remarks
:::info

The user must have a `usageLocation` value in order to assign a license to it.

:::



---

## user-license-list

### Syntax
```
m365 entra user license list [options]
```

### Example
```
m365 entra user license list

m365 entra user license list --userName john.doe@contoso.com

m365 entra user license list --userId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::tip

If you don't specify any option, the command will list the license details of the current logged in user. This does not work when using application permissions.

:::



---

## user-license-remove

### Syntax
```
m365 entra user license remove [options]
```

### Example
```
m365 entra user license remove --userName "john.doe@contoso.com" --ids "EXAMPLE-GUID-PLACEHOLDER,EXAMPLE-GUID-PLACEHOLDER"

m365 entra user license remove --userId EXAMPLE-GUID-PLACEHOLDER --ids "EXAMPLE-GUID-PLACEHOLDER,EXAMPLE-GUID-PLACEHOLDER"

```

---

## user-list

### Syntax
```
m365 entra user list [options]
```

### Example
```
m365 entra user list

m365 entra user list --type Guest

m365 entra user list --properties "displayName,mail"

m365 entra user list --displayName Patt

m365 entra user list --displayName Patt --jobTitle 'Account manager'

m365 entra user list --properties "displayName,mail,manager/*"

```

### Remarks
Using the `--properties` option, you can specify a comma-separated list of user properties to retrieve from the Microsoft Graph. If you don't specify any properties, the command will output the default properties returned by Graph.  

When the `properties` option includes values with a `/`, for example: `manager/displayName`, an additional `$expand` query parameter will be included on `manager`.

To filter the list of users, include additional options that match the user property that you want to filter with. For example `--displayName Patt` will return all users whose `displayName` starts with `Patt`. Multiple filters will be combined using the `and` operator.

Certain properties cannot be returned within a user collection. The following properties are only supported when retrieving an single user using: `aboutMe`, `birthday`, `hireDate`, `interests`, `mySite`, `pastProjects`, `preferredName`, `responsibilities`, `schools`, `skills`, `mailboxSettings`.



---

## user-password-validate

### Syntax
```
m365 entra user password validate [options]
```

### Example
```
m365 entra user password validate --password "cli365P@ssW0rd"

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## user-recyclebinitem-clear

### Syntax
```
m365 entra user recyclebinitem clear [options]
```

### Example
```
m365 entra user recyclebinitem clear

m365 entra user recyclebinitem clear --force

```

### Remarks
:::info

To use this command you must be a Global administrator, User administrator or Privileged Authentication administrator.

:::

:::note

After running this command, it may take a minute before all deleted users are effectively removed from the tenant.

:::



---

## user-recyclebinitem-list

### Syntax
```
m365 entra user recyclebinitem list [options]
```

### Example
```
m365 entra user recyclebinitem list

```

---

## user-recyclebinitem-remove

### Syntax
```
m365 entra user recyclebinitem remove [options]
```

### Example
```
m365 entra user recyclebinitem remove --id EXAMPLE-GUID-PLACEHOLDER

m365 entra user recyclebinitem remove --id EXAMPLE-GUID-PLACEHOLDER --force

```

### Remarks
:::info

To use this command you must be a Global administrator, User administrator or Privileged Authentication administrator.

:::

:::note

After running this command, it may take a minute before the deleted user is effectively removed from the tenant.

:::



---

## user-recyclebinitem-restore

### Syntax
```
m365 entra user recyclebinitem restore [options]
```

### Example
```
m365 entra user recyclebinitem restore --id EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::info

To use this command you must be a Global administrator, User administrator or Privileged Authentication administrator

:::

:::note

After running this command, it may take a minute before the user will reappear in the active users.

:::



---

## user-registrationdetails-list

### Syntax
```
m365 entra user registrationdetails list [options]
```

### Example
```
m365 entra user registrationdetails list```

### Remarks
Using the `--properties` option, you can specify a comma-separated list of registration details properties to retrieve from the Microsoft Graph. If you don't specify any properties, the command will retrieve user's account name, registered methods and timestamp of last update.

:::info

When multiple values are specified for `--EXAMPLE_SECRET_VALUE_PLACEHOLDER` option, the command returns registration details with at least one specified selected method as default second-factor authentication.

When multiple values are specified for `--systemPreferredAuthenticationMethods` option, the command returns registration details with at least one specified most secure authentication methods registered for second-factor authentication.

When multiple values are specified for `--registeredMethods` option, the command returns registration details with at least one specified registered methods used during registration.

:::



---

## user-remove

### Syntax
```
m365 entra user remove [options]
```

### Example
```
m365 entra user remove --id EXAMPLE-GUID-PLACEHOLDER

m365 entra user remove --userName john.doe@contoso.com

```

### Remarks
:::info

If the user with the specified id or user name doesn't exist, you will get a `Resource 'xyz' does not exist or one of its queried reference-property objects are not present.` error.

:::

:::info

To use this command you must be a Global administrator, User administrator or Privileged Authentication administrator.

:::

:::note

After running this command, it may take a minute before the user is effectively moved to the recycle bin.

:::



---

## user-session-revoke

### Syntax
```
m365 entra user session revoke [options]
```

### Example
```
m365 entra user session revoke --userId EXAMPLE-GUID-PLACEHOLDER

m365 entra user session revoke --userName john.doe@contoso.onmicrosoft.com

m365 entra user session revoke --userName john.doe@contoso.onmicrosoft.com --force

```

### Remarks
:::info

To use this command you must be either **User Administrator** or **Global Administrator**.

:::

:::note

There might be a small delay of a few minutes before tokens are revoked.

This API doesn't revoke sign-in sessions for external users, because external users sign in through their home tenant.

:::



---

## user-set

### Syntax
```
m365 entra user set [options]
```

### Example
```
m365 entra user set --id EXAMPLE-GUID-PLACEHOLDER --department IT```

### Remarks
This command allows using unknown options. For a comprehensive list of user properties, please refer to the [Graph documentation page](https://learn.microsoft.com/graph/api/resources/user?view=graph-rest-1.0#properties).

If the user with the specified ID or username doesn't exist, or if the specified option is not found, you will receive a `Resource 'xyz' does not exist or one of its queried reference-property objects are not present.` error.



---

## user-signin-list

### Syntax
```
m365 entra user signin list [options]
```

### Example
```
m365 entra user signin list```

---
