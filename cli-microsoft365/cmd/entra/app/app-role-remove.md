-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra app role remove

Removes role from the specified Entra app registration

## Usage

```sh
m365 entra app role remove [options]
```

## Alias

```sh
m365 entra appregistration role remove [options]
```

## Options

```md definition-list
`--appId [appId]`
: Application (client) ID of the Entra application registration from which role should be removed. Specify either `appId`, `appObjectId` or `appName`

`--appObjectId [appObjectId]`
: Object ID of the Entra application registration from which role should be removed. Specify either `appId`, `appObjectId` or `appName`

`--appName [appName]`
: Name of the Entra application registration from which role should be removed. Specify either `appId`, `appObjectId` or `appName`

`-n, --name [name]`
: Name of the role to remove. Specify either `name`, `id` or `claim`

`-i, --id [id]`
: Id of the role to remove. Specify either `name`, `id` or `claim`

`-c, --claim [claim]`
: Claim value of the role to remove. Specify either `name`, `id` or `claim`

`-f, --force`
: Don't prompt for confirmation to remove the role.
```

<Global />

## Remarks

For best performance use the `appObjectId` option to reference the Entra application registration from which to remove the role. If you use `appId` or `appName`, this command will first need to find the corresponding object ID for that application.

If the command finds multiple Entra application registrations with the specified app name, it will prompt you to disambiguate which app it should use, listing the discovered object IDs.

If the command finds multiple roles with the specified role name, it will prompt you to disambiguate which role it should use, listing the claim values.

If the role to be removed is 'Enabled', this command will disable the role first and then remove.

## Examples

Remove role from a Entra application registration using object ID and role name options. Will prompt for confirmation before deleting the role.

```sh
m365 entra app role remove --appObjectId d75be2e1-0204-4f95-857d-51a37cf40be8 --name "Get Product"
```

Remove role from a Entra application registration using app (client) ID and role claim options. Will prompt for confirmation before deleting the role.

```sh
m365 entra app role remove --appId e75be2e1-0204-4f95-857d-51a37cf40be8 --claim "Product.Get"
```

Remove role from a Entra application registration using app name and role claim options. Will prompt for confirmation before deleting the role.

```sh
m365 entra app role remove --appName "My app" --claim "Product.Get"
```

Remove role from a Entra application registration using object ID and role id options. Will NOT prompt for confirmation before deleting the role.

```sh
m365 entra app role remove --appObjectId d75be2e1-0204-4f95-857d-51a37cf40be8 --id 15927ce6-1933-4b2f-b029-4dee3d53f4dd --force
```

## Response

The command won't return a response on success.
