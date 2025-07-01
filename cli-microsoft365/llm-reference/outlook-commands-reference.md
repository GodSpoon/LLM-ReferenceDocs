<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - OUTLOOK Commands Reference

*This is an automatically generated condensed reference of all OUTLOOK commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-07-01*

---

## Table of Contents

- [mailbox-settings-get](#mailbox-settings-get)
- [mailbox-settings-set](#mailbox-settings-set)
- [mail-send](#mail-send)
- [message-get](#message-get)
- [message-list](#message-list)
- [message-move](#message-move)
- [message-remove](#message-remove)
- [report-mailactivitycounts](#report-mailactivitycounts)
- [report-mailactivityusercounts](#report-mailactivityusercounts)
- [report-mailactivityuserdetail](#report-mailactivityuserdetail)
- [report-mailappusageappsusercounts](#report-mailappusageappsusercounts)
- [report-mailappusageusercounts](#report-mailappusageusercounts)
- [report-mailappusageuserdetail](#report-mailappusageuserdetail)
- [report-mailappusageversionsusercounts](#report-mailappusageversionsusercounts)
- [report-mailboxusagedetail](#report-mailboxusagedetail)
- [report-mailboxusagemailboxcount](#report-mailboxusagemailboxcount)
- [EXAMPLE_SECRET_VALUE_PLACEHOLDER](#EXAMPLE_SECRET_VALUE_PLACEHOLDER)
- [report-mailboxusagestorage](#report-mailboxusagestorage)
- [room-list](#room-list)
- [roomlist-list](#roomlist-list)

---

## mailbox-settings-get

### Syntax
```
m365 outlook mailbox settings get [options]
```

### Example
```
m365 outlook mailbox settings get

m365 outlook mailbox settings get --userId EXAMPLE-GUID-PLACEHOLDER

```

---

## mailbox-settings-set

### Syntax
```
m365 outlook mailbox settings set [options]
```

### Example
```
m365 outlook mailbox settings set --dateFormat 'dd.MM.yyyy' --timeFormat 'H:mm' --timeZone 'Central Europe Standard Time' --language 'en-US'```

---

## mail-send

### Syntax
```
m365 outlook mail send [options]
```

### Example
```
m365 outlook mail send --to chris@contoso.com --subject "DG2000 Data Sheets" --bodyContents "The latest data sheets are in the team site"```

---

## message-get

### Syntax
```
m365 outlook message get [options]
```

### Example
```
m365 outlook message get --id EXAMPLE_SECRET_VALUE_PLACEHOLDER=

m365 outlook message get --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userName sharedmailbox@tenant.com

m365 outlook message get --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userId EXAMPLE-GUID-PLACEHOLDER

m365 outlook message get --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userName user@tenant.com

```

---

## message-list

### Syntax
```
m365 outlook message list [options]
```

### Example
```
m365 outlook message list --folderName Archive --startTime 2023-12-16T18:28:48.6964197Z --endTime 2024-02-01

m365 outlook message list --folderId EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userId EXAMPLE-GUID-PLACEHOLDER

m365 outlook message list --folderName inbox --userName john@contoso.com

```

---

## message-move

### Syntax
```
m365 outlook message move [options]
```

### Example
```
m365 outlook message move --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --sourceFolderId EXAMPLE_SECRET_VALUE_PLACEHOLDER= --targetFolderId EXAMPLE_SECRET_VALUE_PLACEHOLDER=

m365 outlook message move --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --sourceFolderName Inbox --targetFolderName "Project X"

m365 outlook message move --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --sourceFolderName inbox --targetFolderName archive

```

---

## message-remove

### Syntax
```
m365 outlook message remove [options]
```

### Example
```
m365 outlook message remove --id EXAMPLE_SECRET_VALUE_PLACEHOLDER=

m365 outlook message remove --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userName sharedmailbox@contoso.com

m365 outlook message remove --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userId EXAMPLE-GUID-PLACEHOLDER

m365 outlook message remove --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --userName john.doe@contoso.com

```

### Remarks
:::warning

This command will permanently delete the Outlook message. To move a message to the trash bin, use [outlook message move](./message-move.mdx) instead.

:::



---

## report-mailactivitycounts

### Syntax
```
m365 outlook report mailactivitycounts [options]
```

### Example
```
m365 outlook report mailactivitycounts --period D7

m365 outlook report mailactivitycounts --period D7 --output text > "mailactivitycounts.txt"

m365 outlook report mailactivitycounts --period D7 --output json > "mailactivitycounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-mailactivityusercounts

### Syntax
```
m365 outlook report mailactivityusercounts [options]
```

### Example
```
m365 outlook report mailactivityusercounts --period D7

m365 outlook report mailactivityusercounts --period D7 --output text > "mailactivityusercounts.txt"

m365 outlook report mailactivityusercounts --period D7 --output json > "mailactivityusercounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-mailactivityuserdetail

### Syntax
```
m365 outlook report mailactivityuserdetail [options]
```

### Example
```
m365 outlook report mailactivityuserdetail --period D7

m365 outlook report mailactivityuserdetail --date 2019-05-01

m365 outlook report mailactivityuserdetail --period D7 --output text > "mailactivityuserdetail.txt"

m365 outlook report mailactivityuserdetail --period D7 --output json > "mailactivityuserdetail.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-mailappusageappsusercounts

### Syntax
```
m365 outlook report mailappusageappsusercounts [options]
```

### Example
```
m365 outlook report mailappusageappsusercounts --period D7

m365 outlook report mailappusageappsusercounts --period D7 --output text > "mailappusageappsusercounts.txt"

m365 outlook report mailappusageappsusercounts --period D7 --output json > "mailappusageappsusercounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-mailappusageusercounts

### Syntax
```
m365 outlook report mailappusageusercounts [options]
```

### Example
```
m365 outlook report mailappusageusercounts --period D7

m365 outlook report mailappusageusercounts --period D7 --output text > "mailappusageusercounts.txt"

m365 outlook report mailappusageusercounts --period D7 --output json > "mailappusageusercounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-mailappusageuserdetail

### Syntax
```
m365 outlook report mailappusageuserdetail [options]
```

### Example
```
m365 outlook report mailappusageuserdetail --period D7

m365 outlook report mailappusageuserdetail --date 2019-05-01

m365 outlook report mailappusageuserdetail --period D7 --output text > "mailappusageuserdetail.txt"

m365 outlook report mailappusageuserdetail --period D7 --output json > "mailappusageuserdetail.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-mailappusageversionsusercounts

### Syntax
```
m365 outlook report mailappusageversionsusercounts [options]
```

### Example
```
m365 outlook report mailappusageversionsusercounts --period D7

m365 outlook report mailappusageversionsusercounts --period D7 --output text > "mailappusageversionsusercounts.txt"

m365 outlook report mailappusageversionsusercounts --period D7 --output json > "mailappusageversionsusercounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-mailboxusagedetail

### Syntax
```
m365 outlook report mailboxusagedetail [options]
```

### Example
```
m365 outlook report mailboxusagedetail --period D7

m365 outlook report mailboxusagedetail --period D7 --output text > "mailboxusagedetail.txt"

m365 outlook report mailboxusagedetail --period D7 --output json > "mailboxusagedetail.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-mailboxusagemailboxcount

### Syntax
```
m365 outlook report mailboxusagemailboxcount [options]
```

### Example
```
m365 outlook report mailboxusagemailboxcount --period D7

m365 outlook report mailboxusagemailboxcount --period D7 --output text > "mailboxusagemailboxcount.txt"

m365 outlook report mailboxusagemailboxcount --period D7 --output json > "mailboxusagemailboxcount.json"

```

### Remarks
A mailbox is considered active if the user sent or read any email.

:::info

This command supports only csv and json output.

:::



---

## EXAMPLE_SECRET_VALUE_PLACEHOLDER

### Syntax
```
m365 outlook report mailboxusagequotastatusmailboxcounts [options]
```

### Example
```
m365 outlook report mailboxusagequotastatusmailboxcounts --period D7

m365 outlook report mailboxusagequotastatusmailboxcounts --period D7 --output text > "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

m365 outlook report mailboxusagequotastatusmailboxcounts --period D7 --output json > "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-mailboxusagestorage

### Syntax
```
m365 outlook report mailboxusagestorage [options]
```

### Example
```
m365 outlook report mailboxusagestorage --period D7

m365 outlook report mailboxusagestorage --period D7 --output text > "mailboxusagestorage.txt"

m365 outlook report mailboxusagestorage --period D7 --output json > "mailboxusagestorage.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## room-list

### Syntax
```
m365 outlook room list [options]
```

### Example
```
m365 outlook room list

m365 outlook room list --roomlistEmail "bldg2@contoso.com"

```

---

## roomlist-list

### Syntax
```
m365 outlook roomlist list [options]
```

### Example
```
m365 outlook roomlist list

```

---
