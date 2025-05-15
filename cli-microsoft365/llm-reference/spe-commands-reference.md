<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - SPE Commands Reference

*This is an automatically generated condensed reference of all SPE commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-05-15*

---

## Table of Contents

- [container-activate](#container-activate)
- [container-get](#container-get)
- [container-list](#container-list)
- [container-permission-list](#container-permission-list)
- [containertype-add](#containertype-add)
- [containertype-get](#containertype-get)
- [containertype-list](#containertype-list)

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
:::note
You can only create one Trial Container per tenant, a single application registration can only contain one Container and a tenant can contain a maximum of five Containers in total.
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

---
