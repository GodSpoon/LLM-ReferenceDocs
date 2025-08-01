<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - SPP Commands Reference

*This is an automatically generated condensed reference of all SPP commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-08-01*

---

## Table of Contents

- [contentcenter-list](#contentcenter-list)
- [model-apply](#model-apply)
- [model-get](#model-get)
- [model-list](#model-list)
- [model-remove](#model-remove)

---

## contentcenter-list

### Syntax
```
m365 spp contentcenter list [options]
```

### Example
```
m365 spp contentcenter list

```

### Remarks
:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::



---

## model-apply

### Syntax
```
m365 spp model apply [options]
```

### Example
```
m365 spp model apply --webUrl "https://contoso.sharepoint.com" --contentCenterUrl "https://contoso.sharepoint.com/sites/ContentCenter" --id "EXAMPLE-GUID-PLACEHOLDER" --listTitle "Shared Documents"```

---

## model-get

### Syntax
```
m365 spp model get [options]
```

### Example
```
m365 spp model get --siteUrl "https://contoso.sharepoint.com/sites/ContentCenter" --id "EXAMPLE-GUID-PLACEHOLDER"

m365 spp model get --siteUrl "https://contoso.sharepoint.com/sites/ContentCenter" --title "climicrosoft365Model"

```

---

## model-list

### Syntax
```
m365 spp model list [options]
```

### Example
```
m365 spp model list --siteUrl https://contoso.sharepoint.com/sites/ContentCenter

```

---

## model-remove

### Syntax
```
m365 spp model remove [options]
```

### Example
```
m365 spp model remove --siteUrl "https://contoso.sharepoint.com/sites/ContentCenter" --id "EXAMPLE-GUID-PLACEHOLDER"

m365 spp model remove --siteUrl "https://contoso.sharepoint.com/sites/ContentCenter" --title "climicrosoft365Model.classifier"

```

### Remarks
:::note

The model must be removed from all libraries before it can be deleted.

:::



---
