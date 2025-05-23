-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo contenttype remove

Deletes site content type

## Usage

```sh
m365 spo contenttype remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Absolute URL of the site where the content type is located.

`-i, --id [id]`
: The ID of the content type to remove. Specify either `id` or `name`.

`-n, --name [name]`
: The name of the content type to remove. Specify either `id` or `name`.

`-f, --force`
: Don't prompt for confirming removal of the content type.
```

<Global />

## Remarks

If the specified content type is in use by a list and cannot be removed, you will be returned the error: _Another site or list is still using this content type._ SharePoint will not allow a content type to be removed unless any dependent objects are also emptied from the recycle bin including the second-stage recycle bin.

The content type you wish to remove can be selected by the ID or Name of the content type. Either ID or Name parameter must be specified.

## Examples

Remove a site content type by ID

```sh
m365 spo contenttype remove --id "0x01007926A45D687BA842B947286090B8F67D" --webUrl https://contoso.sharepoint.com
```

Remove a site content type by Name

```sh
m365 spo contenttype remove --name "My Content Type" --webUrl https://contoso.sharepoint.com --force
```

Remove a site content type without prompting for confirmation

```sh
m365 spo contenttype remove --name "My Content Type" --webUrl https://contoso.sharepoint.com --force
```

## Response

The command won't return a response on success.
