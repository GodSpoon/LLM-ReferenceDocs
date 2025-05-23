-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra groupsettingtemplate get

Gets information about the specified Entra group settings template

## Usage

```sh
m365 entra groupsettingtemplate get [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the settings template to retrieve. Specify the `id` or `displayName` but not both

`-n, --displayName [displayName]`
: The display name of the settings template to retrieve. Specify the `id` or `displayName` but not both
```

<Global />

## Examples

Get information about the group setting template with id _62375ab9-6b52-47ed-826b-58e47e0e304b_

```sh
m365 entra groupsettingtemplate get --id 62375ab9-6b52-47ed-826b-58e47e0e304b
```

Get information about the group setting template with display name _Group.Unified_

```sh
m365 entra groupsettingtemplate get --displayName Group.Unified
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "08d542b9-071f-4e16-94b0-74abb372e3d9",
    "deletedDateTime": null,
    "displayName": "Group.Unified.Guest",
    "description": "Settings for a specific Unified Group",
    "values": [
      {
        "name": "AllowToAddGuests",
        "type": "System.Boolean",
        "defaultValue": "true",
        "description": "Flag indicating if guests are allowed in a specific Unified Group."
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  deletedDateTime: null
  description    : Settings for a specific Unified Group
  displayName    : Group.Unified.Guest
  id             : 08d542b9-071f-4e16-94b0-74abb372e3d9
  values         : [{"name":"AllowToAddGuests","type":"System.Boolean","defaultValue":"true","description":"Flag indicating if guests are allowed in a specific Unified Group."}]
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,description
  08d542b9-071f-4e16-94b0-74abb372e3d9,Group.Unified.Guest,Settings for a specific Unified Group
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra groupsettingtemplate get --id "08d542b9-071f-4e16-94b0-74abb372e3d9"

  Date: 2023-06-01

  ## Group.Unified.Guest (08d542b9-071f-4e16-94b0-74abb372e3d9)

  Property | Value
  ---------|-------
  id | 08d542b9-071f-4e16-94b0-74abb372e3d9
  displayName | Group.Unified.Guest
  description | Settings for a specific Unified Group
  ```

  </TabItem>
</Tabs>
