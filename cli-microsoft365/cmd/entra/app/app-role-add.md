-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra app role add

Adds role to the specified Entra app registration

## Usage

```sh
m365 entra app role add [options]
```

## Alias

```sh
m365 entra appregistration role add [options]
```

## Options

```md definition-list
`--appId [appId]`
: Application (client) ID of the Entra application registration to which to add the role. Specify either `appId`, `appObjectId` or `appName`

`--appObjectId [appObjectId]`
: Object ID of the Entra application registration to which to add the role. Specify either `appId`, `appObjectId` or `appName`

`--appName [appName]`
: Name of the Entra application registration to which to add the role. Specify either `appId`, `appObjectId` or `appName`

`-n, --name <name>`
: Name of the role to add

`-d, --description <description>`
: Description of the role to add

`-m, --allowedMembers <allowedMembers>`
: Types of members that can be added to the group. Allowed values: `usersGroups`, `applications`, `both`

`-c, --claim <claim>`
: Claim value
```

<Global />

## Remarks

For best performance use the `appObjectId` option to reference the Entra application registration for which to add the role. If you use `appId` or `appName`, this command will first need to find the corresponding object ID for that application.

If the command finds multiple Entra application registrations with the specified app name, it will prompt you to disambiguate which app it should use, listing the discovered object IDs.

## Examples

Add role to the Entra application registration specified by its object ID

```sh
m365 entra app role add --appObjectId d75be2e1-0204-4f95-857d-51a37cf40be8 --name Managers --description "Managers" --allowedMembers usersGroups --claim managers
```

Add role to the Entra application registration specified by its app (client) ID

```sh
m365 entra app role add --appId e75be2e1-0204-4f95-857d-51a37cf40be8 --name Managers --description "Managers" --allowedMembers usersGroups --claim managers
```

Add role to the Entra application registration specified by its name

```sh
m365 entra app role add --appName "My app" --name Managers --description "Managers" --allowedMembers usersGroups --claim managers
```

## Response

The command won't return a response on success.
