-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo site sharingpermission set

Controls how a site and its components can be shared

## Usage

```sh
m365 spo site sharingpermission set [options]
```

## Options

```md definition-list
`-u, --url <url>`
: URL of the site.

`--capability <capability>`
: Define how the site is shared. Possible values: `full`, `limited`, `ownersOnly`.
```

<Global />

## Remarks

When specifying `capability`, consider the following:
- `full`: Site owners and members can share files, folders, and the site. People with Edit permissions can share files and folders.
- `limited`: Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site.
- `ownersOnly`: Only site owners can share files, folders, and the site.

## Examples

Update the sharing permissions for a site so only owners can share files and the site

```sh
m365 spo site sharingpermission set --siteUrl https://siteaddress.com/sites/sitename  --capability ownersOnly
```

Update the sharing permissions for a site where so both owners and members can share files and the site

```sh
m365 spo site sharingpermission set --siteUrl https://siteaddress.com/sites/sitename  --capability full
```

Update the sharing permissions for a site where so owners can share the site, but members can only share files

```sh
m365 spo site sharingpermission set --siteUrl https://siteaddress.com/sites/sitename --capability limited
```

## Response

The command won't return a response on success.

## More information

- Sharing a SharePoint site: [https://support.microsoft.com/office/EXAMPLE_SECRET_VALUE_PLACEHOLDER](https://support.microsoft.com/office/EXAMPLE_SECRET_VALUE_PLACEHOLDER)
