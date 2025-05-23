-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra enterpriseapp remove

Deletes an enterprise application (or service principal)

## Usage

```sh
m365 entra enterpriseapp remove [options]
```

## Alias

```sh
m365 entra sp remove [options]
```

## Options

```md definition-list
`-i, --id [id]`
: ID of the enterprise application.

`-n, --displayName [displayName]`
: Display name of the enterprise application.

`--objectId [objectId]`
: ObjectId of the enterprise application.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Examples

Delete an enterprise application by application ID.

```sh
m365 entra enterpriseapp remove --id b2307a39-e878-458b-bc90-03bc578531d6 --force
```

Delete an enterprise application by display name.

```sh
m365 entra enterpriseapp remove --displayName "Contoso app"
```

Delete an enterprise application by object ID.

```sh
m365 entra enterpriseapp remove --objectId b2307a39-e878-458b-bc90-03bc578531dd
```

## Response

The command won't return a response on success.

## More information

- Application and service principal objects in Microsoft Entra ID: [https://learn.microsoft.com/azure/active-directory/develop/active-directory-application-objects](https://learn.microsoft.com/azure/active-directory/develop/active-directory-application-objects)
