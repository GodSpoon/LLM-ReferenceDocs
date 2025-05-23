-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo folder remove

Deletes the specified folder

## Usage

```sh
m365 spo folder remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the folder to be deleted is located.

`--url <url>`
: The server- or site-relative decoded URL of the folder to delete.

`--recycle`
: Recycles the folder instead of actually deleting it.

`-f, --force`
: Don't prompt for confirming deleting the folder.
```

<Global />

## Remarks

The `spo folder remove` command will remove folder only if it is empty. If the folder contains any files, deleting the folder will fail.

## Examples

Remove a folder with a specific site-relative URL.

```sh
m365 spo folder remove --webUrl https://contoso.sharepoint.com/sites/project-x --url '/Shared Documents/My Folder'
```

Remove a folder with a specific server relative URL to the site recycle bin.

```sh
m365 spo folder remove --webUrl https://contoso.sharepoint.com/sites/project-x --url '/sites/project-x/Shared Documents/My Folder' --recycle
```

## Response

The command won't return a response on success.
