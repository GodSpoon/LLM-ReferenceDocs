-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage community add

Creates a new community in Viva Engage

## Usage

```sh
m365 viva engage community add [options]
```

## Options

```md definition-list
`--displayName <displayName>`
: The name of the community. The maximum length is 255 characters.

`--description <description>`
: The description of the community. The maximum length is 1024 characters.

`--privacy <privacy>`
: Defines the privacy level of the community. The possible values are: `public`, `private`.

`--adminEntraIds [adminEntraIds]`
: Comma-separated list of Microsoft Entra IDs, assigning admin privileges to the designated individuals. Required when using application permissions. Specify either `adminEntraIds` or `adminEntraUserNames`, but not both.

`--adminEntraUserNames [adminEntraUserNames]`
: Comma-separated list of Microsoft Entra UPNs, assigning admin privileges to the designated individuals. Required when using application permissions. Specify either `adminEntraIds` or `adminEntraUserNames`, but not both.

`--wait`
: Wait for the operation to finish.
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reaches general availability.

:::

Creating a community is limited to networks in Native mode only - legacy and external Yammer networks will not be able to use this API for community creation.

## Examples

Create a public community and wait for the community to be created

```sh
m365 viva engage community add --displayName "Software engineers" --description "A community for all software engineers" --privacy public --wait
```

Create a private community

```sh
m365 viva engage community add --displayName "Software engineers" --description "A community for all software engineers" --privacy private
```

Create a private community with owners

```sh
m365 viva engage community add --displayName "Software engineers" --description "A community for all software engineers" --privacy private --adminEntraUserNames "john.doe@contoso.onmicrosoft.com,jane.doe@contoso.onmicrosoft.com"
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  "https://graph.microsoft.com/beta/employeeExperience/engagementAsyncOperations('EXAMPLE_SECRET_VALUE_PLACEHOLDER')"
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  https://graph.microsoft.com/beta/employeeExperience/engagementAsyncOperations('EXAMPLE_SECRET_VALUE_PLACEHOLDER')
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  https://graph.microsoft.com/beta/employeeExperience/engagementAsyncOperations('EXAMPLE_SECRET_VALUE_PLACEHOLDER')
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  https://graph.microsoft.com/beta/employeeExperience/engagementAsyncOperations('EXAMPLE_SECRET_VALUE_PLACEHOLDER')
  ```

  </TabItem>
</Tabs>

### `wait` response

When we make use of the option `wait` the response will differ. 

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "createdDateTime": "2024-04-10T12:16:18.0240578Z",
    "lastActionDateTime": "2024-04-10T12:16:18.0240592Z",
    "status": "succeeded",
    "statusDetail": null,
    "resourceLocation": "https://graph.microsoft.com/beta/employeeExperience/communities('EXAMPLE_SECRET_VALUE_PLACEHOLDER')",
    "operationType": "createCommunity",
    "resourceId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  createdDateTime   : 2024-04-10T12:45:03.4020639Z
  id                : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  lastActionDateTime: 2024-04-10T12:45:03.4020656Z
  operationType     : createCommunity
  resourceId        : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  resourceLocation  : https://graph.microsoft.com/beta/employeeExperience/communities('EXAMPLE_SECRET_VALUE_PLACEHOLDER')
  status            : succeeded
  statusDetail      : null
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,createdDateTime,lastActionDateTime,status,statusDetail,resourceLocation,operationType,resourceId
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,2024-04-12T11:24:29.074105Z,2024-04-12T11:24:29.0741064Z,succeeded,,https://graph.microsoft.com/beta/employeeExperience/communities('EXAMPLE_SECRET_VALUE_PLACEHOLDER'),createCommunity,EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # viva engage community add --displayName "Software engineers" --description "A community for all software engineers" --privacy "private" --wait "true"

  Date: 10/04/2024

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  createdDateTime | 2024-04-10T12:47:47.3488087Z
  lastActionDateTime | 2024-04-10T12:47:47.3488107Z
  status | succeeded
  resourceLocation | https://graph.microsoft.com/beta/employeeExperience/communities('EXAMPLE_SECRET_VALUE_PLACEHOLDER')
  operationType | createCommunity
  resourceId | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
</Tabs>
