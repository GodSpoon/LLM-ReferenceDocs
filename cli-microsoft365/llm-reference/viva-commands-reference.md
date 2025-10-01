<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - VIVA Commands Reference

*This is an automatically generated condensed reference of all VIVA commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-10-01*

---

## Table of Contents

- [connections-app-create](#connections-app-create)
- [engage-community-add](#engage-community-add)
- [engage-community-get](#engage-community-get)
- [engage-community-list](#engage-community-list)
- [engage-community-remove](#engage-community-remove)
- [engage-community-set](#engage-community-set)
- [engage-community-user-add](#engage-community-user-add)
- [engage-community-user-list](#engage-community-user-list)
- [engage-community-user-remove](#engage-community-user-remove)
- [engage-message-add](#engage-message-add)
- [engage-message-get](#engage-message-get)
- [engage-message-like-set](#engage-message-like-set)
- [engage-message-list](#engage-message-list)
- [engage-message-remove](#engage-message-remove)
- [engage-network-list](#engage-network-list)
- [engage-report-activitycounts](#engage-report-activitycounts)
- [engage-report-activityusercounts](#engage-report-activityusercounts)
- [engage-report-activityuserdetail](#engage-report-activityuserdetail)
- [EXAMPLE_SECRET_VALUE_PLACEHOLDER](#EXAMPLE_SECRET_VALUE_PLACEHOLDER)
- [engage-report-deviceusageusercounts](#engage-report-deviceusageusercounts)
- [engage-report-deviceusageuserdetail](#engage-report-deviceusageuserdetail)
- [engage-report-groupsactivitycounts](#engage-report-groupsactivitycounts)
- [engage-report-groupsactivitydetail](#engage-report-groupsactivitydetail)
- [engage-report-groupsactivitygroupcounts](#engage-report-groupsactivitygroupcounts)
- [engage-role-list](#engage-role-list)
- [engage-role-member-list](#engage-role-member-list)
- [engage-search](#engage-search)
- [engage-user-get](#engage-user-get)
- [engage-user-list](#engage-user-list)

---

## connections-app-create

### Syntax
```
m365 viva connections app create [options]
```

### Example
```
m365 viva connections app create --portalUrl https://contoso.sharepoint.com --name Contoso --description "Contoso company app" --longDescription "Stay on top of what's happening at Contoso" --companyName Contoso --companyWebsiteUrl https://contoso.com --coloredIconPath icon-color.png --outlineIconPath icon-outline.png

```

### Remarks
If the specified portal URL doesn't exist, the command will return `404 - FILE NOT FOUND` error.

The specified portal URL must point to a valid Communication site. To get the list of Communication sites in your tenant, execute: `m365 spo site list --type CommunicationSite`.

The command generates a Microsoft Teams app package. App packages must meet specific requirements to be uploaded to Microsoft Teams. Specified attributes must not exceed their maximum length and the specified color and outline icons must be respectively 192x192px and 32x32px. For the latest list of requirements, see the links in the **More information** section at the end of this page. The generated app package will be written in the current working folder.

After creating the Viva Connections desktop app package, you need to upload it to your Microsoft Teams app catalog. You can do it either manually, or using the CLI by executing `m365 teams app publish --filePath ./contoso.zip`.



---

## engage-community-add

### Syntax
```
m365 viva engage community add [options]
```

### Example
```
m365 viva engage community add --displayName "Software engineers" --description "A community for all software engineers" --privacy public --wait```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reaches general availability.

:::

Creating a community is limited to networks in Native mode only - legacy and external Yammer networks will not be able to use this API for community creation.



---

## engage-community-get

### Syntax
```
m365 viva engage community get [options]
```

### Example
```
m365 viva engage community get --id EXAMPLE_SECRET_VALUE_PLACEHOLDER

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## engage-community-list

### Syntax
```
m365 viva engage community list [options]
```

### Example
```
m365 viva engage community list

```

---

## engage-community-remove

### Syntax
```
m365 viva engage community remove [options]
```

### Example
```
m365 viva engage community remove --id EXAMPLE_SECRET_VALUE_PLACEHOLDER --force

m365 viva engage community remove --displayName 'Software Engineers'

m365 viva engage community remove --entraGroupId 'EXAMPLE-GUID-PLACEHOLDER'

```

### Remarks
:::info

When the Viva Engage community is removed, all the associated Microsoft 365 content, including the M365 group, the document library, OneNote notebook, and Planner plan is deleted.

:::



---

## engage-community-set

### Syntax
```
m365 viva engage community set [options]
```

### Example
```
m365 viva engage community set --id EXAMPLE_SECRET_VALUE_PLACEHOLDER --newDisplayName 'Developers' --description 'Community for all devs' --privacy public

m365 viva engage community set --displayName 'Developrs' --newDisplayName 'Developers'

m365 viva engage community set --entraGroupId 'EXAMPLE-GUID-PLACEHOLDER' --newDisplayName 'Developers'

```

---

## engage-community-user-add

### Syntax
```
m365 viva engage community user add [options]
```

### Example
```
m365 viva engage community user add --communityDisplayName "All company" --ids EXAMPLE-GUID-PLACEHOLDER --role Member```

---

## engage-community-user-list

### Syntax
```
m365 viva engage community user list [options]
```

### Example
```
m365 viva engage community user list --communityId EXAMPLE_SECRET_VALUE_PLACEHOLDER

m365 viva engage community user list --communityDisplayName "All company" --role Admin

m365 viva engage community user list --entraGroupId EXAMPLE-GUID-PLACEHOLDER --role Member

```

---

## engage-community-user-remove

### Syntax
```
m365 viva engage community user remove [options]
```

### Example
```
m365 viva engage community user remove --communityDisplayName "All company" --id EXAMPLE-GUID-PLACEHOLDER

m365 viva engage community user remove --entraGroupId EXAMPLE-GUID-PLACEHOLDER --userName john.doe@contoso.com --force

```

---

## engage-message-add

### Syntax
```
m365 viva engage message add [options]
```

### Example
```
m365 viva engage message add --body "Hello everyone!" --repliedToId 1231231231```

### Remarks
:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::



---

## engage-message-get

### Syntax
```
m365 viva engage message get [options]
```

### Example
```
m365 viva engage message get --id 1239871123

m365 viva engage message get --id 1239871123 --output json

```

### Remarks
:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::



---

## engage-message-like-set

### Syntax
```
m365 viva engage message like set [options]
```

### Example
```
m365 viva engage message like set --messageId 5611239081

m365 viva engage message like set --messageId 5611239081 --enable false

m365 viva engage message like set --messageId 5611239081 --enable false --force

```

### Remarks
:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::



---

## engage-message-list

### Syntax
```
m365 viva engage message list [options]
```

### Example
```
m365 viva engage message list

m365 viva engage message list --olderThanId 5611239081

m365 viva engage message list --threaded

m365 viva engage message list --limit 10

m365 viva engage message list --groupId 312891231 --limit 10

m365 viva engage message list --threadId 5611239081 --limit 10

m365 viva engage message list --feedType Sent --limit 20

```

### Remarks
:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::

Feed types



---

## engage-message-remove

### Syntax
```
m365 viva engage message remove [options]
```

### Example
```
m365 viva engage message remove --id 1239871123

m365 viva engage message remove --id 1239871123 --force

```

### Remarks
:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::

To remove a message, you must either:



---

## engage-network-list

### Syntax
```
m365 viva engage network list [options]
```

### Example
```
m365 viva engage network list

m365 viva engage network list --withSuspended

```

### Remarks
:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::



---

## engage-report-activitycounts

### Syntax
```
m365 viva engage report activitycounts [options]
```

### Example
```
m365 viva engage report activitycounts --period D7

m365 viva engage report activitycounts --period D7 --output text > "activitycounts.txt"

m365 viva engage report activitycounts --period D7 --output json > "activitycounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## engage-report-activityusercounts

### Syntax
```
m365 viva engage report activityusercounts [options]
```

### Example
```
m365 viva engage report activityusercounts --period D7

m365 viva engage report activityusercounts --period D7 --output text > "activityusercounts.txt"

m365 viva engage report activityusercounts --period D7 --output json > "activityusercounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## engage-report-activityuserdetail

### Syntax
```
m365 viva engage report activityuserdetail [options]
```

### Example
```
m365 viva engage report activityuserdetail --period D7

m365 viva engage report activityuserdetail --date 2019-05-01

m365 viva engage report activityuserdetail --period D7 --output text > "activityuserdetail.txt"

m365 viva engage report activityuserdetail --period D7 --output json > "activityuserdetail.json"

```

### Remarks
As this report is only available for the past 28 days, date parameter value should be a date from that range.

:::info

This command supports only csv and json output.

:::



---

## EXAMPLE_SECRET_VALUE_PLACEHOLDER

### Syntax
```
m365 viva engage report deviceusagedistributionusercounts [options]
```

### Example
```
m365 viva engage report deviceusagedistributionusercounts --period D7

m365 viva engage report deviceusagedistributionusercounts --period D7 --output text > "deviceusagedistributionusercounts.txt"

m365 viva engage report deviceusagedistributionusercounts --period D7 --output json > "deviceusagedistributionusercounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## engage-report-deviceusageusercounts

### Syntax
```
m365 viva engage report deviceusageusercounts [options]
```

### Example
```
m365 viva engage report deviceusageusercounts --period D7

m365 viva engage report deviceusageusercounts --period D7 --output text > "deviceusageusercounts.txt"

m365 viva engage report deviceusageusercounts --period D7 --output json > "deviceusageusercounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## engage-report-deviceusageuserdetail

### Syntax
```
m365 viva engage report deviceusageuserdetail [options]
```

### Example
```
m365 viva engage report deviceusageuserdetail --period D7

m365 viva engage report deviceusageuserdetail --date 2019-07-01

m365 viva engage report deviceusageuserdetail --period D7 --output text > "deviceusageuserdetail.txt"

m365 viva engage report deviceusageuserdetail --period D7 --output json > "deviceusageuserdetail.json"

```

### Remarks
As this report is only available for the past 28 days, date parameter value should be a date from that range.

:::info

This command supports only csv and json output.

:::



---

## engage-report-groupsactivitycounts

### Syntax
```
m365 viva engage report groupsactivitycounts [options]
```

### Example
```
m365 viva engage report groupsactivitycounts --period D7

m365 viva engage report groupsactivitycounts --period D7 --output text > "groupsactivitycounts.txt"

m365 viva engage report groupsactivitycounts --period D7 --output json > "groupsactivitycounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## engage-report-groupsactivitydetail

### Syntax
```
m365 viva engage report groupsactivitydetail [options]
```

### Example
```
m365 viva engage report groupsactivitydetail --period D7

m365 viva engage report groupsactivitydetail --date 2019-07-01

m365 viva engage report groupsactivitydetail --period D7 --output text > "groupsactivitydetail.txt"

m365 viva engage report groupsactivitydetail --period D7 --output json > "groupsactivitydetail.json"

```

### Remarks
As this report is only available for the past 28 days, date parameter value should be a date from that range.

:::info

This command supports only csv and json output.

:::



---

## engage-report-groupsactivitygroupcounts

### Syntax
```
m365 viva engage report groupsactivitygroupcounts [options]
```

### Example
```
m365 viva engage report groupsactivitygroupcounts --period D7

m365 viva engage report groupsactivitygroupcounts --period D7 --output text > "groupsactivitygroupcounts.txt"

m365 viva engage report groupsactivitygroupcounts --period D7 --output json > "groupsactivitygroupcounts.json"

```

### Remarks
:::info

This command supports only csv and json output.

:::



---

## engage-role-list

### Syntax
```
m365 viva engage role list [options]
```

### Example
```
m365 viva engage role list

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reaches general availability.

:::



---

## engage-role-member-list

### Syntax
```
m365 viva engage role member list [options]
```

### Example
```
m365 viva engage role member list --roleId EXAMPLE-GUID-PLACEHOLDER

m365 viva engage role member list --roleName 'Verified Admin'

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reaches general availability.

:::



---

## engage-search

### Syntax
```
m365 viva engage search [options]
```

### Example
```
m365 viva engage search --queryText "community"

m365 viva engage search --queryText "community" --show "groups"

m365 viva engage search --queryText "community" --show "topics"

m365 viva engage search --queryText "nuborocks.onmicrosoft.com" --show "users" --limit 50

m365 viva engage search --queryText "community" --output json

m365 viva engage search --queryText "community" --output json --limit 50

```

### Remarks
:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::

Using the `--show` option in JSON output is not supported. To filter JSON results, use either a JMESPath query or filter the data yourself after retrieving them.



---

## engage-user-get

### Syntax
```
m365 viva engage user get [options]
```

### Example
```
m365 viva engage user get

m365 viva engage user get --id 1496550697

m365 viva engage user get --email john.smith@contoso.com

m365 viva engage user get --email john.smith@contoso.com --output json

```

### Remarks
:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::

All operations return a single user object. Operations executed with the `email` parameter return an array of user objects.



---

## engage-user-list

### Syntax
```
m365 viva engage user list [options]
```

### Example
```
m365 viva engage user list

m365 viva engage user list --letter a

m365 viva engage user list --reverse

m365 user list --groupId 5785177 --limit 10

```

### Remarks
:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::



---
