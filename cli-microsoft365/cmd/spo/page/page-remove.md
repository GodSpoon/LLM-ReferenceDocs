-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo page remove

Removes a modern page

## Usage

```sh
m365 spo page remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the page is located.

`-n, --name <name>`
: Name of the page.

`--recycle`
: Send the page to the recycle bin instead of permanently deleting it.

`--bypassSharedLock`
: Remove the page even if it is locked for shared use.

`-f, --force`
: Do not prompt for confirmation.
```

<Global />

## Examples

Remove a modern page

```sh
m365 spo page remove --name HR.aspx --webUrl https://contoso.sharepoint.com/sites/Marketing
```

Remove a modern page without a confirmation prompt

```sh
m365 spo page remove --name HR.aspx --webUrl https://contoso.sharepoint.com/sites/Marketing --force
```

Send a page to the recycle bin

```sh
m365 spo page remove --name HR.aspx --webUrl https://contoso.sharepoint.com/sites/Marketing --recycle
```

Remove a page that is locked

```sh
m365 spo page remove --name HR.aspx --webUrl https://contoso.sharepoint.com/sites/Marketing --bypassSharedLock
```

Remove a page that is located in a subfolder

```sh
m365 spo page remove --name /Departments/People/HR.aspx --webUrl https://contoso.sharepoint.com/sites/Marketing
```

## Response

The command won't return a response on success.
