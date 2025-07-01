<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - SKYPE Commands Reference

*This is an automatically generated condensed reference of all SKYPE commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-07-01*

---

## Table of Contents

- [report-activitycounts](#report-activitycounts)
- [report-activityusercounts](#report-activityusercounts)
- [report-activityuserdetail](#report-activityuserdetail)

---

## report-activitycounts

### Syntax
```
m365 skype report activitycounts [options]
```

### Example
```
m365 skype report activitycounts --period D7

m365 skype report activitycounts --period D7 --output text > "activitycounts.txt"

m365 skype report activitycounts --period D7 --output json > "activitycounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-activityusercounts

### Syntax
```
m365 skype report activityusercounts [options]
```

### Example
```
m365 skype report activityusercounts --period D7

m365 skype report activityusercounts --period D7 --output text > "activityusercounts.txt"

m365 skype report activityusercounts --period D7 --output json > "activityusercounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-activityuserdetail

### Syntax
```
m365 skype report activityuserdetail [options]
```

### Example
```
m365 skype report activityuserdetail --period D7

m365 skype report activityuserdetail --date 2019-05-01

m365 skype report activityuserdetail --period D7 --output text > "activityuserdetail.txt"

m365 skype report activityuserdetail --period D7 --output json > "activityuserdetail.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---
