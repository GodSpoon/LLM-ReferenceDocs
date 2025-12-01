<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - TENANT Commands Reference

*This is an automatically generated condensed reference of all TENANT commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-12-01*

---

## Table of Contents

- [id-get](#id-get)
- [info-get](#info-get)
- [people-profilecardproperty-add](#people-profilecardproperty-add)
- [people-profilecardproperty-get](#people-profilecardproperty-get)
- [people-profilecardproperty-list](#people-profilecardproperty-list)
- [people-profilecardproperty-remove](#people-profilecardproperty-remove)
- [people-profilecardproperty-set](#people-profilecardproperty-set)
- [people-pronouns-get](#people-pronouns-get)
- [people-pronouns-set](#people-pronouns-set)
- [report-activeusercounts](#report-activeusercounts)
- [report-activeuserdetail](#report-activeuserdetail)
- [report-office365activationcounts](#report-office365activationcounts)
- [report-office365activationsusercounts](#report-office365activationsusercounts)
- [report-office365activationsuserdetail](#report-office365activationsuserdetail)
- [report-servicesusercounts](#report-servicesusercounts)
- [report-settings-get](#report-settings-get)
- [report-settings-set](#report-settings-set)
- [security-alerts-list](#security-alerts-list)
- [serviceannouncement-health-get](#serviceannouncement-health-get)
- [serviceannouncement-healthissue-get](#serviceannouncement-healthissue-get)
- [serviceannouncement-healthissue-list](#serviceannouncement-healthissue-list)
- [serviceannouncement-health-list](#serviceannouncement-health-list)
- [serviceannouncement-message-get](#serviceannouncement-message-get)
- [serviceannouncement-message-list](#serviceannouncement-message-list)

---

## id-get

### Syntax
```
m365 tenant id get [options]
```

### Example
```
m365 tenant id get --domainName contoso.com

m365 tenant id get

```

### Remarks
If no domain name is specified, the command will return the tenant ID of the tenant to which you are currently logged in.



---

## info-get

### Syntax
```
m365 tenant info get [options]
```

### Example
```
m365 tenant info get

m365 tenant info get --domainName contoso.com

m365 tenant info get --tenantId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
If no domain name or tenantId is specified, the command will return the tenant information of the currently signed in user.



---

## people-profilecardproperty-add

### Syntax
```
m365 tenant people profilecardproperty add [options]
```

### Example
```
m365 tenant people profilecardproperty add --name UserPrincipalName

m365 tenant people profilecardproperty add --name customAttribute1 --displayName 'Cost Center'

m365 tenant people profilecardproperty add --name customAttribute1 --displayName 'Cost Center' --displayName-nl-NL 'Kostencentrum'

```

### Remarks
:::info

To use this command you must be either **Tenant Administrator** or **Global Administrator**.

:::

:::info

You can specify localized values for the `displayName` as well. These can be entered by suffixing the displayName option with a language code: `--displayName-nl-NL "Kostencentrum"`, `--displayName-de "Kostenstelle"`.

:::

:::warning

When adding an attribute to a profile card, it takes up to 24 hours for the addition to be displayed.

:::



---

## people-profilecardproperty-get

### Syntax
```
m365 tenant people profilecardproperty get [options]
```

### Example
```
m365 tenant people profilecardproperty get --name customAttribute1

```

### Remarks
:::info

To use this command you must be either **Tenant Administrator** or **Global Administrator**.

:::



---

## people-profilecardproperty-list

### Syntax
```
m365 tenant people profilecardproperty list [options]
```

### Example
```
m365 tenant people profilecardproperty list

```

### Remarks
:::info

To use this command you must be either **Tenant Administrator** or **Global Administrator**.

:::



---

## people-profilecardproperty-remove

### Syntax
```
m365 tenant people profilecardproperty remove [options]
```

### Example
```
m365 tenant people profilecardproperty remove --name UserPrincipalName

m365 tenant people profilecardproperty remove --name UserPrincipalName --force

```

### Remarks
:::info

To use this command you must be either **Tenant Administrator** or **Global Administrator**.

:::

:::warning

When removing an attribute from a profile card, it takes up to 24 hours for the change to be displayed.

:::



---

## people-profilecardproperty-set

### Syntax
```
m365 tenant people profilecardproperty set [options]
```

### Example
```
m365 tenant people profilecardproperty set --name customAttribute1 --displayName "Cost Center"

m365 tenant people profilecardproperty set --name customAttribute1 --displayName "Cost Center" --displayName-nl-NL "Kostencentrum" --displayName-de "Kostenstelle"

```

### Remarks
:::info

To use this command you must be either **Tenant Administrator** or **Global Administrator**.

:::

:::info

You can specify localized values for the `displayName` as well. These can be entered by suffixing the displayName option with a language code: `--displayName-nl-NL "Kostencentrum"`, `--displayName-de "Kostenstelle"`.

:::

:::warning

When updating an attribute to a profile card, it takes up to 24 hours for the addition to be displayed.

:::



---

## people-pronouns-get

### Syntax
```
m365 tenant people pronouns get [options]
```

### Example
```
m365 tenant people pronouns get

```

---

## people-pronouns-set

### Syntax
```
m365 tenant people pronouns set [options]
```

### Example
```
m365 tenant people pronouns set --enabled true

m365 tenant people pronouns set --enabled false

```

---

## report-activeusercounts

### Syntax
```
m365 tenant report activeusercounts [options]
```

### Example
```
m365 tenant report activeusercounts --period D7

m365 tenant report activeusercounts --period D7 --output text > "activeusercounts.txt"

m365 tenant report activeusercounts --period D7 --output json > "activeusercounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-activeuserdetail

### Syntax
```
m365 tenant report activeuserdetail [options]
```

### Example
```
m365 tenant report activeuserdetail --period D7

m365 tenant report activeuserdetail --date 2019-05-01

m365 tenant report activeuserdetail --period D7 --output text > "activeuserdetail.txt"

m365 tenant report activeuserdetail --period D7 --output json > "activeuserdetail.json"

```

### Remarks
As this report is only available for the past 28 days, date parameter value should be a date from that range.

:::info

This command supports only csv and json output.

:::



---

## report-office365activationcounts

### Syntax
```
m365 tenant report office365activationcounts [options]
```

### Example
```
m365 tenant report office365activationcounts

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-office365activationsusercounts

### Syntax
```
m365 tenant report office365activationsusercounts [options]
```

### Example
```
m365 tenant report office365activationsusercounts

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-office365activationsuserdetail

### Syntax
```
m365 tenant report office365activationsuserdetail [options]
```

### Example
```
m365 tenant report office365activationsuserdetail

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-servicesusercounts

### Syntax
```
m365 tenant report servicesusercounts [options]
```

### Example
```
m365 tenant report servicesusercounts --period D7

m365 tenant report servicesusercounts --period D7 --output text > "servicesusercounts.txt"

m365 tenant report servicesusercounts --period D7 --output json > "servicesusercounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## report-settings-get

### Syntax
```
m365 tenant report settings get [options]
```

### Example
```
m365 tenant report settings get

```

---

## report-settings-set

### Syntax
```
m365 tenant report settings set [options]
```

### Example
```
m365 tenant report settings set --displayConcealedNames true

```

---

## security-alerts-list

### Syntax
```
m365 tenant security alerts list [options]
```

### Example
```
m365 tenant security alerts list

m365 tenant security alerts list --vendor "Azure Sentinel"

```

---

## serviceannouncement-health-get

### Syntax
```
m365 tenant serviceannouncement health get [options]
```

### Example
```
m365 tenant serviceannouncement health get --serviceName "Exchange Online"

m365 tenant serviceannouncement health get --serviceName "Exchange Online" --issues

```

---

## serviceannouncement-healthissue-get

### Syntax
```
m365 tenant serviceannouncement healthissue get [options]
```

### Example
```
m365 tenant serviceannouncement healthissue get --id MO226784

```

---

## serviceannouncement-healthissue-list

### Syntax
```
m365 tenant serviceannouncement healthissue list [options]
```

### Example
```
m365 tenant serviceannouncement healthissue list

m365 tenant serviceannouncement healthissue list --service "Microsoft Forms"

```

---

## serviceannouncement-health-list

### Syntax
```
m365 tenant serviceannouncement health list [options]
```

### Example
```
m365 tenant serviceannouncement health list

m365 tenant serviceannouncement health list --issues

```

---

## serviceannouncement-message-get

### Syntax
```
m365 tenant serviceannouncement message get [options]
```

### Example
```
m365 tenant serviceannouncement message get --id MC001337

```

---

## serviceannouncement-message-list

### Syntax
```
m365 tenant serviceannouncement message list [options]
```

### Example
```
m365 tenant serviceannouncement message list

m365 tenant serviceannouncement message list --service "Microsoft Teams"

```

---
