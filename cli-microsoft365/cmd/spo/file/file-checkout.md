-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo file checkout

Checks out specified file

## Usage

```sh
m365 spo file checkout [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the file is located.

`--url [url]`
: The server- or site-relative decoded URL of the file to retrieve. Specify either `url` or `id` but not both.

`-i, --id [id]`
: The UniqueId (GUID) of the file to retrieve. Specify either `url` or `id` but not both.
```

<Global />

## Examples

Checks out file with the specified UniqueId located in the specified site.

```sh
m365 spo file checkout --webUrl https://contoso.sharepoint.com/sites/project-x --id 'b2307a39-e878-458b-bc90-03bc578531d6'
```

Checks out file with the specified server-relative url located in the specified site.

```sh
m365 spo file checkout --webUrl https://contoso.sharepoint.com/sites/project-x --url '/sites/project-x/documents/Test1.docx'
```

## Response

The command won't return a response on success.
