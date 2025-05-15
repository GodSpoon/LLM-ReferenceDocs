-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams chat member list

Lists all members from a Microsoft Teams chat conversation.

## Usage

```sh
m365 teams chat member list [options]
```

## Options

```md definition-list
`-i, --chatId <chatId>`
: The ID of the chat conversation.
```

<Global />

## Examples

List the members from a Microsoft Teams chat conversation.

```sh
m365 teams chat member list --chatId 19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@unq.gbl.spaces
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER=",
      "roles": [
        "owner"
      ],
      "displayName": "John Doe",
      "visibleHistoryStartDateTime": "0001-01-01T00:00:00Z",
      "userId": "78ccf530-bbf0-47e4-aae6-da5f8c6fb142",
      "email": "johndoe@contoso.onmicrosoft.com",
      "tenantId": "446355e4-e7e3-43d5-82f8-d7ad8272d55b"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  userId                                displayName     email
  ------------------------------------  --------------  ---------------------------------
  78ccf530-bbf0-47e4-aae6-da5f8c6fb142  John Doe        johndoe@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  userId,displayName,email
  78ccf530-bbf0-47e4-aae6-da5f8c6fb142,John Doe,johndoe@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams chat member list --chatId "19:EXAMPLE_SECRET_VALUE_PLACEHOLDER@unq.gbl.spaces"

  Date: 5/8/2023

  ## John Doe (EXAMPLE_SECRET_VALUE_PLACEHOLDER=)

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER=
  displayName | John Doe
  visibleHistoryStartDateTime | 0001-01-01T00:00:00Z
  userId | 78ccf530-bbf0-47e4-aae6-da5f8c6fb142
  email | johndoe@contoso.onmicrosoft.com
  tenantId | 446355e4-e7e3-43d5-82f8-d7ad8272d55b
  ```

  </TabItem>
</Tabs>
