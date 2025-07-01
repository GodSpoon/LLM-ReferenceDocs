<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - PURVIEW Commands Reference

*This is an automatically generated condensed reference of all PURVIEW commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-07-01*

---

## Table of Contents

- [auditlog-list](#auditlog-list)
- [retentionevent-add](#retentionevent-add)
- [retentionevent-get](#retentionevent-get)
- [retentionevent-list](#retentionevent-list)
- [retentionevent-remove](#retentionevent-remove)
- [retentioneventtype-add](#retentioneventtype-add)
- [retentioneventtype-get](#retentioneventtype-get)
- [retentioneventtype-list](#retentioneventtype-list)
- [retentioneventtype-remove](#retentioneventtype-remove)
- [retentioneventtype-set](#retentioneventtype-set)
- [retentionlabel-add](#retentionlabel-add)
- [retentionlabel-get](#retentionlabel-get)
- [retentionlabel-list](#retentionlabel-list)
- [retentionlabel-remove](#retentionlabel-remove)
- [retentionlabel-set](#retentionlabel-set)
- [sensitivitylabel-get](#sensitivitylabel-get)
- [sensitivitylabel-list](#sensitivitylabel-list)
- [sensitivitylabel-policysettings-list](#sensitivitylabel-policysettings-list)
- [threatassessment-add](#threatassessment-add)
- [threatassessment-get](#threatassessment-get)
- [threatassessment-list](#threatassessment-list)

---

## auditlog-list

### Syntax
```
m365 purview auditlog list [options]
```

### Example
```
m365 purview auditlog list --contentType SharePoint

m365 purview auditlog list --contentType SharePoint --startTime "2023-01-01T00:00:00Z" --endTime "2023-01-03T09:00:00Z"

m365 purview auditlog list --contentType SharePoint --startTime "2023-01-01T00:00:00Z" --endTime "2023-01-01T12:00:00Z" > auditLogs.json

```

### Remarks
:::info

Before you can access audit log data, you must enable unified audit logging for your Microsoft 365 tenant. For instructions, check out the page [Turn auditing on or off](https://learn.microsoft.com/microsoft-365/compliance/audit-log-enable-disable).

:::

:::info

When running this command for the first time for a certain content type, a subscription for this content type is created. It can take up to 12 hours for the first content blobs to become available for that subscription.

:::

:::tip

Retrieving audit logs is an intensive process, especially for large or active tenants. In this case it may take some time to retrieve all audit logs. It can be useful to add the `--verbose` option to your command to view the command progress.

:::

When you specify a value for `contentType`, consider the following:



---

## retentionevent-add

### Syntax
```
m365 purview retentionevent add [options]
```

### Example
```
m365 purview retentionevent add --displayName 'Employee information expiration' --description 'Employee documents expired due to offboarding' --eventTypeName 'CustomRetentionTime' --triggerDateTime '2022-12-31' --assetIds 'ComplianceAssetId:EmployeeNr1234'

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## retentionevent-get

### Syntax
```
m365 purview retentionevent get [options]
```

### Example
```
m365 purview retentionevent get --id EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## retentionevent-list

### Syntax
```
m365 purview retentionevent list [options]
```

### Example
```
m365 purview retentionevent list

```

### Remarks
:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## retentionevent-remove

### Syntax
```
m365 purview retentionevent remove [options]
```

### Example
```
m365 purview retentionevent remove --id EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## retentioneventtype-add

### Syntax
```
m365 purview retentioneventtype add [options]
```

### Example
```
m365 purview retentioneventtype add --displayName 'Contract Expiry' --description 'A retention event type to start a retention period based on the date that a contract expired.'

```

### Remarks
:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## retentioneventtype-get

### Syntax
```
m365 purview retentioneventtype get [options]
```

### Example
```
m365 purview retentioneventtype get --id EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## retentioneventtype-list

### Syntax
```
m365 purview retentioneventtype list [options]
```

### Example
```
m365 purview retentioneventtype list

```

### Remarks
:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## retentioneventtype-remove

### Syntax
```
m365 purview retentioneventtype remove [options]
```

### Example
```
m365 purview retentioneventtype remove --id EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## retentioneventtype-set

### Syntax
```
m365 purview retentioneventtype set [options]
```

### Example
```
m365 purview retentioneventtype set --id EXAMPLE-GUID-PLACEHOLDER --description 'some extra information'

```

### Remarks
:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## retentionlabel-add

### Syntax
```
m365 purview retentionlabel add [options]
```

### Example
```
m365 purview retentionlabel add --displayName 'some label' --behaviorDuringRetentionPeriod retain --actionAfterRetentionPeriod delete --retentionDuration 365```

### Remarks
:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## retentionlabel-get

### Syntax
```
m365 purview retentionlabel get [options]
```

### Example
```
m365 purview retentionlabel get --id EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## retentionlabel-list

### Syntax
```
m365 purview retentionlabel list [options]
```

### Example
```
m365 purview retentionlabel list

```

### Remarks
:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## retentionlabel-remove

### Syntax
```
m365 purview retentionlabel remove [options]
```

### Example
```
m365 purview retentionlabel remove --id 'EXAMPLE-GUID-PLACEHOLDER'

```

### Remarks
:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## retentionlabel-set

### Syntax
```
m365 purview retentionlabel set [options]
```

### Example
```
m365 purview retentionlabel set --id EXAMPLE-GUID-PLACEHOLDER --behaviorDuringRetentionPeriod retainAsRecord --actionAfterRetentionPeriod delete --retentionDuration 365

m365 purview retentionlabel set --id EXAMPLE-GUID-PLACEHOLDER --behaviorDuringRetentionPeriod retainAsRegulatoryRecord --actionAfterRetentionPeriod startDispositionReview --retentionDuration 365 --retentionTrigger dateModified

```

### Remarks
:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## sensitivitylabel-get

### Syntax
```
m365 purview sensitivitylabel get [options]
```

### Example
```
m365 purview sensitivitylabel get --id EXAMPLE-GUID-PLACEHOLDER

m365 purview sensitivitylabel get --id EXAMPLE-GUID-PLACEHOLDER --userId EXAMPLE-GUID-PLACEHOLDER

m365 purview sensitivitylabel get --id EXAMPLE-GUID-PLACEHOLDER --userName john.doe@contoso.com

```

### Remarks
:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::

:::warning

When operating in app-only mode, you have the option to use either the `userName` or `userId` parameters to retrieve the sensitivity policy settings for a specific user. Without specifying either of these parameters, the command will retrieve the sensitivity policy settings for the currently authenticated user when operating in delegated mode.

:::



---

## sensitivitylabel-list

### Syntax
```
m365 purview sensitivitylabel list [options]
```

### Example
```
m365 purview sensitivitylabel list

m365 purview sensitivitylabel list --userId EXAMPLE-GUID-PLACEHOLDER

m365 purview sensitivitylabel list --userName john.doe@contoso.com

```

### Remarks
:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::

:::warning

When operating in app-only mode, you have the option to use either the `userName` or `userId` parameters to retrieve the sensitivity label for a specific user. Without specifying either of these parameters, the command will retrieve the sensitivity label for the currently authenticated user when operating in delegated mode.

:::



---

## sensitivitylabel-policysettings-list

### Syntax
```
m365 purview sensitivitylabel policysettings list [options]
```

### Example
```
m365 purview sensitivitylabel policysettings list

m365 purview sensitivitylabel policysettings list --userId EXAMPLE-GUID-PLACEHOLDER

m365 purview sensitivitylabel policysettings list --userName john.doe@contoso.com

```

### Remarks
:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::

:::warning

When operating in app-only mode, you have the option to use either the `userName` or `userId` parameters to retrieve the sensitivity policy settings for a specific user. Without specifying either of these parameters, the command will retrieve the sensitivity policy settings for the currently authenticated user when operating in delegated mode.

:::



---

## threatassessment-add

### Syntax
```
m365 purview threatassessment add [options]
```

### Example
```
m365 purview threatassessment add --type file --expectedAssessment block --category malware --fileName 'test.txt' --path 'C:\Path\To\File.txt'

m365 purview threatassessment add --type url --expectedAssessment block --category phishing --url 'http://contoso.com'

```

### Remarks
:::info

:::



---

## threatassessment-get

### Syntax
```
m365 purview threatassessment get [options]
```

### Example
```
m365 purview threatassessment get --id EXAMPLE-GUID-PLACEHOLDER

m365 purview threatassessment get --id EXAMPLE-GUID-PLACEHOLDER --withResults

```

---

## threatassessment-list

### Syntax
```
m365 purview threatassessment list [options]
```

### Example
```
m365 purview threatassessment list

m365 purview threatassessment list --type mail

```

---
