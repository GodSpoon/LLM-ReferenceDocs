-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra user groupmembership list

Retrieves all groups where the user is a member of

## Usage

```sh
m365 entra user groupmembership list [options]
```

## Options

```md definition-list
`-i, --userId [userId]`
: The ID of the user to retrieve information for. Use either `userId`, `userName` or `userEmail`, but not multiple.

`-n, --userName [userName]`
: The name of the user to retrieve information for. Use either `userId`, `userName` or `userEmail`, but not multiple.

`-e, --userEmail [userEmail]`
: The email of the user to retrieve information for. Use either `userId`, `userName` or `userEmail`, but not multiple.

`--securityEnabledOnly [securityEnabledOnly]`
: Specifies that only security-enabled groups that the user is a member of should be returned
```

<Global />

## Examples

Retrieves groups that the user is a member of

```sh
m365 entra user groupmembership list --userId '1caf7dcd-7e83-4c3a-94f7-932a1299c844'
```

Retrieves only security groups that the user is a member of

```sh
m365 entra user groupmembership list --userName 'john.doe@contoso.com' --securityEnabledOnly
```

Retrieves groups where the currently logged user is a member of

```sh
m365 entra user groupmembership list --userId '@meId'
```

Retrieves groups where the currently logged user is a member of

```sh
m365 entra user groupmembership list --userName '@meUserName'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "groupId": "01b62bc5-9701-4f93-9587-9d1ea58a086d"
    },
    {
      "groupId": "619701a2-4bdc-494a-a9dd-9d3aeebcafd9"
    },
    {
      "groupId": "ec98d904-ac8c-49f0-99e1-c9c0e1a1e453"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  groupId
  ------------------------------------
  01b62bc5-9701-4f93-9587-9d1ea58a086d
  619701a2-4bdc-494a-a9dd-9d3aeebcafd9
  ec98d904-ac8c-49f0-99e1-c9c0e1a1e453
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  groupId
  01b62bc5-9701-4f93-9587-9d1ea58a086d
  619701a2-4bdc-494a-a9dd-9d3aeebcafd9
  ec98d904-ac8c-49f0-99e1-c9c0e1a1e453
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra user groupmembership list --userId "1f5595b2-aa07-445d-9801-a45ea18160b2"

  Date: 5/17/2024

  Property | Value
  ---------|-------
  groupId | 01b62bc5-9701-4f93-9587-9d1ea58a086d

  Property | Value
  ---------|-------
  groupId | 619701a2-4bdc-494a-a9dd-9d3aeebcafd9

  Property | Value
  ---------|-------
  groupId | ec98d904-ac8c-49f0-99e1-c9c0e1a1e453
  ```

  </TabItem>
</Tabs>
