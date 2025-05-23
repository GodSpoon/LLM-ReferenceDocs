-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra oauth2grant list

Lists OAuth2 permission grants for the specified service principal

## Usage

```sh
m365 entra oauth2grant list [options]
```

## Options

```md definition-list
`-i, --spObjectId <spObjectId>`
: objectId of the service principal for which the configured OAuth2 permission grants should be retrieved.
```

<Global />

## Remarks

In order to list existing OAuth2 permissions granted to a service principal, you need its `objectId`. You can retrieve it using the [entra enterpriseapp get](../enterpriseapp/enterpriseapp-get.mdx) command.

When using the text output type (default), the command lists only the values of the `objectId`, `resourceId` and `scope` properties of the OAuth grant. When setting the output type to JSON, all available properties are included in the command output.

## Examples

List OAuth2 permissions granted to service principal with `objectId` _b2307a39-e878-458b-bc90-03bc578531d6_.

```sh
m365 entra oauth2grant list --spObjectId b2307a39-e878-458b-bc90-03bc578531d6
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "clientId": "283f45c9-6b6f-4d15-a7b8-da2c2f3f6e67",
      "consentType": "AllPrincipals",
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "principalId": null,
      "resourceId": "65429544-d782-42f4-bcfe-cd9c4bf566eb",
      "scope": "Mail.Read Mail.Send"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  resourceId                            scope
  ------------------------------------  -------------------
  65429544-d782-42f4-bcfe-cd9c4bf566eb  Mail.Read Mail.Send
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  clientId,consentType,id,resourceId,scope
  283f45c9-6b6f-4d15-a7b8-da2c2f3f6e67,AllPrincipals,EXAMPLE_SECRET_VALUE_PLACEHOLDER,65429544-d782-42f4-bcfe-cd9c4bf566eb,Mail.Read Mail.Send
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra oauth2grant list --spObjectId "283f45c9-6b6f-4d15-a7b8-da2c2f3f6e67"

  Date: 2023-06-02

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  clientId | 283f45c9-6b6f-4d15-a7b8-da2c2f3f6e67
  consentType | AllPrincipals
  id | yUU\_KG9rFU2nuNosLz9uZ0SVQmWC1\_RCvP7NnEv1Zus
  resourceId | 65429544-d782-42f4-bcfe-cd9c4bf566eb
  scope | Mail.Read Mail.Send
  ```

  </TabItem>
</Tabs>

## More information

- Application and service principal objects in Microsoft Entra ID: [https://learn.microsoft.com/azure/active-directory/develop/active-directory-application-objects](https://learn.microsoft.com/azure/active-directory/develop/active-directory-application-objects)
- List oauth2PermissionGrants: [https://learn.microsoft.com/graph/api/oauth2permissiongrant-list?view=graph-rest-1.0](https://learn.microsoft.com/graph/api/oauth2permissiongrant-list?view=graph-rest-1.0)
