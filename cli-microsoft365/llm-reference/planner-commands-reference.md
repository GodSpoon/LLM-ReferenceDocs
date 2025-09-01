<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - PLANNER Commands Reference

*This is an automatically generated condensed reference of all PLANNER commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-09-01*

---

## Table of Contents

- [bucket-add](#bucket-add)
- [bucket-get](#bucket-get)
- [bucket-list](#bucket-list)
- [bucket-remove](#bucket-remove)
- [bucket-set](#bucket-set)
- [plan-add](#plan-add)
- [plan-get](#plan-get)
- [plan-list](#plan-list)
- [plan-remove](#plan-remove)
- [plan-set](#plan-set)
- [roster-add](#roster-add)
- [roster-get](#roster-get)
- [roster-member-add](#roster-member-add)
- [roster-member-get](#roster-member-get)
- [roster-member-list](#roster-member-list)
- [roster-member-remove](#roster-member-remove)
- [roster-plan-list](#roster-plan-list)
- [roster-remove](#roster-remove)
- [task-add](#task-add)
- [task-checklistitem-add](#task-checklistitem-add)
- [task-checklistitem-list](#task-checklistitem-list)
- [task-checklistitem-remove](#task-checklistitem-remove)
- [task-get](#task-get)
- [task-list](#task-list)
- [task-reference-add](#task-reference-add)
- [task-reference-list](#task-reference-list)
- [task-reference-remove](#task-reference-remove)
- [task-remove](#task-remove)
- [task-set](#task-set)
- [tenant-settings-list](#tenant-settings-list)
- [tenant-settings-set](#tenant-settings-set)

---

## bucket-add

### Syntax
```
m365 planner bucket add [options]
```

### Example
```
m365 planner bucket add --name "My Planner Bucket" --planId "xqQg5FS2LkCp935s-FIFm2QAFkHM" --orderHint " !"

m365 planner bucket add --name "My Planner Bucket" --planTitle "My Planner Plan" --ownerGroupName "My Planner Group"

m365 planner bucket add --name "My Planner Bucket" --rosterId "RuY-PSpdw02drevnYDTCJpgAEfoI"

```

### Remarks
:::warning

When using `rosterId`, the command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## bucket-get

### Syntax
```
m365 planner bucket get [options]
```

### Example
```
m365 planner bucket get --id "5h1uuYFk4kKQ0hfoTUkRLpgALtYi"

m365 planner bucket get --name "Planner Bucket A" --planId "xqQg5FS2LkCp935s-FIFm2QAFkHM"

m365 planner bucket get --name "Planner Bucket A" --planTitle "My Plan" --ownerGroupName "My Group"

m365 planner bucket get --name "Planner Bucket A" --planTitle "My Plan" --ownerGroupId "EXAMPLE-GUID-PLACEHOLDER"

m365 planner bucket get --name "Planner Bucket A" --rosterId "RuY-PSpdw02drevnYDTCJpgAEfoI"

```

### Remarks
:::warning

When using `rosterId`, the command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## bucket-list

### Syntax
```
m365 planner bucket list [options]
```

### Example
```
m365 planner bucket list --planId "xqQg5FS2LkCp935s-FIFm2QAFkHM"

m365 planner bucket list --planTitle "My Plan" --ownerGroupName "My Group"

m365 planner bucket list --planTitle "My Plan" --rosterId "RuY-PSpdw02drevnYDTCJpgAEfoI"

```

### Remarks
:::warning

When using `rosterId`, the command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## bucket-remove

### Syntax
```
m365 planner bucket remove [options]
```

### Example
```
m365 planner bucket remove --id "vncYUXCRBke28qMLB-d4xJcACtNz"

m365 planner bucket remove --id "vncYUXCRBke28qMLB-d4xJcACtNz" --force

m365 planner bucket remove --name "My Bucket" --planId "oUHpnKBFekqfGE_PS6GGUZcAFY7b"

m365 planner bucket remove --name "My Bucket" --planTitle "My Plan" --ownerGroupName "My Group"

m365 planner bucket remove --name "My Bucket" --rosterId "RuY-PSpdw02drevnYDTCJpgAEfoI"

```

### Remarks
:::warning

When using `rosterId`, the command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## bucket-set

### Syntax
```
m365 planner bucket set [options]
```

### Example
```
m365 planner bucket set --id "vncYUXCRBke28qMLB-d4xJcACtNz" --newName "New bucket name"

m365 planner bucket set --name "My Bucket" --planTitle "My Plan" --ownerGroupName "My Group" --newName "New bucket name"

m365 planner bucket set --name "My Bucket" --planTitle "My Plan" --ownerGroupId EXAMPLE-GUID-PLACEHOLDER --newName "New bucket name"

m365 planner bucket set --name "My Bucket" --rosterId "RuY-PSpdw02drevnYDTCJpgAEfoI" --newName "New bucket name"

```

### Remarks
:::warning

When using `rosterId`, the command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## plan-add

### Syntax
```
m365 planner plan add [options]
```

### Example
```
m365 planner plan add --title 'My Planner Plan' --ownerGroupId 'EXAMPLE-GUID-PLACEHOLDER'

m365 planner plan add --title 'My Planner Plan' --ownerGroupName 'My Planner Group'

m365 planner plan add --title 'My Planner Plan' --rosterId 'EXAMPLE-GUID-PLACEHOLDER'

m365 planner plan add --title 'My Planner Plan' --ownerGroupName 'My Planner Group' --shareWithUserNames 'Allan.Carroll@contoso.com,Ida.Stevens@contoso.com'

```

---

## plan-get

### Syntax
```
m365 planner plan get [options]
```

### Example
```
m365 planner plan get --id "gndWOTSK60GfPQfiDDj43JgACDCb"

m365 planner plan get --title "MyPlan" --ownerGroupId "EXAMPLE-GUID-PLACEHOLDER"

m365 planner plan get --title "MyPlan" --ownerGroupName "My Planner Group"

m365 planner plan get --rosterId "FeMZFDoK8k2oWmuGE-XFHZcAEwtn"

```

### Remarks
:::warning

When using `rosterId`, the command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## plan-list

### Syntax
```
m365 planner plan list [options]
```

### Example
```
m365 planner plan list --ownerGroupId "EXAMPLE-GUID-PLACEHOLDER"

m365 planner plan list --ownerGroupName "My Planner Group"

m365 planner plan list --rosterId "FeMZFDoK8k2oWmuGE-XFHZcAEwtn"

```

### Remarks
:::warning

When using rosterId, the command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## plan-remove

### Syntax
```
m365 planner plan remove [options]
```

### Example
```
m365 planner plan remove --id gndWOTSK60GfPQfiDDj43JgACDCb

m365 planner plan remove --title "My Plan" --ownerGroupId EXAMPLE-GUID-PLACEHOLDER

m365 planner plan remove --title "My Plan" --ownerGroupName "My Planner Group" --force

```

### Remarks
If you wish to delete a Planner plan contained within a Planner Roster, you'll have to remove the roster using [planner roster remove](../roster/roster-remove.mdx).



---

## plan-set

### Syntax
```
m365 planner plan set [options]
```

### Example
```
m365 planner plan set --id 'gndWOTSK60GfPQfiDDj43JgACDCb' --newTitle 'New Title'

m365 planner plan set --title 'Plan Title' --ownerGroupName 'My Group' --shareWithUserNames 'user1@contoso.com,user2@contoso.com'

m365 planner plan set --id 'gndWOTSK60GfPQfiDDj43JgACDCb' --category21 'ToDo' --category25 'Urgent'

```

### Remarks
This command allows using unknown options. 

:::warning

When using `rosterId`, the command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## roster-add

### Syntax
```
m365 planner roster add [options]
```

### Example
```
m365 planner roster add

```

### Remarks
:::warning

The Roster will be automatically deleted when it doesn't contain a plan 24 hours after its creation. Membership information will be completely erased within 30 days of this deletion.

:::

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

:::info

To be able to create a new Roster, the Planner Roster creation tenant setting should be enabled. Use the [planner tenant settings list](../tenant/tenant-settings-list.mdx) command to check if this setting is enabled for your tenant.

:::



---

## roster-get

### Syntax
```
m365 planner roster get [options]
```

### Example
```
m365 planner roster get --id EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## roster-member-add

### Syntax
```
m365 planner roster member add [options]
```

### Example
```
m365 planner roster member add --rosterId EXAMPLE-GUID-PLACEHOLDER --userName john.doe@contoso.com

m365 planner roster member add --rosterId EXAMPLE-GUID-PLACEHOLDER --userId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## roster-member-get

### Syntax
```
m365 planner roster member get [options]
```

### Example
```
m365 planner roster member get --rosterId EXAMPLE-GUID-PLACEHOLDER --userName john.doe@contoso.com

m365 planner roster member get --rosterId EXAMPLE-GUID-PLACEHOLDER --userId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## roster-member-list

### Syntax
```
m365 planner roster member list [options]
```

### Example
```
m365 planner roster member list --rosterId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## roster-member-remove

### Syntax
```
m365 planner roster member remove [options]
```

### Example
```
m365 planner roster member remove --rosterId EXAMPLE-GUID-PLACEHOLDER --userId EXAMPLE-GUID-PLACEHOLDER

m365 planner roster member remove --rosterId EXAMPLE-GUID-PLACEHOLDER --userName john.doe@contoso.com

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

:::warning

The Planner Roster will be deleted when it doesn't have any users remaining in the membership list because the last user removed themselves. Roster, its plan and all contained tasks will be deleted within 30 days of this operation. We will show an extra prompt when this happens. This prompt is also suppressed when specifying `-f, --force`.

:::



---

## roster-plan-list

### Syntax
```
m365 planner roster plan list [options]
```

### Example
```
m365 planner roster plan list

m365 planner roster plan list --userName john.doe@contoso.com

m365 planner roster plan list --userId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## roster-remove

### Syntax
```
m365 planner roster remove [options]
```

### Example
```
m365 planner roster remove --id EXAMPLE-GUID-PLACEHOLDER

m365 planner roster remove --id EXAMPLE-GUID-PLACEHOLDER --force

```

### Remarks
:::warning

Deleting a Planner Roster will also delete the plan within the Roster.

:::

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## task-add

### Syntax
```
m365 planner task add [options]
```

### Example
```
m365 planner task add --title "My Planner Task" --planId "8QZEH7b3wkSbGQobscsM5gADCBa" --bucketId "IK8tuFTwQEa5vTonM7ZMRZgAKdna"```

### Remarks
When you specify the value for `percentComplete`, consider the following:

When you specify an integer value for `priority`, consider the following:

When using `description` with a multiple lines value, use the new line character of the shell you are using to indicate line breaks. For PowerShell this is `` `n ``. For Zsh or Bash use `
` with a `$` in front. E.g. `$"Line 1
Line 2"`.

:::warning

When using `rosterId`, the command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## task-checklistitem-add

### Syntax
```
m365 planner task checklistitem add [options]
```

### Example
```
m365 planner task checklistitem add --taskId 2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2 --title "My checklist item"

m365 planner task checklistitem add --taskId 2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2 --title "My checklist item" --isChecked

```

---

## task-checklistitem-list

### Syntax
```
m365 planner task checklistitem list [options]
```

### Example
```
m365 planner task checklistitem list --taskId 'vzCcZoOv-U27PwydxHB8opcADJo-'

```

---

## task-checklistitem-remove

### Syntax
```
m365 planner task checklistitem remove [options]
```

### Example
```
m365 planner task checklistitem remove --id "40012" --taskId "2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2" 

m365 planner task checklistitem remove --id "40012" --taskId "2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2" --force

```

---

## task-get

### Syntax
```
m365 planner task get [options]
```

### Example
```
m365 planner task get --id "vzCcZoOv-U27PwydxHB8opcADJo-"

m365 planner task get --title "My Planner Task" --bucketName "My Planner Bucket" --planTitle "My Planner Plan" --ownerGroupName "My Planner Group"

m365 planner task get --title "New Task" --bucketName "To do" --rosterId "EXAMPLE-GUID-PLACEHOLDER"

```

### Remarks
:::warning

When using `rosterId`, the command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## task-list

### Syntax
```
m365 planner task list [options]
```

### Example
```
m365 planner task list```

### Remarks
:::warning

This command uses API that is currently in preview to enrich the results with the `priority` field. Keep in mind that this preview API is subject to change once the API reached general availability.

:::

:::warning

When using `rosterId`, the command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## task-reference-add

### Syntax
```
m365 planner task reference add [options]
```

### Example
```
m365 planner task reference add --taskId "2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2" --url "https://www.microsoft.com"

m365 planner task reference add --taskId "2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2" --url "https://www.microsoft.com" --alias "Parker"

m365 planner task reference add --taskId "2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2" --url "https://www.microsoft.com" --type "Excel"

```

---

## task-reference-list

### Syntax
```
m365 planner task reference list [options]
```

### Example
```
m365 planner task reference list --taskId uBk5fK_MHkeyuPYlCo4OFpcAM

```

---

## task-reference-remove

### Syntax
```
m365 planner task reference remove [options]
```

### Example
```
m365 planner task reference remove --url "https://www.microsoft.com" --taskId "2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2" 

m365 planner task reference remove --alias "Parker" --taskId "2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2"

```

---

## task-remove

### Syntax
```
m365 planner task remove [options]
```

### Example
```
m365 planner task remove --id "2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2"```

### Remarks
:::warning

When using `rosterId`, the command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## task-set

### Syntax
```
m365 planner task set [options]
```

### Example
```
m365 planner task set --id "Z-RLQGfppU6H3663DBzfs5gAMD3o" --title "My Planner Task"```

### Remarks
When you specify the value for `percentComplete`, consider the following:

When you specify an integer value for `priority`, consider the following:

You can add up to 6 categories to the task. An example to add _category1_ and _category3_ would be `category1,category3`.

When using `description` with a multiple lines value, use the new line character of the shell you are using to indicate line breaks. For PowerShell this is `` `n ``. For Zsh or Bash use `
` with a `$` in front. E.g. `$"Line 1
Line 2"`.

:::warning

When using `rosterId`, the command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::



---

## tenant-settings-list

### Syntax
```
m365 planner tenant settings list [options]
```

### Example
```
m365 planner tenant settings list

```

### Remarks
After executing the command `planner tenant settings set`, it can take some time for all changes to propagate across the tenant. Because of this, executing this command right away can return some unexpected results.



---

## tenant-settings-set

### Syntax
```
m365 planner tenant settings set [options]
```

### Example
```
m365 planner tenant settings set --isPlannerAllowed false

m365 planner tenant settings set --allowCalendarSharing false --allowPlannerMobilePushNotifications false

m365 planner tenant settings set --isPlannerAllowed true --allowRosterCreation false

```

---
