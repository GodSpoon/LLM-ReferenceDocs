-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# purview threatassessment list

Get a list of threat assessments

## Usage

```sh
m365 purview threatassessment list [options]
```

## Options

```md definition-list
`-t, --type [type]`
: The type of threat assessment to retrieve. Allowed values are `mail`, `file`, `emailFile` and `url`.
```

<Global />

## Examples

Get a list of threat assessments

```sh
m365 purview threatassessment list
```

Get a list of threat assessments of type _mail_

```sh
m365 purview threatassessment list --type mail
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "type": "mail",
      "id": "49c5ef5b-1f65-444a-e6b9-08d772ea2059",
      "createdDateTime": "2019-11-27T03:30:18.6890937Z",
      "contentType": "mail",
      "expectedAssessment": "block",
      "category": "spam",
      "status": "pending",
      "requestSource": "administrator",
      "recipientEmail": "john@contoso.onmicrosoft.com",
      "destinationRoutingReason": "notJunk",
      "messageUri": "https://graph.microsoft.com/v1.0/users/c52ce8db-3e4b-4181-93c4-7d6b6bffaf60/messages/AAMkADU3MWUxOTU0LWNlOTEt=",
      "createdBy": {
        "user": {
          "id": "c52ce8db-3e4b-4181-93c4-7d6b6bffaf60",
          "displayName": "John Doe"
        }
      }
    }
  ];
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    type  category
  ------------------------------------  -----------  --------
  49c5ef5b-1f65-444a-e6b9-08d772ea2059  mail         spam
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,type,category
  49c5ef5b-1f65-444a-e6b9-08d772ea2059,mail,spam
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # purview threatassessment list

  Date: 16/2/2023

  ## a47e428c-a7bd-4cf2-f061-08db0f58b736

  Property | Value
  ---------|-------
  type | mail
  id | 49c5ef5b-1f65-444a-e6b9-08d772ea2059
  createdDateTime | 2019-11-27T03:30:18.6890937Z
  contentType | mail
  expectedAssessment | block
  category | spam
  status | pending
  recipientEmail | john@contoso.onmicrosoft.com
  destinationRoutingReason | notJunk
  messageUri | https://graph.microsoft.com/v1.0/users/c52ce8db-3e4b-4181-93c4-7d6b6bffaf60/messages/AAMkADU3MWUxOTU0LWNlOTEt=
  createdBy | {"user":{"id":"c52ce8db-3e4b-4181-93c4-7d6b6bffaf60","displayName":"John Doe"}}
  ```

  </TabItem>
</Tabs>
