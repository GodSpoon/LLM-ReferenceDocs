-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra roledefinition set

Updates a custom Microsoft Entra ID role definition

## Usage

```sh
m365 entra roledefinition set [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The id of the role definition to be updated. Specify either `id` or `displayName`, but not both.

`-n, --displayName [displayName]`
: The display name of the role definition to be updated. Specify either `id` or `displayName`, but not both.

`--newDisplayName [newDisplayName]`
: Updated display name for the role definition.

`-d, --description [description]`
: Updated description for the role definition.

`-e, --enabled [enabled]`
: Indicates if the role is enabled for the assignment.

`a-, --allowedResourceActions [allowedResourceActions]`
: Updated comma-separated list of resource actions allowed for the role.

`-v, --version [version]`
: Updated version of the role definition.
```

<Global />

## Remarks

Use the `m365 entra rolepermission list --resourceNamespace microsoft.directory` command to get a list of available resource actions.

## Examples

Update a custom Microsoft Entra ID role specified by the id

```sh
m365 entra roledefinition set --id fadbc488-151d-4431-9143-6abbffae759f --newDisplayName 'Application Remover' --description 'Allows to remove any Entra ID application' --allowedResourceActions 'microsoft.directory/applications/delete'
```

Update a custom Microsoft Entra ID role specified by the display name

```sh
m365 entra roledefinition set --displayName 'Application Remover' --version '1.0' --enabled true --allowedResourceActions 'microsoft.directory/applications/delete,microsoft.directory/applications/owners/update'
```

## Response

The command won't return a response on success

## More information

- https://learn.microsoft.com/graph/api/rbacapplication-post-roledefinitions
