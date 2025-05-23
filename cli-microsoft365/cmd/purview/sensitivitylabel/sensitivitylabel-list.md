-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# purview sensitivitylabel list

Get a list of sensitivity labels

## Usage

```sh
m365 purview sensitivitylabel list [options]
```

## Options

```md definition-list
`--userId [userId]`
: User's Microsoft Entra ID. Optionally specify this if you want to get a list of sensitivity labels that the user has access to. Specify either `userId` or `userName` but not both.

`--userName [userName]`
: User's UPN (user principal name, e.g. johndoe@example.com). Optionally specify this if you want to get a list of sensitivity labels that the user has access to. Specify either `userId` or `userName` but not both.
```

<Global />

## Remarks

:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::

:::warning

When operating in app-only mode, you have the option to use either the `userName` or `userId` parameters to retrieve the sensitivity label for a specific user. Without specifying either of these parameters, the command will retrieve the sensitivity label for the currently authenticated user when operating in delegated mode.

:::

## Examples

Get a list of sensitivity labels.

```sh
m365 purview sensitivitylabel list
```

Get a list of sensitivity labels that a specific user has access to by its Id.

```sh
m365 purview sensitivitylabel list --userId 59f80e08-24b1-41f8-8586-16765fd830d3
```

Get a list of sensitivity labels that a specific user has access to by its UPN.

```sh
m365 purview sensitivitylabel list --userName john.doe@contoso.com
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "6f4fb2db-ecf4-4279-94ba-23d059bf157e",
      "name": "Unrestricted",
      "description": "",
      "color": "",
      "sensitivity": 0,
      "tooltip": "Information either intended for general distribution, or which would not have any impact on the organization if it were to be distributed.",
      "isActive": true,
      "isAppliable": true,
      "contentFormats": [
        "file",
        "email"
      ],
      "hasProtection": false,
      "parent": null
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                    name                   isActive
  ------------------------------------  ---------------------  --------
  6f4fb2db-ecf4-4279-94ba-23d059bf157e  Unrestricted           true
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,name,isActive
  6f4fb2db-ecf4-4279-94ba-23d059bf157e,Unrestricted,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # purview sensitivitylabel list

  Date: 3/26/2023

  ## Unrestricted (6f4fb2db-ecf4-4279-94ba-23d059bf157e)

  Property | Value
  ---------|-------
  id | 6f4fb2db-ecf4-4279-94ba-23d059bf157e
  name | Unrestricted
  description |
  color |
  sensitivity | 0
  tooltip | Information either intended for general distribution, or which would not have any impact on the organization if it were to be distributed.
  isActive | true
  isAppliable | true
  hasProtection | false
  parent | null
  ```

  </TabItem>
</Tabs>
