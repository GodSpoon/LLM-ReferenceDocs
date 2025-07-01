<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - ONEDRIVE Commands Reference

*This is an automatically generated condensed reference of all ONEDRIVE commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-07-01*

---

## Table of Contents

- [onedrive-list](#onedrive-list)
- [report-activityfilecounts](#report-activityfilecounts)
- [report-activityusercounts](#report-activityusercounts)
- [report-activityuserdetail](#report-activityuserdetail)
- [report-usageaccountcounts](#report-usageaccountcounts)
- [report-usageaccountdetail](#report-usageaccountdetail)
- [report-usagefilecounts](#report-usagefilecounts)
- [report-usagestorage](#report-usagestorage)

---

## onedrive-list

### Syntax
```
m365 onedrive list [options]
```

### Example
```
m365 onedrive list

```

---

## report-activityfilecounts

### Syntax
```
m365 onedrive report activityfilecounts [options]
```

### Example
```
m365 onedrive report activityfilecounts --period D7

m365 onedrive report activityfilecounts --period D7 --output text > "activityfilecounts.txt"

m365 onedrive report activityfilecounts --period D7 --output json > "activityfilecounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-activityusercounts

### Syntax
```
m365 onedrive report activityusercounts [options]
```

### Example
```
m365 onedrive report activityusercounts --period D7

m365 onedrive report activityusercounts --period D7 --output text > "activityusercounts.txt"

m365 onedrive report activityusercounts --period D7 --output json > "activityusercounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-activityuserdetail

### Syntax
```
m365 onedrive report activityuserdetail [options]
```

### Example
```
m365 onedrive report activityuserdetail --period D7

m365 onedrive report activityuserdetail --date 2019-05-01

m365 onedrive report activityuserdetail --period D7 --output text > "onedriveactivityuserdetail.txt"

m365 onedrive report activityuserdetail --period D7 --output json > "onedriveactivityuserdetail.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-usageaccountcounts

### Syntax
```
m365 onedrive report usageaccountcounts [options]
```

### Example
```
m365 onedrive report usageaccountcounts --period D7

m365 onedrive report usageaccountcounts --period D7 --output text > "usageaccountcounts.txt"

m365 onedrive report usageaccountcounts --period D7 --output json > "usageaccountcounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::

Any site on which users viewed, modified, uploaded, downloaded, shared, or synced files is considered an active site



---

## report-usageaccountdetail

### Syntax
```
m365 onedrive report usageaccountdetail [options]
```

### Example
```
m365 onedrive report usageaccountdetail --period D7

m365 onedrive report usageaccountdetail --date 2019-05-01

m365 onedrive report usageaccountdetail --period D7 --output text > "onedriveusageaccountdetail.txt"

m365 onedrive report usageaccountdetail --period D7 --output json > "onedriveusageaccountdetail.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-usagefilecounts

### Syntax
```
m365 onedrive report usagefilecounts [options]
```

### Example
```
m365 onedrive report usagefilecounts --period D7

m365 onedrive report usagefilecounts --period D7 --output text > "usagefilecounts.txt"

m365 onedrive report usagefilecounts --period D7 --output json > "usagefilecounts.json"

```

### Remarks
A file is considered active if it has been saved, synced, modified, or shared within the specified time period.

:::info

This command supports only csv and json output.

:::



---

## report-usagestorage

### Syntax
```
m365 onedrive report usagestorage [options]
```

### Example
```
m365 onedrive report usagestorage --period D7

m365 onedrive report usagestorage --period D7 --output text > "usagestorage.txt"

m365 onedrive report usagestorage --period D7 --output json > "usagestorage.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---
