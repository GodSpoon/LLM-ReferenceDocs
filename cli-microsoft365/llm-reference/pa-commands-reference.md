<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - PA Commands Reference

*This is an automatically generated condensed reference of all PA commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-09-01*

---

## Table of Contents

- [app-consent-set](#app-consent-set)
- [app-export](#app-export)
- [app-get](#app-get)
- [app-list](#app-list)
- [app-owner-set](#app-owner-set)
- [app-permission-ensure](#app-permission-ensure)
- [app-permission-list](#app-permission-list)
- [app-permission-remove](#app-permission-remove)
- [app-remove](#app-remove)
- [connector-export](#connector-export)
- [connector-list](#connector-list)
- [environment-get](#environment-get)
- [environment-list](#environment-list)

---

## app-consent-set

### Syntax
```
m365 pa app consent set [options]
```

### Example
```
m365 pa app consent set --environmentName EXAMPLE-GUID-PLACEHOLDER --name EXAMPLE-GUID-PLACEHOLDER --bypass true

m365 pa app consent set --environmentName EXAMPLE-GUID-PLACEHOLDER --name EXAMPLE-GUID-PLACEHOLDER --bypass false --force

```

### Remarks
This command only works for canvas apps.



---

## app-export

### Syntax
```
m365 pa app export [options]
```

### Example
```
m365 pa app export --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name EXAMPLE-GUID-PLACEHOLDER```

---

## app-get

### Syntax
```
m365 pa app get [options]
```

### Example
```
m365 pa app get --name EXAMPLE-GUID-PLACEHOLDER

m365 pa app get --displayName App

m365 pa app get --name EXAMPLE-GUID-PLACEHOLDER --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --asAdmin

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reaches general availability.

:::

As a maker, you are able to retrieve the Power Apps you have permission to. As an administrator, you are also able to retrieve Power Apps from other users you don't have permission to. To get the app from another user, use the `asAdmin` option and make sure to specify the `environment` option as well.

If you try to retrieve a non-existing Microsoft Power App, you will get the `Request failed with status code 404` error.



---

## app-list

### Syntax
```
m365 pa app list [options]
```

### Example
```
m365 pa app list

m365 pa app list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --asAdmin

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reaches general availability.

:::

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

By default, the `app list` command returns only your apps. To list all apps, use the `asAdmin` option and make sure to specify the `environment` option. You cannot specify only one of the options, when specifying the `environment` option the `asAdmin` option has to be present as well.



---

## app-owner-set

### Syntax
```
m365 pa app owner set [options]
```

### Example
```
m365 pa app owner set --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --appName EXAMPLE-GUID-PLACEHOLDER --userId EXAMPLE-GUID-PLACEHOLDER --roleForOldAppOwner CanEdit

m365 pa app owner set --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --appName EXAMPLE-GUID-PLACEHOLDER --userName john.doe@contoso.com

```

### Remarks
:::info

To use this command you must be a Global or Power Platform admin.

:::



---

## app-permission-ensure

### Syntax
```
m365 pa app permission ensure [options]
```

### Example
```
m365 pa app permission ensure --appName EXAMPLE-GUID-PLACEHOLDER --userName john.doe@contoso.com --roleName CanView --sendInvitationMail```

### Remarks
:::note

When specifying a value for `groupId` or `groupName`, note that you can only grant permissions to security groups.

:::



---

## app-permission-list

### Syntax
```
m365 pa app permission list [options]
```

### Example
```
m365 pa app permission list --appName EXAMPLE-GUID-PLACEHOLDER

m365 pa app permission list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --appName EXAMPLE-GUID-PLACEHOLDER --asAdmin

m365 pa app permission list --appName EXAMPLE-GUID-PLACEHOLDER --roleName CanEdit

```

### Remarks
When you specify a value for `roleName`, consider the following:



---

## app-permission-remove

### Syntax
```
m365 pa app permission remove [options]
```

### Example
```
m365 pa app permission remove --appName EXAMPLE-GUID-PLACEHOLDER --userName john.doe@contoso.com 

m365 pa app permission remove --appName EXAMPLE-GUID-PLACEHOLDER --groupName Developers

m365 pa app permission remove --environment EXAMPLE_SECRET_VALUE_PLACEHOLDER --appName EXAMPLE-GUID-PLACEHOLDER --userId EXAMPLE-GUID-PLACEHOLDER --asAdmin

m365 pa app permission remove --appName EXAMPLE-GUID-PLACEHOLDER --tenant

```

---

## app-remove

### Syntax
```
m365 pa app remove [options]
```

### Example
```
m365 pa app remove --name EXAMPLE-GUID-PLACEHOLDER

m365 pa app remove --name EXAMPLE-GUID-PLACEHOLDER --force

m365 pa app remove --name EXAMPLE-GUID-PLACEHOLDER --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --asAdmin

```

### Remarks
By default, the command will try to remove a Power App. As maker, you are able to delete the Power Apps you own. As administrator, you are also able to delete Power Apps from other users.

To remove an app you do not own, use the `asAdmin` option and make sure to specify the `environmentName` option as well.

To remove a model-driven Power App you need administrator permissions.

If the Power App with the name you specified doesn't exist, you will get the `Error: App 'abc' does not exist` error.



---

## connector-export

### Syntax
```
m365 pa connector export [options]
```

### Example
```
m365 pa connector export --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name EXAMPLE_SECRET_VALUE_PLACEHOLDER

m365 pa connector export --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name EXAMPLE_SECRET_VALUE_PLACEHOLDER --outputFolder connector

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

If no output folder has been specified, the `pa connector export` command will create a folder named after the connector in the current folder. If the output folder has been specified, the folder named after the connector will be created in that folder.



---

## connector-list

### Syntax
```
m365 pa connector list [options]
```

### Example
```
m365 pa connector list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## environment-get

### Syntax
```
m365 pa environment get [options]
```

### Example
```
m365 pa environment get

m365 pa environment get --name EXAMPLE_SECRET_VALUE_PLACEHOLDER

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.



---

## environment-list

### Syntax
```
m365 pa environment list [options]
```

### Example
```
m365 pa environment list

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---
