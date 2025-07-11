-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# purview threatassessment get

Get a threat assessment

## Usage

```sh
m365 purview threatassessment get [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The Id of the threat assessment.

`--includeResults`
: (deprecated. Use option `withResults` instead) Include the threat assessment results.

`--withResults`
: Include the threat assessment results.
```

<Global />

## Examples

Get a threat assessment.

```sh
m365 purview threatassessment get --id c37d695e-d581-4ae9-82a0-9364eba4291e
```

Get a threat assessment including results.

```sh
m365 purview threatassessment get --id c37d695e-d581-4ae9-82a0-9364eba4291e --withResults
```

## Response

### Standard Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "8aaba0ac-ec4d-4e62-5774-08db16c68731",
    "createdDateTime": "2023-02-25T00:23:33.0550644Z",
    "contentType": "mail",
    "expectedAssessment": "block",
    "category": "spam",
    "status": "pending",
    "requestSource": "administrator",
    "recipientEmail": "john@contoso.com",
    "destinationRoutingReason": "notJunk",
    "messageUri": "https://graph.microsoft.com/v1.0/users/john@contoso.com/messages/EXAMPLE_SECRET_VALUE_PLACEHOLDER=",
    "createdBy": {
      "user": {
        "id": "fe36f75e-c103-410b-a18a-2bf6df06ac3a",
        "displayName": "John Doe"
      }
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  category                : spam
  contentType             : mail
  createdBy               : {"user":{"id":"fe36f75e-c103-410b-a18a-2bf6df06ac3a","displayName":"John Doe"}}
  createdDateTime         : 2023-02-25T00:23:33.0550644Z
  destinationRoutingReason: notJunk
  expectedAssessment      : block
  id                      : 8aaba0ac-ec4d-4e62-5774-08db16c68731
  messageUri              : https://graph.microsoft.com/v1.0/users/john@contoso.com/messages/EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  recipientEmail          : john@contoso.com
  requestSource           : administrator
  status                  : pending
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,createdDateTime,contentType,expectedAssessment,category,status,requestSource,recipientEmail,destinationRoutingReason,messageUri,createdBy
  8aaba0ac-ec4d-4e62-5774-08db16c68731,2023-02-25T00:23:33.0550644Z,mail,block,spam,pending,administrator,john@contoso.com,notJunk,https://graph.microsoft.com/v1.0/users/john@contoso.com/messages/EXAMPLE_SECRET_VALUE_PLACEHOLDER=,"{""user"":{""id"":""fe36f75e-c103-410b-a18a-2bf6df06ac3a"",""displayName"":""John Doe""}}"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # purview threatassessment get --id "8aaba0ac-ec4d-4e62-5774-08db16c68731"

  Date: 25/02/2023

  ## 8aaba0ac-ec4d-4e62-5774-08db16c68731

  Property | Value
  ---------|-------
  id | 8aaba0ac-ec4d-4e62-5774-08db16c68731
  createdDateTime | 2023-02-25T00:23:33.0550644Z
  contentType | mail
  expectedAssessment | block
  category | spam
  status | pending
  requestSource | administrator
  recipientEmail | john@contoso.com
  destinationRoutingReason | notJunk
  messageUri | https://graph.microsoft.com/v1.0/users/john@contoso.com/messages/EXAMPLE_SECRET_VALUE_PLACEHOLDER\_hLMK5kAAAAAAEMAABiOC8xvYmdT6G2E\_hLMK5kAALHNaMuAAA=
  ```

  </TabItem>
</Tabs>

### `withResults` response

When we make use of the option `withResults` the response will differ. 

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "8aaba0ac-ec4d-4e62-5774-08db16c68731",
    "createdDateTime": "2023-02-25T00:23:33.0550644Z",
    "contentType": "mail",
    "expectedAssessment": "block",
    "category": "spam",
    "status": "pending",
    "requestSource": "administrator",
    "recipientEmail": "john@contoso.com",
    "destinationRoutingReason": "notJunk",
    "messageUri": "https://graph.microsoft.com/v1.0/users/john@contoso.com/messages/EXAMPLE_SECRET_VALUE_PLACEHOLDER=",
    "createdBy": {
      "user": {
        "id": "fe36f75e-c103-410b-a18a-2bf6df06ac3a",
        "displayName": "John Doe"
      }
    },
    "results": [
      {
        "id": "a5455871-18d1-44d8-0866-08db16c68b85",
        "createdDateTime": "2023-02-25T00:23:40.28Z",
        "resultType": "checkPolicy",
        "message": "No policy was hit."
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  category                : spam
  contentType             : mail
  createdBy               : {"user":{"id":"fe36f75e-c103-410b-a18a-2bf6df06ac3a","displayName":"John Doe"}}
  createdDateTime         : 2023-02-25T00:23:33.0550644Z
  destinationRoutingReason: notJunk
  expectedAssessment      : block
  id                      : 8aaba0ac-ec4d-4e62-5774-08db16c68731
  messageUri              : https://graph.microsoft.com/v1.0/users/john@contoso.com/messages/EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  recipientEmail          : john@contoso.com
  requestSource           : administrator
  results                 : [{"id":"a5455871-18d1-44d8-0866-08db16c68b85","createdDateTime":"2023-02-25T00:23:40.28Z","resultType":"checkPolicy","message":"No policy was hit."}]
  status                  : pending
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,createdDateTime,contentType,expectedAssessment,category,status,requestSource,recipientEmail,destinationRoutingReason,messageUri,createdBy,results
  8aaba0ac-ec4d-4e62-5774-08db16c68731,2023-02-25T00:23:33.0550644Z,mail,block,spam,pending,administrator,john@contoso.com,notJunk,https://graph.microsoft.com/v1.0/users/john@contoso.com/messages/EXAMPLE_SECRET_VALUE_PLACEHOLDER=,"{""user"":{""id"":""fe36f75e-c103-410b-a18a-2bf6df06ac3a"",""displayName"":""John Doe""}}","[{""id"":""a5455871-18d1-44d8-0866-08db16c68b85"",""createdDateTime"":""2023-02-25T00:23:40.28Z"",""resultType"":""checkPolicy"",""message"":""No policy was hit.""}]"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # purview threatassessment get --id "8aaba0ac-ec4d-4e62-5774-08db16c68731" --withResults "true"

  Date: 25/02/2023

  ## 8aaba0ac-ec4d-4e62-5774-08db16c68731

  Property | Value
  ---------|-------
  id | 8aaba0ac-ec4d-4e62-5774-08db16c68731
  createdDateTime | 2023-02-25T00:23:33.0550644Z
  contentType | mail
  expectedAssessment | block
  category | spam
  status | pending
  requestSource | administrator
  recipientEmail | john@contoso.com
  destinationRoutingReason | notJunk
  messageUri | https://graph.microsoft.com/v1.0/users/john@contoso.com/messages/EXAMPLE_SECRET_VALUE_PLACEHOLDER\_hLMK5kAAAAAAEMAABiOC8xvYmdT6G2E\_hLMK5kAALHNaMuAAA=
  ```

  </TabItem>
</Tabs>
