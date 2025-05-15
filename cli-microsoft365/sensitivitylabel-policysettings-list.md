<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# purview sensitivitylabel policysettings list

Get a list of policy settings for a sensitivity label.

## Usage

```sh
m365 purview sensitivitylabel policysettings list [options]
```

## Options

```md definition-list
`--userId [userId]`
: User's Microsoft Entra ID. Optionally specify this if you want to get a list of policy settings for a sensitivity label that the user has access to. Specify either `userId` or `userName` but not both.

`--userName [userName]`
: User's UPN (user principal name, e.g. johndoe@example.com). Optionally specify this if you want to get a list of policy settings for a sensitivity label that the user has access to. Specify either `userId` or `userName` but not both.
```

<Global />

## Remarks

:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::

:::warning

When operating in app-only mode, you have the option to use either the `userName` or `userId` parameters to retrieve the sensitivity policy settings for a specific user. Without specifying either of these parameters, the command will retrieve the sensitivity policy settings for the currently authenticated user when operating in delegated mode.

:::

## Examples

Get a list of policy settings for a sensitivity label.

```sh
m365 purview sensitivitylabel policysettings list
```

Get a list of policy settings for a sensitivity label that a specific user has access to by its Id.

```sh
m365 purview sensitivitylabel policysettings list --userId 59f80e08-24b1-41f8-8586-16765fd830d3
```

Get a list of policy settings for a sensitivity label that a specific user has access to by its UPN.

```sh
m365 purview sensitivitylabel policysettings list --userName john.doe@contoso.com
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "moreInfoUrl": "https://learn.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels?view=o365-worldwide#EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "isMandatory": true,
    "isDowngradeJustificationRequired": true,
    "defaultLabelId": "022bb90d-0cda-491d-b861-d195b14532dc"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  defaultLabelId                  : 022bb90d-0cda-491d-b861-d195b14532dc
  id                              : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  DB021CADB4
  isDowngradeJustificationRequired: true
  isMandatory                     : true
  moreInfoUrl                     : https://learn.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels?view=o365-worldwide#EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,moreInfoUrl,isMandatory,isDowngradeJustificationRequired,defaultLabelId
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,https://learn.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels?view=o365-worldwide#EXAMPLE_SECRET_VALUE_PLACEHOLDER,1,1,022bb90d-0cda-491d-b861-d195b14532dc
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # purview sensitivitylabel policysettings list

  Date: 4/11/2023

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  moreInfoUrl | https://learn.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels?view=o365-worldwide#EXAMPLE_SECRET_VALUE_PLACEHOLDER
  isMandatory | true
  isDowngradeJustificationRequired | true
  defaultLabelId | 022bb90d-0cda-491d-b861-d195b14532dc
  ```

  </TabItem>
</Tabs>
