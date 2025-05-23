-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo list view set

Updates existing list view

## Usage

```sh
m365 spo list view set [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the list is located

`--listId [listId]`
: ID of the list where the view is located. Specify either `listId`, `listTitle`, or `listUrl`.

`--listTitle [listTitle]`
: Title of the list where the view is located. Specify either `listId`, `listTitle`, or `listUrl`.

`--listUrl [listUrl]`
: Server- or site-relative URL of the list. Specify either `listId` , `listTitle` or `listUrl`.

`--id [id]`
: ID of the view to update. Specify `title` or `id` but not both

`--title [title]`
: Title of the view to update. Specify `title` or `id` but not both
```

<Global />

## Remarks

Specify properties to update using their names, eg. `--Title 'New Title' --JSLink jslink.js`

When updating list formatting, the value of the CustomFormatter property must be XML-escaped, eg. `&lt;` instead of `<`.

:::warning[Escaping JSON in PowerShell]

When updating list view formatting for a view with the `--CustomFormatter` option, it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

## Examples

Update the title of the list view specified by its name

```sh
m365 spo list view set --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'My List' --title 'All items' --Title 'All events'
```

Update the title of the list view specified by its ID

```sh
m365 spo list view set --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl '/sites/project-x/lists/Events' --id 330f29c5-5c4c-465f-9f4b-7903020ae1ce --Title 'All events'
```

Update view formatting of the specified list view

<Tabs>
  <TabItem value="PowerShell">

  ```sh
  m365 spo list view set --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'My List' --title 'All items' --CustomFormatter '{\"schema\":\"https://developer.microsoft.com/json-schemas/sp/view-formatting.schema.json\",\"additionalRowClass\": \"=if([$DueDate] &lt;= @now, ''sp-field-severity--severeWarning'', '''')\"}'
  ```

  </TabItem>
  <TabItem value="Bash">

  ```sh
  m365 spo list view set --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'My List' --title 'All items' --CustomFormatter "{\"schema\":\"https://developer.microsoft.com/json-schemas/sp/view-formatting.schema.json\",\"additionalRowClass\": \"=if([$DueDate] &lt;= @now, 'sp-field-severity--severeWarning', '')\"}"
  ```

  </TabItem>
</Tabs>

## Response

The command won't return a response on success.
