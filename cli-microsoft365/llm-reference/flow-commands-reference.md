<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - FLOW Commands Reference

*This is an automatically generated condensed reference of all FLOW commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-05-15*

---

## Table of Contents

- [environment-get](#environment-get)
- [environment-list](#environment-list)
- [flow-disable](#flow-disable)
- [flow-enable](#flow-enable)
- [flow-export](#flow-export)
- [flow-get](#flow-get)
- [flow-list](#flow-list)
- [flow-remove](#flow-remove)
- [owner-ensure](#owner-ensure)
- [owner-list](#owner-list)
- [owner-remove](#owner-remove)
- [recyclebinitem-list](#recyclebinitem-list)
- [recyclebinitem-restore](#recyclebinitem-restore)
- [run-cancel](#run-cancel)
- [run-get](#run-get)
- [run-list](#run-list)
- [run-resubmit](#run-resubmit)

---

## environment-get

### Syntax
```
m365 flow environment get [options]
```

### Example
```
m365 flow environment get --name EXAMPLE_SECRET_VALUE_PLACEHOLDER

m365 flow environment get

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
m365 flow environment list [options]
```

### Example
```
m365 flow environment list

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## flow-disable

### Syntax
```
m365 flow disable [options]
```

### Example
```
m365 flow disable --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name EXAMPLE-GUID-PLACEHOLDER

m365 flow disable --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name EXAMPLE-GUID-PLACEHOLDER --asAdmin

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

By default, the command will try to disable Power Automate flows you own. If you want to disable Power Automate flows owned by another user, use the `asAdmin` flag.

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

If the Power Automate flow with the name you specified doesn't exist, you will get the `The caller with object id 'abc' does not have permission for connection 'xyz' under Api 'shared_logicflows'.` error. If you try to disable a non-existing flow as admin, you will get the `Could not find flow 'xyz'.` error.



---

## flow-enable

### Syntax
```
m365 flow enable [options]
```

### Example
```
m365 flow enable --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name EXAMPLE-GUID-PLACEHOLDER

m365 flow enable --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name EXAMPLE-GUID-PLACEHOLDER --asAdmin

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

By default, the command will try to enable Power Automate flows you own. If you want to enable flows owned by another user, use the `asAdmin` flag.

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

If the Power Automate flow with the name you specified doesn't exist, you will get the `The caller with object id 'abc' does not have permission for connection 'xyz' under Api 'shared_logicflows'.` error. If you try to enable a non-existing flow as admin, you will get the `Could not find flow 'xyz'.` error.



---

## flow-export

### Syntax
```
m365 flow export [options]
```

### Example
```
m365 flow export --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name EXAMPLE-GUID-PLACEHOLDER```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

If the Power Automate flow with the name you specified doesn't exist, you will get the `The caller with object id 'abc' does not have permission for connection 'xyz' under Api 'shared_logicflows'.` error.



---

## flow-get

### Syntax
```
m365 flow get [options]
```

### Example
```
m365 flow get --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name EXAMPLE-GUID-PLACEHOLDER

m365 flow get --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name EXAMPLE-GUID-PLACEHOLDER --asAdmin

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

By default, the command will try to retrieve Power Automate flows you own. If you want to retrieve a flow owned by another user, use the `asAdmin` flag.

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

If the Power Automate flow with the name you specified doesn't exist, you will get the `The caller with object id 'abc' does not have permission for connection 'xyz' under Api 'shared_logicflows'.` error. If you try to retrieve a non-existing flow as admin, you will get the `Could not find flow 'xyz'.` error.



---

## flow-list

### Syntax
```
m365 flow list [options]
```

### Example
```
m365 flow list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER

m365 flow list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --asAdmin

m365 flow list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --sharingStatus sharedWithMe

m365 flow list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --sharingStatus personal --includeSolutions

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

When you specify a value for `sharingStatus`, consider the following:



---

## flow-remove

### Syntax
```
m365 flow remove [options]
```

### Example
```
m365 flow remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name EXAMPLE-GUID-PLACEHOLDER

m365 flow remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name EXAMPLE-GUID-PLACEHOLDER --force

m365 flow remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name EXAMPLE-GUID-PLACEHOLDER --asAdmin

m365 flow remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name EXAMPLE-GUID-PLACEHOLDER --asAdmin --force

```

### Remarks
By default, the command will try to remove a Power Automate flow you own. If you want to remove a Flow owned by another user, use the `asAdmin` flag.

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

If the Power Automate flow with the name you specified doesn't exist, you will get the `Error: Resource 'abc' does not exist in environment 'xyz'` error.



---

## owner-ensure

### Syntax
```
m365 flow owner ensure [options]
```

### Example
```
m365 flow owner ensure --userId EXAMPLE-GUID-PLACEHOLDER --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName EXAMPLE-GUID-PLACEHOLDER --roleName CanEdit```

---

## owner-list

### Syntax
```
m365 flow owner list [options]
```

### Example
```
m365 flow owner list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName EXAMPLE-GUID-PLACEHOLDER

m365 flow owner list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName EXAMPLE-GUID-PLACEHOLDER --asAdmin

```

---

## owner-remove

### Syntax
```
m365 flow owner remove [options]
```

### Example
```
m365 flow owner remove --userId EXAMPLE-GUID-PLACEHOLDER --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName EXAMPLE-GUID-PLACEHOLDER --force```

---

## recyclebinitem-list

### Syntax
```
m365 flow recyclebinitem list [options]
```

### Example
```
m365 flow recyclebinitem list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reaches general availability.

:::

:::info

To use this command, you must be a Global or Power Platform administrator.

:::

A Power Automate flow is soft-deleted when:

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.



---

## recyclebinitem-restore

### Syntax
```
m365 flow recyclebinitem restore [options]
```

### Example
```
m365 flow recyclebinitem restore --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reaches general availability.

:::

:::info

To use this command, you must be a Global or Power Platform administrator.

:::

When a Power Automate flow is restored, it will be automatically disabled. To make it operational again, you must [enable](../flow-enable.mdx) it.

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.



---

## run-cancel

### Syntax
```
m365 flow run cancel [options]
```

### Example
```
m365 flow run cancel --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName EXAMPLE-GUID-PLACEHOLDER --name 08586653536760200319026785874CU62

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

If the flow with the name you specified doesn't exist, you will get the `The caller with object id 'abc' does not have permission for connection 'xyz' under Api 'shared_logicflows'.` error.

If the run with the name you specified doesn't exist, you will get the `The workflow 'xyz' run 'abc' could not be found.` error.



---

## run-get

### Syntax
```
m365 flow run get [options]
```

### Example
```
m365 flow run get --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName EXAMPLE-GUID-PLACEHOLDER --name 08586653536760200319026785874CU62```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

If the Microsoft Flow with the name you specified doesn't exist, you will get the `The caller with object id 'abc' does not have permission for connection 'xyz' under Api 'shared_logicflows'.` error.

If the run with the name you specified doesn't exist, you will get the `The provided workflow run name is not valid.` error.

If the option `withTrigger` is specified, but the trigger does not contain an outputsLink such as for example with a `Recurrence` trigger, this option will be ignored.



---

## run-list

### Syntax
```
m365 flow run list [options]
```

### Example
```
m365 flow run list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName EXAMPLE-GUID-PLACEHOLDER```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

If the Microsoft Flow with the name you specified doesn't exist, you will get the `The caller with object id 'abc' does not have permission for connection 'xyz' under Api 'shared_logicflows'.` error.

When using `--withTrigger`, extra requests will get fired for each retrieved flow run. This has an impact on the time the command takes to run.  



---

## run-resubmit

### Syntax
```
m365 flow run resubmit [options]
```

### Example
```
m365 flow run resubmit --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName EXAMPLE-GUID-PLACEHOLDER --name 08586653536760200319026785874CU62

m365 flow run resubmit --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName EXAMPLE-GUID-PLACEHOLDER --name 08586653536760200319026785874CU62 --force

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

If the Microsoft Flow with the name you specified doesn't exist, you will get the `The caller with object id 'abc' does not have permission for connection 'xyz' under Api 'shared_logicflows'.` error.

If the run with the name you specified doesn't exist, you will get the `The workflow 'xyz' run 'abc' could not be found.` error.



---
