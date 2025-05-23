-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo site apppermission remove

Removes a specific application permission from a site

## Usage

```sh
m365 spo site apppermission remove [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: URL of the site collection where the permission to remove is located

`--appId [appId]`
: App Id

`-n, --appDisplayName [appDisplayName]`
: App display name

`-i, --id [id]`
: ID of the permission to remove

`-f, --force`
: Don't prompt for confirmation
```

<Global />

## Example

Removes all application permissions for application with id _89ea5c94-7736-4e25-95ad-3fa95f62b66e_ on site _https://contoso.sharepoint.com/sites/project-x_

```sh
m365 spo site apppermission remove --siteUrl https://contoso.sharepoint.com/sites/project-x --appId 89ea5c94-7736-4e25-95ad-3fa95f62b66e
```

Removes all application permissions for application named _Foo_ on site _https://contoso.sharepoint.com/sites/project-x_

```sh
m365 spo site apppermission remove --siteUrl https://contoso.sharepoint.com/sites/project-x --appDisplayName Foo
```

Removes the application permission with the specified ID on site _https://contoso.sharepoint.com/sites/project-x_

```sh
m365 spo site apppermission remove --siteUrl https://contoso.sharepoint.com/sites/project-x --id EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

## Response

The command won't return a response on success.
