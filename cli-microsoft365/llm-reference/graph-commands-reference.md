<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - GRAPH Commands Reference

*This is an automatically generated condensed reference of all GRAPH commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-07-01*

---

## Table of Contents

- [changelog-list](#changelog-list)
- [directoryextension-add](#directoryextension-add)
- [directoryextension-get](#directoryextension-get)
- [directoryextension-list](#directoryextension-list)
- [directoryextension-remove](#directoryextension-remove)
- [openextension-add](#openextension-add)
- [openextension-get](#openextension-get)
- [openextension-list](#openextension-list)
- [openextension-remove](#openextension-remove)
- [openextension-set](#openextension-set)
- [schemaextension-add](#schemaextension-add)
- [schemaextension-get](#schemaextension-get)
- [schemaextension-list](#schemaextension-list)
- [schemaextension-remove](#schemaextension-remove)
- [schemaextension-set](#schemaextension-set)
- [subscription-add](#subscription-add)

---

## changelog-list

### Syntax
```
m365 graph changelog list [options]
```

### Example
```
m365 graph changelog list

m365 graph changelog list --services 'Groups,Users'

m365 graph changelog list --startDate '2021-01-01' --endDate '2021-05-01'

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## directoryextension-add

### Syntax
```
m365 graph directoryextension add [options]
```

### Example
```
m365 graph directoryextension add --name gitHubWorkAccountName --appName ContosoApp --targetObjects User --dataType String

m365 graph directoryextension add --name departmentIds --appId EXAMPLE-GUID-PLACEHOLDER --targetObjects 'Application,Device' --dataType Integer --isMultiValued

```

---

## directoryextension-get

### Syntax
```
m365 graph directoryextension get [options]
```

### Example
```
m365 graph directoryextension get --id EXAMPLE-GUID-PLACEHOLDER --appId EXAMPLE-GUID-PLACEHOLDER

m365 graph directoryextension get --name EXAMPLE_SECRET_VALUE_PLACEHOLDER --appName ContosoApp

```

---

## directoryextension-list

### Syntax
```
m365 graph directoryextension list [options]
```

### Example
```
m365 graph directoryextension list

m365 graph directoryextension list --appId EXAMPLE-GUID-PLACEHOLDER

m365 graph directoryextension list --appObjectId EXAMPLE-GUID-PLACEHOLDER

m365 graph directoryextension list --appName ContosoApp

```

### Remarks
When neither `appId`, `appObjectId` nor `appName` is specified, the command will return all available directory extensions including those registered for multi-tenant apps.

https://learn.microsoft.com/en-us/graph/api/EXAMPLE_SECRET_VALUE_PLACEHOLDER?view=graph-rest-1.0&tabs=http

Otherwise, it will return directory extensions for a specific application.

https://learn.microsoft.com/en-us/graph/api/application-list-extensionproperty?view=graph-rest-1.0&tabs=http



---

## directoryextension-remove

### Syntax
```
m365 graph directoryextension remove [options]
```

### Example
```
m365 graph directoryextension remove --name EXAMPLE_SECRET_VALUE_PLACEHOLDER --appObjectId EXAMPLE-GUID-PLACEHOLDER --force

m365 graph directoryextension remove --id EXAMPLE-GUID-PLACEHOLDER --appName ContosoApp

```

---

## openextension-add

### Syntax
```
m365 graph openextension add [options]
```

### Example
```
m365 graph openextension add --resourceId EXAMPLE-GUID-PLACEHOLDER --resourceType user --name 'com.contoso.roamingSettings' --theme dark --color red --language English```

### Remarks
This command allows using unknown options to add custom data to the open extension.

When adding an open extension to a user, it's possible to use the UPN as the resourceId.

:::warning[Escaping JSON in PowerShell]

When creating open extensions it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::



---

## openextension-get

### Syntax
```
m365 graph openextension get [options]
```

### Example
```
m365 graph openextension get --resourceId EXAMPLE-GUID-PLACEHOLDER --name 'com.contoso.roamingSettings' --resourceType user

m365 graph openextension get --resourceId john.doe@contoso.com --name 'com.contoso.roamingSettings' --resourceType user

```

---

## openextension-list

### Syntax
```
m365 graph openextension list [options]
```

### Example
```
m365 graph openextension list --resourceId EXAMPLE-GUID-PLACEHOLDER --resourceType user

m365 graph openextension list --resourceId john.doe@contoso.com --resourceType user

m365 graph openextension list --resourceId EXAMPLE-GUID-PLACEHOLDER --resourceType group

m365 graph openextension list --resourceId EXAMPLE-GUID-PLACEHOLDER --resourceType organization

```

---

## openextension-remove

### Syntax
```
m365 graph openextension remove [options]
```

### Example
```
m365 graph openextension remove --resourceId EXAMPLE-GUID-PLACEHOLDER --name 'com.contoso.roamingSettings' --resourceType user

m365 graph openextension remove --resourceId john.doe@contoso.com --name 'com.contoso.roamingSettings' --resourceType user --force

m365 graph openextension remove --resourceId EXAMPLE-GUID-PLACEHOLDER --name 'com.contoso.groupSettings' --resourceType group

```

---

## openextension-set

### Syntax
```
m365 graph openextension set [options]
```

### Example
```
m365 graph openextension set --userId EXAMPLE-GUID-PLACEHOLDER --name 'com.contoso.roamingSettings' --resourceType user --theme dark --color red --language English```

### Remarks
This command allows using unknown options to update custom data of the open extension.

When updating an open extension to a user, it's possible to use the UPN as the resourceId.

:::warning[Escaping JSON in PowerShell]

When updating open extensions it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

:::info

If a property of the open extension is not specified, the property is removed from the open extension.

If a property of the open extension is not specified and `keepUnchangedProperties` is specified, the property will be kept in the open extension.

:::



---

## schemaextension-add

### Syntax
```
m365 graph schemaextension add [options]
```

### Example
```
m365 graph schemaextension add --id MySchemaExtension --description "My Schema Extension" --targetTypes Group --owner EXAMPLE-GUID-PLACEHOLDER --properties '[{"name":"myProp1","type":"Integer"},{"name":"myProp2","type":"String"}]'

m365 graph schemaextension add --id contoso_MySchemaExtension --description "My Schema Extension" --targetTypes Group --owner EXAMPLE-GUID-PLACEHOLDER --properties '[{"name":"myProp1","type":"Integer"},{"name":"myProp2","type":"String"}]'

```

### Remarks
To create a schema extension, you have to specify a unique ID for the schema extension. You can assign a value in one of two ways:

The schema extension ID cannot be changed after creation.

The schema extension owner is the ID of the Microsoft Entra application that is the owner of the schema extension. Once set, this property is read-only and cannot be changed.

The target types are the set of Microsoft Graph resource types (that support schema extensions) that this schema extension definition can be applied to. This option is specified as a comma-separated list

:::warning[Escaping JSON in PowerShell]

When using the `--properties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::



---

## schemaextension-get

### Syntax
```
m365 graph schemaextension get [options]
```

### Example
```
m365 graph schemaextension get --id domain_myExtension 

```

### Remarks
To get properties of a schema extension definition, you have to pass the ID of the schema
extension.



---

## schemaextension-list

### Syntax
```
m365 graph schemaextension list [options]
```

### Example
```
m365 graph schemaextension list 

m365 graph schemaextension list --owner EXAMPLE-GUID-PLACEHOLDER

m365 graph schemaextension list --owner EXAMPLE-GUID-PLACEHOLDER --pageNumber 2 --pageSize 10

```

### Remarks
pageNumber is specified as a 0-based index. A value of 2 returns the third page of items. 



---

## schemaextension-remove

### Syntax
```
m365 graph schemaextension remove [options]
```

### Example
```
m365 graph schemaextension remove --id domain_myExtension 

m365 graph schemaextension remove --id domain_myExtension --force

```

### Remarks
To remove specified schema extension definition, you have to pass the ID of the schema
extension.



---

## schemaextension-set

### Syntax
```
m365 graph schemaextension set [options]
```

### Example
```
m365 graph schemaextension set --id MySchemaExtension --owner EXAMPLE-GUID-PLACEHOLDER --description "My schema extension" 

m365 graph schemaextension set --id contoso_MySchemaExtension --owner EXAMPLE-GUID-PLACEHOLDER --targetTypes "Group,User" --properties '[{"name":"myProp1","type":"Integer"},{"name":"myProp2","type":"String"}]'

m365 graph schemaextension set --id contoso_MySchemaExtension --owner EXAMPLE-GUID-PLACEHOLDER --status Available

```

### Remarks
The lifecycle state of the schema extension. The initial state upon creation is `InDevelopment`.
Possible states transitions are from `InDevelopment` to `Available` and `Available` to `Deprecated`.
The target types are the set of Microsoft Graph resource types (that support schema extensions) that this schema extension definition can be applied to. This option is specified as a comma-separated list.

:::warning[Escaping JSON in PowerShell]

When using the `--properties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::



---

## subscription-add

### Syntax
```
m365 graph subscription add [options]
```

### Example
```
m365 graph subscription add --resource "me/mailFolders('Inbox')/messages" --changeTypes "updated" --notificationUrl "https://webhook.azurewebsites.net/api/send/myNotifyClient" --expirationDateTime "2016-11-20T18:23:45.935Z" --clientState "secretClientState"```

### Remarks
On personal OneDrive, you can subscribe to the root folder or any subfolder in that drive. On OneDrive for Business, you can subscribe to only the root folder.

Notifications are sent for the requested types of changes on the subscribed folder, or any file, folder, or other `driveItem` instances in its hierarchy. You cannot subscribe to `drive` or `driveItem` instances that are not folders, such as individual files.

In Outlook, delegated permission supports subscribing to items in folders in only the signed-in user's mailbox.
That means, for example, you cannot use the delegated permission Calendars.Read to subscribe to events in another user’s mailbox.

To subscribe to change notifications of Outlook contacts, events, or messages in shared or delegated folders:

:::info

For subscribers whose notification endpoint supports a version lower than the currently recommended version (TLS 1.2), specifying this property by a set timeline allows them to temporarily use their deprecated version of TLS before completing their upgrade to TLS 1.2. 
For these subscribers, not setting this property per the timeline would result in subscription operations failing.

:::



---
