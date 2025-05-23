-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo navigation node set

Updates a SharePoint navigation node

## Usage

```sh
m365 spo navigation node set [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Absolute URL of the site.

`--id <id>`
: Id of the navigation node.

`--title [title]`
: New title of the navigation node.

`--url [url]`
: New URL of the navigation node. Specify an empty string `""` to update the navigation label to a linkless label.

`--audienceIds [audienceIds]`
: Comma-separated list of group IDs that will be used for audience targeting. Speficy an empty string `""` to clear this value. The limit is 10 ids per navigation node.

`--isExternal [isExternal]`
: Whether the navigation node points to an external URL. Valid values: `true` or `false`.

`--openInNewWindow [openInNewWindow]`
: Open the URL in a new window. Valid values: `true` or `false`.
```

<Global />

## Remarks

To enable/disable audience targeting for the navigation bar, use the [`spo web set`](../web/web-set.mdx) command.

## Examples

Updates the title of a navigation node

```sh
m365 spo navigation node set --webUrl https://contoso.sharepoint.com/sites/marketing --id 2209 --title "Pictures"
```

Updates the URL of a navigation node

```sh
m365 spo navigation node set --webUrl https://contoso.sharepoint.com/sites/marketing --id 2209 --url "https://www.microsoft.com" --isExternal true
```

Updates audience targeting of a navigation node with 3 groups

```sh
m365 spo navigation node set --webUrl https://contoso.sharepoint.com/sites/marketing --id 2209 --audienceIds "61f78c73-f71a-471e-a3b9-15daa936e200,9524e6b4-e663-44fe-b179-210c963e37e7,c42b8756-494d-4141-a575-45f01320e26a"
```

Updates the navigation node so that it opens in a new window

```sh
m365 spo navigation node set --webUrl https://contoso.sharepoint.com/sites/marketing --id 2209 --openInNewWindow true
```

## Response

The command won't return a response on success.
