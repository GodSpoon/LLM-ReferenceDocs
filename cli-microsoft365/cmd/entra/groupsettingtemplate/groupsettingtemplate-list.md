-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra groupsettingtemplate list

Lists Entra group settings templates

## Usage

```sh
m365 entra groupsettingtemplate list [options]
```

## Options

<Global />

## Examples

List all group setting templates in the tenant

```sh
m365 entra groupsettingtemplate list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
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
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    displayName
  ------------------------------------  ------------------------------------
  08d542b9-071f-4e16-94b0-74abb372e3d9  Group.Unified.Guest
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
  # entra groupsettingtemplate list

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
