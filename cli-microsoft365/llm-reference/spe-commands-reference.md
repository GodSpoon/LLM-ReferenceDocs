<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - SPE Commands Reference

*This is an automatically generated condensed reference of all SPE commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-06-01*

---

## Table of Contents

- [container-activate](#container-activate)
- [container-add](#container-add)
- [container-get](#container-get)
- [container-list](#container-list)
- [container-permission-list](#container-permission-list)
- [container-recyclebinitem-list](#container-recyclebinitem-list)
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

---

## containertype-add

### Syntax
```
m365 spe containertype add [options]
```

### Example
```
m365 spe containertype add --name 'trial container' --applicationId 'EXAMPLE-GUID-PLACEHOLDER' --trial

m365 spe containertype add --name 'standard container' --applicationId 'EXAMPLE-GUID-PLACEHOLDER' --azureSubscriptionId 'EXAMPLE-GUID-PLACEHOLDER' --region 'West Europe' --resourceGroup 'Standard group'

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

:::note

You can only create one Trial container type per tenant, a single application registration can only contain one container type and a tenant can contain a maximum of five containers types in total.

:::



---

## containertype-get

### Syntax
```
m365 containertype get [options]
```

### Example
```
m365 spe containertype get --id 'EXAMPLE-GUID-PLACEHOLDER'

m365 spe containertype get --name 'test container'

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

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
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

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
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---
