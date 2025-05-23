-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# purview retentionlabel add

Create a retention label

## Usage

```sh
m365 purview retentionlabel add [options]
```

## Options

```md definition-list
`-n, --displayName <displayName>`
: The display name of the label.

`--behaviorDuringRetentionPeriod <behaviorDuringRetentionPeriod>`
: Specifies how the behavior of a document with this label should be during the retention period. Allowed values: `doNotRetain`, `retain`, `retainAsRecord`, `retainAsRegulatoryRecord`.

`--actionAfterRetentionPeriod <actionAfterRetentionPeriod>`
: Specifies the action to take on a document with this label applied after the retention period. Allowed values: `none`, `delete`, `startDispositionReview`.

`--retentionDuration <retentionDuration>`
: The number of days to retain the content.

`-t, --retentionTrigger [retentionTrigger]`
: Specifies whether the retention duration is calculated from the content creation date, labeled date, or last modification date. Allowed values: `dateLabeled`, `dateCreated`, `dateModified`, `dateOfEvent`. Defaults to `dateLabeled`.

`--defaultRecordBehavior [defaultRecordBehavior]`
: Specifies the locked or unlocked state of a record label when it is created. Allowed values: `startLocked`, `startUnlocked`, Defaults to `startLocked`.

`--descriptionForUsers [descriptionForUsers]`
: The label information for the user.

`--descriptionForAdmins [descriptionForAdmins]`
: The label information for the admin.

`--labelToBeApplied [labelToBeApplied]`
: Specifies the replacement label to be applied automatically after the retention period of the current label ends.

`--eventTypeId [eventTypeId]`
: The Id of the event type that is used to in case of an event-based label. Specify when using retentionTrigger with the value `dateOfEvent`. Specify either `eventTypeId` or `eventTypeName`, but not both.

`--eventTypeName [eventTypeName]`
:	The display name of the event type that is used to in case of an event-based label. Specify when using retentionTrigger with the value `dateOfEvent`. Specify either `eventTypeId` or `eventTypeName`, but not both.
```

<Global />

## Remarks

:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::

## Examples

Create a retention label that retains documents and deletes them after one year.

```sh
m365 purview retentionlabel add --displayName 'some label' --behaviorDuringRetentionPeriod retain --actionAfterRetentionPeriod delete --retentionDuration 365
```

Create a retention label that retains documents as records and does not take any action one year after the last modification date.

```sh
m365 purview retentionlabel add --displayName 'some label' --behaviorDuringRetentionPeriod retainAsRecord --actionAfterRetentionPeriod none --retentionDuration 365 --retentionTrigger dateModified
```

Create an event-based retention label that retains documents as records and deletes them one year after a _Contract Expiry_ event date.

```sh
m365 purview retentionlabel add --displayName 'some label' --behaviorDuringRetentionPeriod retain --actionAfterRetentionPeriod delete --retentionDuration 365 --retentionTrigger dateOfEvent --eventTypeName "Contract Expiry"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "displayName": "some label",
    "descriptionForAdmins": "Description for admins",
    "descriptionForUsers": "Description for users",
    "isInUse": false,
    "retentionTrigger": "dateLabeled",
    "behaviorDuringRetentionPeriod": "retain",
    "actionAfterRetentionPeriod": "delete",
    "createdDateTime": "2022-12-21T09:28:37Z",
    "lastModifiedDateTime": "2022-12-21T09:28:37Z",
    "labelToBeApplied": "another label",
    "defaultRecordBehavior": "startLocked",
    "id": "f7e05955-210b-4a8e-a5de-3c64cfa6d9be",
    "retentionDuration": {
      "days": 365
    },
    "createdBy": {
      "user": {
        "id": null,
        "displayName": "John Doe"
      }
    },
    "lastModifiedBy": {
      "user": {
        "id": null,
        "displayName": "John Doe"
      }
    },
    "dispositionReviewStages": []
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  actionAfterRetentionPeriod   : delete
  behaviorDuringRetentionPeriod: retain
  createdBy                    : {"user":{"id":null,"displayName":"John Doe"}}
  createdDateTime              : 2022-12-21T09:32:38Z
  defaultRecordBehavior        : startLocked
  descriptionForAdmins         : Description for admins
  descriptionForUsers          : Description for users
  displayName                  : some label
  dispositionReviewStages      : []
  id                           : 3b388f3c-541b-4696-ad0e-83f960695d89
  isInUse                      : false
  labelToBeApplied             : another label
  lastModifiedBy               : {"user":{"id":null,"displayName":"John Doe"}}
  lastModifiedDateTime         : 2022-12-21T09:32:38Z
  retentionDuration            : {"days":365}
  retentionTrigger             : dateLabeled
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  displayName,descriptionForAdmins,descriptionForUsers,isInUse,retentionTrigger,behaviorDuringRetentionPeriod,actionAfterRetentionPeriod,createdDateTime,lastModifiedDateTime,labelToBeApplied,defaultRecordBehavior,id,retentionDuration,createdBy,lastModifiedBy,dispositionReviewStages
  some label,Description for admins,Description for users,,dateLabeled,retain,delete,2022-12-21T09:33:32Z,2022-12-21T09:33:32Z,another label,startLocked,cfc8b132-7aef-45f4-9fcf-3c199090ba2a,"{""days"":365}","{""user"":{""id"":null,""displayName"":""John Doe""}}","{""user"":{""id"":null,""displayName"":""John Doe""}}",[]
  ```

  </TabItem>
</Tabs>

## More information

- Create retentionLabel: [https://learn.microsoft.com/graph/api/security-retentionlabel-post?view=graph-rest-beta&tabs=http](https://learn.microsoft.com/graph/api/security-retentionlabel-post?view=graph-rest-beta&tabs=http)
