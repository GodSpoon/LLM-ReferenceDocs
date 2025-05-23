-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo contenttype field set

Adds or updates a site column reference in a site content type

## Usage

```sh
m365 spo contenttype field set [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Absolute URL of the site where the content type is located.

`--contentTypeId <contentTypeId>`
: ID of the content type on which the field reference should be set.

`-i, --id <id>`
: ID of the field to which the reference should be set.

`-r, --required [required]`
: Set to `true`, if the field should be required or to `false` if it should be optional.

`--hidden [hidden]`
: Set to `true`, if the field should be hidden or to `false` if it should be visible.
```

<Global />

## Remarks

If the field reference already exists, the command will update its _required_ and _hidden_ properties as specified in the command.

## Examples

Add the specified site column to the specified content type as an optional and visible field.

```sh
m365 spo contenttype field set --webUrl https://contoso.sharepoint.com/sites/portal --contentTypeId 0x01007926A45D687BA842B947286090B8F67D --id ebe7e498-44ff-43da-a7e5-99b444f656a5
```

Add the specified site column to the specified content type as a required field.

```sh
m365 spo contenttype field set --webUrl https://contoso.sharepoint.com/sites/portal --contentTypeId 0x01007926A45D687BA842B947286090B8F67D --id ebe7e498-44ff-43da-a7e5-99b444f656a5 --required true
```

Update the existing site column reference in the specified content type to optional.

```sh
m365 spo contenttype field set --webUrl https://contoso.sharepoint.com/sites/portal --contentTypeId 0x01007926A45D687BA842B947286090B8F67D --id ebe7e498-44ff-43da-a7e5-99b444f656a5 --required false
```

## Response

The command won't return a response on success.
