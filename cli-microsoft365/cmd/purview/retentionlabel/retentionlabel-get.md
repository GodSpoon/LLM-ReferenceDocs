-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# purview retentionlabel get

Get a retention label

## Usage

```sh
m365 purview retentionlabel get [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The Id of the retention label.
```

<Global />

## Remarks

:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::

## Examples

Get a retention label

```sh
m365 purview retentionlabel get --id c37d695e-d581-4ae9-82a0-9364eba4291e
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "displayName": "TEST LABEL",
    "descriptionForAdmins": "",
    "descriptionForUsers": "",
    "isInUse": false,
    "retentionTrigger": "dateCreated",
    "behaviorDuringRetentionPeriod": "retain",
    "actionAfterRetentionPeriod": "delete",
    "createdDateTime": "2022-12-12T15:14:53Z",
    "lastModifiedDateTime": "2022-12-12T15:43:06Z",
    "labelToBeApplied": "",
    "defaultRecordBehavior": "startLocked",
    "id": "5c8af2e2-b489-4fa0-9c16-180180245ac8",
    "retentionDuration": {
      "days": 100
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
  createdDateTime              : 2022-12-12T15:14:53Z
  defaultRecordBehavior        : startLocked
  descriptionForAdmins         :
  descriptionForUsers          :
  displayName                  : TEST LABEL
  dispositionReviewStages      : []
  id                           : 5c8af2e2-b489-4fa0-9c16-180180245ac8
  isInUse                      : false
  labelToBeApplied             :
  lastModifiedBy               : {"user":{"id":null,"displayName":"John Doe"}}
  lastModifiedDateTime         : 2022-12-12T15:43:06Z
  retentionDuration            : {"days":100}
  retentionTrigger             : dateCreated
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  displayName,descriptionForAdmins,descriptionForUsers,isInUse,retentionTrigger,behaviorDuringRetentionPeriod,actionAfterRetentionPeriod,createdDateTime,lastModifiedDateTime,labelToBeApplied,defaultRecordBehavior,id,retentionDuration,createdBy,lastModifiedBy,dispositionReviewStages
  TEST LABEL,,,,dateCreated,retain,delete,2022-12-12T15:14:53Z,2022-12-12T15:43:06Z,,startLocked,5c8af2e2-b489-4fa0-9c16-180180245ac8,"{""days"":100}","{""user"":{""id"":null,""displayName"":""John Doe""}}","{""user"":{""id"":null,""displayName"":""John Doe""}}",[]
  ```

  </TabItem>
</Tabs>
