-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo tenant recyclebinitem remove

Removes the specified deleted Site Collection from Tenant Recycle Bin

## Usage

```sh
m365 spo tenant recyclebinitem remove [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: URL of the site to remove

`--wait`
: Wait for the site collection to be removed before completing the command

`-f, --force`
: Don't prompt for confirming removing the deleted site collection
```

<Global />

## Remarks

Removing a site collection is by default asynchronous and depending on the current state of Microsoft 365, might take up to few minutes. If you're building a script with steps that require the site to be fully removed, you should use the `--wait` flag. When using this flag, the `m365 spo tenant recyclebinitem remove` command will keep running until it received confirmation from Microsoft 365 that the site has been fully removed.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::
    
## Examples

Removes the specified deleted site collection from tenant recycle bin

```sh
m365 spo tenant recyclebinitem remove --siteUrl https://contoso.sharepoint.com/sites/team
```

Removes the specified deleted site collection from tenant recycle bin and wait for the removing process to complete

```sh
m365 spo tenant recyclebinitem remove --siteUrl https://contoso.sharepoint.com/sites/team --wait
```

## Response

The command won't return a response on success.
