-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra approleassignment add

Adds service principal permissions also known as scopes and app role assignments for specified Microsoft Entra application registration

## Usage

```sh
m365 entra approleassignment add [options]
```

## Options

```md definition-list
`--appId [appId]`
: Application appId also known as clientId of the App Registration to which the configured scopes (app roles) should be applied.

`--appObjectId [appObjectId]`
: Application objectId of the App Registration to which the configured scopes (app roles) should be applied.

`--appDisplayName [appDisplayName]`
: Application name of the App Registration to which the configured scopes (app roles) should be applied.

`-r, --resource <resource>`
: Service principal name, appId or objectId that has the scopes (roles) e.g. `SharePoint`.

`-s, --scopes <scopes>`
: Permissions known also as scopes and roles to grant the application with. If multiple permissions have to be granted, they have to be comma-separated e.g. `Sites.Read.All`, `Sites.ReadWrite.all`.
```

<Global />

## Remarks

This command requires tenant administrator permissions.

Specify either the `appId`, `appObjectId` or `appDisplayName` but not multiple. If you specify more than one option value, the command will fail with an error.

Autocomplete values for the `resource` option do not mean allowed values. The autocomplete will just suggest some known names, but that doesn't restrict you to use the name of your own custom application or other application within your tenant.

This command can also be used to assign permissions to system or user-assigned managed identity.

## Examples

Adds SharePoint _Sites.Read.All_ application permissions to Entra application with app id _57907bf8-73fa-43a6-89a5-1f603e29e451_

```sh
m365 entra approleassignment add --appId "57907bf8-73fa-43a6-89a5-1f603e29e451" --resource "SharePoint" --scopes "Sites.Read.All"
```

Adds multiple Microsoft Graph application permissions to an Entra application with the name _MyAppName__

```sh
m365 entra approleassignment add --appDisplayName "MyAppName" --resource "Microsoft Graph" --scopes "Mail.Read,Mail.Send"
```

Adds Microsoft Graph _Mail.Read_ application permissions to a system-managed identity app with objectId _57907bf8-73fa-43a6-89a5-1f603e29e451_

```sh
m365 entra approleassignment add --appObjectId "57907bf8-73fa-43a6-89a5-1f603e29e451" --resource "Microsoft Graph" --scopes "Mail.Read"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#servicePrincipals('6c519c5d-829a-47f9-9d5c-fd564ce103bd')/appRoleAssignments/$entity",
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "deletedDateTime": null,
      "appRoleId": "d13f72ca-a275-4b96-b789-48ebcc4da984",
      "createdDateTime": "2023-06-01T19:00:20.8353382Z",
      "principalDisplayName": "QuillBot",
      "principalId": "6c519c5d-829a-47f9-9d5c-fd564ce103bd",
      "principalType": "ServicePrincipal",
      "resourceDisplayName": "Office 365 SharePoint Online",
      "resourceId": "eafaa868-bc8f-43ac-a882-b65a62a668fd"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  objectId            : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  principalDisplayName: QuillBot
  resourceDisplayName : Microsoft Graph
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  objectId,principalDisplayName,resourceDisplayName
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,QuillBot,Microsoft Graph
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra approleassignment add --appId "e89804ac-a571-48cf-b2ba-fd57b5d49993" --resource "Microsoft Graph" --scopes "Mail.Read"

  Date: 2023-06-01

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  objectId | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  principalDisplayName | QuillBot
  resourceDisplayName | Microsoft Graph
  ```

  </TabItem>
</Tabs>

## More information

- Microsoft Graph permissions reference: [https://learn.microsoft.com/graph/permissions-reference](https://learn.microsoft.com/graph/permissions-reference)
