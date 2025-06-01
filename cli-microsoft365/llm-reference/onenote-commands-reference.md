<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - ONENOTE Commands Reference

*This is an automatically generated condensed reference of all ONENOTE commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-06-01*

---

## Table of Contents

- [notebook-add](#notebook-add)
- [notebook-list](#notebook-list)
- [page-list](#page-list)

---

## notebook-add

### Syntax
```
m365 onenote notebook add [options]
```

### Example
```
m365 onenote notebook add --name "Private Notebook"```

---

## notebook-list

### Syntax
```
m365 onenote notebook list [options]
```

### Example
```
m365 onenote notebook list

m365 onenote notebook list --groupId EXAMPLE-GUID-PLACEHOLDER

m365 onenote notebook list --groupName "MyGroup"

m365 onenote notebook list --userName user1@contoso.onmicrosoft.com

m365 onenote notebook list --userId EXAMPLE-GUID-PLACEHOLDER

m365 onenote notebook list --webUrl https://contoso.sharepoint.com/sites/testsite

```

---

## page-list

### Syntax
```
m365 onenote page list [options]
```

### Example
```
m365 onenote page list

m365 onenote page list --groupId EXAMPLE-GUID-PLACEHOLDER

m365 onenote page list --groupName "MyGroup"

m365 onenote page list --userName user1@contoso.onmicrosoft.com

m365 onenote page list --userId EXAMPLE-GUID-PLACEHOLDER

m365 onenote page list --webUrl https://contoso.sharepoint.com/sites/testsite

```

### Remarks
When we don't specify either `userId`, `userName`, `groupId`, `groupName` or `webUrl`, the OneNote pages will be retrieved of the currently logged in user.



---
