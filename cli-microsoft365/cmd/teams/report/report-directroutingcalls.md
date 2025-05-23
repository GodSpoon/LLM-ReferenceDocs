-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams report directroutingcalls

Get details about direct routing calls made within a given time period

## Usage

```sh
m365 teams report directroutingcalls [options]
```

## Options

```md definition-list
`--fromDateTime <fromDateTime>`
: The start of time range to query. UTC, inclusive.

`--toDateTime [toDateTime]`
: The end time range to query. UTC, inclusive. Defaults to today if omitted.
```

<Global />

## Remarks

This command only works with app-only permissions. You will need to create your own Microsoft Entra app with `CallRecords.Read.All` permission assigned. Instructions on how to create your own Microsoft Entra app can be found at [Using your own Microsoft Entra identity](../../../user-guide/using-own-identity.mdx)

The difference between `fromDateTime` and `toDateTime` cannot exceed a period of 90 days.

:::info

This command supports only csv and json output.

:::

## Examples

Get details about direct routing calls made between 2020-10-31 and today.

```sh
m365 teams report directroutingcalls --fromDateTime 2020-10-31
```

Get details about direct routing calls made between 2020-10-31 and 2020-12-31 and exports the report data in the specified path in text format.

```sh
m365 teams report directroutingcalls --fromDateTime 2020-10-31 --toDateTime 2020-12-31 --output text > "directroutingcalls.txt"
```

Get details about direct routing calls made between 2020-10-31 and 2020-12-31 and exports the report data in the specified path in json format.

```sh
m365 teams report directroutingcalls --fromDateTime 2020-10-31 --toDateTime 2020-12-31 --output json > "directroutingcalls.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ``` json
  {
    "@odata.count": 1,
    "value": [
      {
        "id": "9e8bba57-dc14-533a-a7dd-f0da6575eed1",
        "correlationId": "c98e1515-a937-4b81-b8a8-3992afde64e0",
        "userId": "db03c14b-06eb-4189-939b-7cbf3a20ba27",
        "userPrincipalName": "richard.malk@contoso.com",
        "userDisplayName": "Richard Malk",
        "startDateTime": "2019-11-01T00:00:25.105Z",
        "inviteDateTime": "2019-11-01T00:00:21.949Z",
        "failureDateTime": "0001-01-01T00:00:00Z",
        "endDateTime": "2019-11-01T00:00:30.105Z",
        "duration": 5,
        "callType": "ByotIn",
        "successfulCall": true,
        "callerNumber": "+12345678***",
        "calleeNumber": "+01234567***",
        "mediaPathLocation": "USWE",
        "signalingLocation": "EUNO",
        "finalSipCode": 0,
        "callEndSubReason": 540000,
        "finalSipCodePhrase": "BYE",
        "trunkFullyQualifiedDomainName": "tll-audiocodes01.adatum.biz",
        "mediaBypassEnabled": false
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ``` text
  id,calleeNumber,callerNumber,startDateTime
  9e8bba57-dc14-533a-a7dd-f0da6575eed1,+01234567***,+12345678***,2019-11-01T00:00:25.105Z
  ```

  </TabItem>
  <TabItem value="CSV">

  ``` text
  id,calleeNumber,callerNumber,startDateTime
  9e8bba57-dc14-533a-a7dd-f0da6575eed1,+01234567***,+12345678***,2019-11-01T00:00:25.105Z
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  id,calleeNumber,callerNumber,startDateTime
  9e8bba57-dc14-533a-a7dd-f0da6575eed1,+01234567***,+12345678***,2019-11-01T00:00:25.105Z
  ```

  </TabItem>
</Tabs>
