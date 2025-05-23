-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo field set

Updates existing list or site column

## Usage

```sh
m365 spo field set [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Absolute URL of the site where the field is located.

`--listId [listId]`
: ID of the list where the field is located (if list column). Specify either `listTitle`, `listId` or `listUrl`.

`--listTitle [listTitle]`
: Title of the list where the field is located (if list column). Specify either `listTitle`, `listId` or `listUrl`.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list where the field is located (if list column). Specify either `listTitle`, `listId` or `listUrl`.

`-i, --id [id]`
: ID of the field to update. Specify either `id`, `title`, or 'internalName' but not all.

`-t, --title [title]`
: Title of the field to update. Specify either `id`, `title`, or 'internalName' but not all.

`--internalName [internalName]`
: Internal name of the field to update. Specify either `id`, `title`, or 'internalName' but not all.

`--updateExistingLists`
: Set, to push the update to existing lists. Otherwise, the changes will apply to new lists only.
```

<Global />

## Remarks

Specify properties to update using their names, eg. `--Title 'New Title' --JSLink jslink.js`.

:::warning[Escaping JSON in PowerShell]

When updating column formatting for a field with the `--CustomFormatter` option, it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

## Examples

Update the title of the site column specified by its internal name and push changes to existing lists.

```sh
m365 spo field set --webUrl https://contoso.sharepoint.com/sites/project-x --internalName 'MyColumn' --updateExistingLists --Title 'My column'
```

Update the title of the site column specified by its title and push changes to existing lists.

```sh
m365 spo field set --webUrl https://contoso.sharepoint.com/sites/project-x --title 'MyColumn' --updateExistingLists --Title 'My column'
```

Update the title of the list column specified by its ID.

```sh
m365 spo field set --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'My List' --id 330f29c5-5c4c-465f-9f4b-7903020ae1ce --Title 'My column'
```

Update the description of a column specified by the ID on a list retrieved by the URL.

```sh
m365 spo field set --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl '/sites/project-x/Lists/My List' --id 330f29c5-5c4c-465f-9f4b-7903020ae1ce --Description 'My column Description'
```

Update column formatting of the specified list column based on title.

```sh
m365 spo field set --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'My List' --title 'MyColumn' --CustomFormatter '{"schema":"https://developer.microsoft.com/json-schemas/sp/column-formatting.schema.json", "elmType": "div", "txtContent": "@currentField"}'
```
Update column formatting of the specified list column based on internalName.

```sh
m365 spo field set --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'My List' --internalName 'MyColumn' --CustomFormatter '{"schema":"https://developer.microsoft.com/json-schemas/sp/column-formatting.schema.json", "elmType": "div", "txtContent": "@currentField"}'
```

## Response

The command won't return a response on success.
