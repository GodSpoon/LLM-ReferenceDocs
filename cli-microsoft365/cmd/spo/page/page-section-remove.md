-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo page section remove

Removes the specified section from a modern page

## Usage

```sh
m365 spo page section remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the page is located.

`-n, --pageName <pageName>`
: Name of the page from which to remove a section.

`-s, --section <section>`
: ID of the section to be removed.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

If the specified `pageName` doesn't refer to an existing modern page, you will get a _File doesn't exists_ error.

## Examples

Remove section of a modern page

```sh
m365 spo page section remove --webUrl https://contoso.sharepoint.com/sites/team-a --pageName home.aspx --section 1
```

## Response

The command won't return a response on success.
