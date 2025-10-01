<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - PP Commands Reference

*This is an automatically generated condensed reference of all PP commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-10-01*

---

## Table of Contents

- [aibuildermodel-get](#aibuildermodel-get)
- [aibuildermodel-list](#aibuildermodel-list)
- [aibuildermodel-remove](#aibuildermodel-remove)
- [copilot-get](#copilot-get)
- [copilot-list](#copilot-list)
- [copilot-remove](#copilot-remove)
- [dataverse-table-get](#dataverse-table-get)
- [dataverse-table-list](#dataverse-table-list)
- [dataverse-table-remove](#dataverse-table-remove)
- [dataverse-table-row-list](#dataverse-table-row-list)
- [dataverse-table-row-remove](#dataverse-table-row-remove)
- [environment-get](#environment-get)
- [environment-list](#environment-list)
- [gateway-get](#gateway-get)
- [gateway-list](#gateway-list)
- [managementapp-add](#managementapp-add)
- [managementapp-list](#managementapp-list)
- [solution-get](#solution-get)
- [solution-list](#solution-list)
- [solution-publish](#solution-publish)
- [solution-publisher-add](#solution-publisher-add)
- [solution-publisher-get](#solution-publisher-get)
- [solution-publisher-list](#solution-publisher-list)
- [solution-publisher-remove](#solution-publisher-remove)
- [solution-remove](#solution-remove)
- [tenant-settings-list](#tenant-settings-list)
- [tenant-settings-set](#tenant-settings-set)
- [website-get](#website-get)

---

## aibuildermodel-get

### Syntax
```
m365 pp aibuildermodel get [options]
```

### Example
```
m365 pp aibuildermodel get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "Document Processing 11/29/2022, 12:58:43 PM"

m365 pp aibuildermodel get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --id "EXAMPLE-GUID-PLACEHOLDER" --asAdmin

```

---

## aibuildermodel-list

### Syntax
```
m365 pp aibuildermodel list [options]
```

### Example
```
m365 pp aibuildermodel list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

m365 pp aibuildermodel list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --asAdmin

```

---

## aibuildermodel-remove

### Syntax
```
m365 pp aibuildermodel remove [options]
```

### Example
```
m365 pp aibuildermodel remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "AI Builder Model Name"

m365 pp aibuildermodel remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "AI Builder Model Name" --force

m365 pp aibuildermodel remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER  --asAdmin

```

---

## copilot-get

### Syntax
```
m365 pp copilot get [options]
```

### Example
```
m365 pp copilot get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "CLI 365 Copilot"

m365 pp copilot get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "CLI 365 Copilot" --asAdmin

m365 pp copilot get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --id "EXAMPLE-GUID-PLACEHOLDER"

m365 pp copilot get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --id "EXAMPLE-GUID-PLACEHOLDER" --asAdmin

```

---

## copilot-list

### Syntax
```
m365 pp copilot list [options]
```

### Example
```
m365 pp copilot list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

m365 pp copilot list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --asAdmin

```

---

## copilot-remove

### Syntax
```
m365 pp copilot remove [options]
```

### Example
```
m365 pp copilot remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Chatbot Name"

m365 pp copilot remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER --force

m365 pp copilot remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Chatbot Name" --asAdmin

```

---

## dataverse-table-get

### Syntax
```
m365 pp dataverse table get [options]
```

### Example
```
m365 pp dataverse table get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "aaduser"

m365 pp dataverse table get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "aaduser" --asAdmin

```

---

## dataverse-table-list

### Syntax
```
m365 pp dataverse table list [options]
```

### Example
```
m365 pp dataverse table list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

m365 pp dataverse table list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --asAdmin

```

---

## dataverse-table-remove

### Syntax
```
m365 pp dataverse table remove [options]
```

### Example
```
m365 pp dataverse table remove --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "aaduser"

m365 pp dataverse table remove --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "aaduser" --asAdmin

m365 pp dataverse table remove --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "aaduser" --force

```

---

## dataverse-table-row-list

### Syntax
```
m365 pp dataverse table row list [options]
```

### Example
```
m365 pp dataverse table row list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --entitySetName "cr6c3_accounts"

m365 pp dataverse table row list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --tableName "cr6c3_account"

m365 pp dataverse table row list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --entitySetName "cr6c3_accounts" --asAdmin

```

---

## dataverse-table-row-remove

### Syntax
```
m365 pp dataverse table row remove [options]
```

### Example
```
m365 pp dataverse table row remove --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --tableName "aadusers" --id "EXAMPLE-GUID-PLACEHOLDER"```

---

## environment-get

### Syntax
```
m365 pp environment get [options]
```

### Example
```
m365 pp environment get --name EXAMPLE_SECRET_VALUE_PLACEHOLDER

m365 pp environment get --name EXAMPLE_SECRET_VALUE_PLACEHOLDER --asAdmin

m365 pp environment get --default

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

Register CLI for Microsoft 365 or Microsoft Entra application as a management application for the Power Platform using 

`m365 pp managementapp add [options]`

:::



---

## environment-list

### Syntax
```
m365 pp environment list [options]
```

### Example
```
m365 pp environment list

m365 pp environment list --asAdmin

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.
Register CLI for Microsoft 365 or Microsoft Entra application as a management application for the Power Platform using m365 pp managementapp add [options]

:::



---

## gateway-get

### Syntax
```
m365 pp gateway get [options]
```

### Example
```
m365 pp gateway get --id EXAMPLE-GUID-PLACEHOLDER

```

---

## gateway-list

### Syntax
```
m365 pp gateway list [options]
```

### Example
```
m365 pp gateway list

```

---

## managementapp-add

### Syntax
```
m365 pp managementapp add [options]
```

### Example
```
m365 pp managementapp add --appId EXAMPLE-GUID-PLACEHOLDER

m365 pp managementapp add --objectId EXAMPLE-GUID-PLACEHOLDER

m365 pp managementapp add --name "My app"

```

### Remarks
To execute this command the first time you'll need sign in using the Microsoft Azure PowerShell application registration. You can do this by executing `m365 login --appId EXAMPLE-GUID-PLACEHOLDER`. To register the Microsoft Entra application registration that CLI for Microsoft 365 uses by default, execute `m365 pp managementapp add--appId EXAMPLE-GUID-PLACEHOLDER`.

For best performance use the `appId` option to reference the Microsoft Entra application registration to update. If you use `objectId` or `name`, this command will first need to find the corresponding `appId` for that application.

If the command finds multiple Microsoft Entra application registrations with the specified app name, it will prompt you to disambiguate which app it should use, listing the discovered object IDs.



---

## managementapp-list

### Syntax
```
m365 pp managementapp list [options]
```

### Example
```
m365 pp managementapp list

```

---

## solution-get

### Syntax
```
m365 pp solution get [options]
```

### Example
```
m365 pp solution get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "Default"

m365 pp solution get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "Default" --asAdmin

m365 pp solution get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --id "EXAMPLE-GUID-PLACEHOLDER"

m365 pp solution get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --id "EXAMPLE-GUID-PLACEHOLDER" --asAdmin

```

---

## solution-list

### Syntax
```
m365 pp solution list [options]
```

### Example
```
m365 pp solution list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

m365 pp solution list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --asAdmin

```

---

## solution-publish

### Syntax
```
m365 pp solution publish [options]
```

### Example
```
m365 pp solution publish --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Solution Name"

m365 pp solution publish --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER --wait

m365 pp solution publish --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Solution Name" --asAdmin

```

---

## solution-publisher-add

### Syntax
```
m365 pp solution publisher add [options]
```

### Example
```
m365 pp solution publisher add --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "Contoso" --displayName "Contoso" --prefix "new" --choiceValuePrefix 10000

m365 pp solution publisher add --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "Contoso" --displayName "Contoso" --prefix "new" --choiceValuePrefix 10000 --asAdmin

```

---

## solution-publisher-get

### Syntax
```
m365 pp solution publisher get [options]
```

### Example
```
m365 pp solution publisher get --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "MicrosoftCorporation"```

---

## solution-publisher-list

### Syntax
```
m365 pp solution publisher list [options]
```

### Example
```
m365 pp solution publisher list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

m365 pp solution publisher list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --asAdmin

```

---

## solution-publisher-remove

### Syntax
```
m365 pp solution publisher remove [options]
```

### Example
```
m365 pp solution publisher remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Publisher Name"

m365 pp solution publisher remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Publisher Name" --force

m365 pp solution publisher remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Publisher Name" --asAdmin

m365 pp solution publisher remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --id EXAMPLE-GUID-PLACEHOLDER

```

---

## solution-remove

### Syntax
```
m365 pp solution remove [options]
```

### Example
```
m365 pp solution remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name "Solution Name"```

---

## tenant-settings-list

### Syntax
```
m365 pp tenant settings list [options]
```

### Example
```
m365 pp tenant settings list

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## tenant-settings-set

### Syntax
```
m365 pp tenant settings set [options]
```

### Example
```
m365 pp tenant settings set --EXAMPLE_SECRET_VALUE_PLACEHOLDER true --EXAMPLE_SECRET_VALUE_PLACEHOLDER true --EXAMPLE_SECRET_VALUE_PLACEHOLDER true

m365 pp tenant settings set --enableGuestsToMake true

m365 pp tenant settings set --walkMeOptOut true --disableNewsletterSendout true --disableSurveyFeedback true

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## website-get

### Syntax
```
m365 pp website get [options]
```

### Example
```
m365 pp website get --name Demo --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER 

m365 pp website get --id EXAMPLE-GUID-PLACEHOLDER --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER 

m365 pp website get --url https://site-0uaq9.powerappsportals.com --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER 

```

---
