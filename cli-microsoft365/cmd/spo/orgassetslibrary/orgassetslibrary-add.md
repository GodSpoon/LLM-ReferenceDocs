-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo orgassetslibrary add

Promotes an existing library to become an organization assets library

## Usage

```sh
m365 spo orgassetslibrary add [options]
```

## Options

```md definition-list
`--libraryUrl <libraryUrl>`
: The URL of the library to promote.

`--thumbnailUrl [thumbnailUrl]`
: The URL of the thumbnail to render.

`--cdnType [cdnType]`
: Specifies the CDN type. Allowed values `Public`, `Private`. Default `Private`.

`--orgAssetType [orgAssetType]`
: Specifies the type of organizational library. Allowed values `ImageDocumentLibrary`, `OfficeTemplateLibrary`, `OfficeFontLibrary`. Defaults to `ImageDocumentLibrary`.
```

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

To enable CDN in your tenant use the [spo cdn set](../cdn/cdn-set.mdx) command.

The document library on which you run the command must at least have read permissions for all users, except external users.

## Examples

Promotes an existing library to become an organization assets library

```sh
m365 spo orgassetslibrary add --libraryUrl "https://contoso.sharepoint.com/SiteAssets"
```

Promotes an existing library to become an organization assets library with Thumbnail

```sh
m365 spo orgassetslibrary --libraryUrl "https://contoso.sharepoint.com/SiteAssets" --thumbnailUrl "https://contoso.sharepoint.com/assets/logo.png"
```

Promotes an existing library to become an organization assets Office template library

```sh
m365 spo orgassetslibrary add --libraryUrl "https://contoso.sharepoint.com/SiteAssets" --orgAssetType "OfficeTemplateLibrary"
```

## Response

The command won't return a response on success.
