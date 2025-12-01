<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - SPE Commands Reference

*This is an automatically generated condensed reference of all SPE commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-12-01*

---

## Table of Contents

- [container-activate](#container-activate)
- [container-add](#container-add)
- [container-get](#container-get)
- [container-list](#container-list)
- [container-permission-list](#container-permission-list)
- [container-recyclebinitem-list](#container-recyclebinitem-list)
- [container-recyclebinitem-restore](#container-recyclebinitem-restore)
- [container-remove](#container-remove)
- [containertype-add](#containertype-add)
- [containertype-get](#containertype-get)
- [containertype-list](#containertype-list)
- [containertype-remove](#containertype-remove)

---

## container-activate

### Syntax
```
m365 spe container activate [options]
```

### Example
```
m365 spe container activate --id "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER"

```

---

## container-add

### Syntax
```
m365 spe container add [options]
```

### Example
```
m365 spe container add --name Invoices --containerTypeId EXAMPLE-GUID-PLACEHOLDER

m365 spe container add --name Invoices --containerTypeName "Invoice app container type"

m365 spe container add --name Invoices --containerTypeId EXAMPLE-GUID-PLACEHOLDER --ocrEnabled true --itemMajorVersionLimit 200 --itemVersioningEnabled true

```

### Remarks
:::warning

The command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## container-get

### Syntax
```
m365 spe container get [options]
```

### Example
```
m365 spe container get --id "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER"

```

---

## container-list

### Syntax
```
m365 spe container list [options]
```

### Example
```
m365 spe container list --containerTypeId "EXAMPLE-GUID-PLACEHOLDER"

m365 spe container list --containerTypeName "trial container"

```

### Remarks
:::warning

The command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## container-permission-list

### Syntax
```
m365 spe container permission list [options]
```

### Example
```
m365 spe container permission list --containerId "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER"

```

---

## container-recyclebinitem-list

### Syntax
```
m365 spe container recyclebinitem list [options]
```

### Example
```
m365 spe container recyclebinitem list --containerTypeId "EXAMPLE-GUID-PLACEHOLDER"

m365 spe container recyclebinitem list --containerTypeName "My container type name"

```

### Remarks
:::warning

The command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## container-recyclebinitem-restore

### Syntax
```
m365 spe container recyclebinitem restore [options]
```

### Example
```
m365 spe container recyclebinitem restore --id "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER"

m365 spe container recyclebinitem restore --containerTypeId "EXAMPLE-GUID-PLACEHOLDER" --name "Invoices"

m365 spe container recyclebinitem restore --containerTypeName "My container type name" --name "Invoices"

```

### Remarks
:::warning

The command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## container-remove

### Syntax
```
m365 spe container remove [options]
```

### Example
```
m365 spe container remove --id "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER"

m365 spe container remove --id "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER" --recycle

m365 spe container remove --name "My Application Storage Container" --containerTypeId EXAMPLE-GUID-PLACEHOLDER

m365 spe container remove --name "My Application Storage Container" --containerTypeName "My Application Container Type"

```

### Remarks
:::warning

The command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## containertype-add

### Syntax
```
m365 spe containertype add [options]
```

### Example
```
m365 spe containertype add --name 'trial container' --applicationId 'EXAMPLE-GUID-PLACEHOLDER' --billingType trial```

### Remarks
:::warning

The command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

:::note

The tenant must own the application that is assigned as the owner of the container type.

:::

:::note

You can only create **one** Trial container type per tenant, a single application registration can only contain **one** container type and a tenant can contain a maximum of **five** containers types in total.

:::

The registration of a container type in a newly created tenant can fail if the tenant isn't yet fully ready. You might need to wait at least an hour before you can register a container type in a new tenant.



---

## containertype-get

### Syntax
```
m365 containertype get [options]
```

### Example
```
m365 spe containertype get --id EXAMPLE-GUID-PLACEHOLDER

m365 spe containertype get --name 'Container Type 1'

```

### Remarks
:::warning

The command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## containertype-list

### Syntax
```
m365 spe containertype list [options]
```

### Example
```
m365 spe containertype list

```

### Remarks
:::warning

The command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## containertype-remove

### Syntax
```
m365 spe containertype remove [options]
```

### Example
```
m365 spe containertype remove --id EXAMPLE-GUID-PLACEHOLDER

m365 spe containertype remove --name 'My container type'

```

### Remarks
:::danger[Important]

This command relies on a different API endpoint due to current API limitations. As a result, it requires different permissions than other `spe containertype` commands. We plan to align the permissions in the future once these limitations are resolved.

:::



---
