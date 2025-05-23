-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo folder retentionlabel ensure

Apply a retention label to a folder

## Usage

```sh
m365 spo folder retentionlabel ensure [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the retention label from a file to apply is located.

`--folderUrl [folderUrl]`
: The server- or site-relative decoded URL of the folder that should be labelled. Specify either `folderUrl` or `folderId` but not both.

`-i, --folderId [folderId]`
: The UniqueId (GUID) of the folder that should be labelled. Specify either `folderUrl` or `folderId` but not both.

`--name <name>`
: Name of the retention label to apply to the folder.
```

<Global />

## Remarks

You can also use [spo listitem retentionlabel remove](./../../../cmd/spo/listitem/listitem-retentionlabel-remove.mdx) for removing the retention label from a list item.

## Examples

Applies a retention label to a folder based on the label name and the folderUrl.

```sh
m365 spo folder retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --folderUrl '/Shared Documents' --name 'Some label'
```

Applies a retention label to a folder based on the label name and the folderId.

```sh
m365 spo folder retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --folderId '26541f96-017c-4189-a604-599e083533b8'  --name 'Some label'
```

## Response

The command won't return a response on success.
