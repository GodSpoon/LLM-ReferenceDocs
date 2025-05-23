-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo site commsite enable

Enables communication site features on the specified site

## Usage

```sh
m365 spo site commsite enable [options]
```

## Options

```md definition-list
`-u, --url <url>`
: The URL of the site to enable communication site features on

`-i, --designPackageId [designPackageId]`
: The ID of the site design to apply when enabling communication site features. Specify designPackageId or designPackage but not both.

`-p, --designPackage [designPackage]`
: The site design to apply when enabling communication site features. Valid values are: Topic, Showcase, or Blank. Defaults to Topic. Specify designPackageId or designPackage but not both.
```

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Enable communication site features on an existing site

```sh
m365 spo site commsite enable --url https://contoso.sharepoint.com
```

Enable communication site features on an existing site and apply the Showcase design package using its ID.

```sh
m365 spo site commsite enable --url https://contoso.sharepoint.com --designPackageId 6142d2a0-63a5-4ba0-aede-d9fefca2c767
```

Enable communication site features on an existing site and apply the Showcase design package using its friendly name.

```sh
m365 spo site commsite enable --url https://contoso.sharepoint.com --designPackage Showcase
```

## Response

The command won't return a response on success.
