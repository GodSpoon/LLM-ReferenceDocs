-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spp model remove

Deletes a document understanding model

## Usage

```sh
m365 spp model remove [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: The URL of the content center site.

`-i, --id [id]`
: The unique ID of the model. Specify either `id` or `title` but not both.

`-t, --title [title]`
: The display name of the model. Specify either `id` or `title` but not both.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::note

The model must be removed from all libraries before it can be deleted.

:::

## Examples

Delete a SharePoint Premium document understanding model using the model’s UniqueId.

```sh
m365 spp model remove --siteUrl "https://contoso.sharepoint.com/sites/ContentCenter" --id "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc"
```

Delete a SharePoint Premium document understanding model using the model’s title.

```sh
m365 spp model remove --siteUrl "https://contoso.sharepoint.com/sites/ContentCenter" --title "climicrosoft365Model.classifier"
```

## Response

The command won't return a response on success.
