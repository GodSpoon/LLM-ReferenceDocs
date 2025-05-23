-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo page set

Updates modern page properties

## Usage

```sh
m365 spo page set [options]
```

## Options

```md definition-list
`-n, --name <name>`
: Name of the page to update.

`-u, --webUrl <webUrl>`
: URL of the site where the page to update is located.

`-l, --layoutType [layoutType]`
: Layout of the page. Allowed values `Article`, `Home`, `SingleWebPartAppPage`, `RepostPage`, `HeaderlessSearchResults`, `Spaces`, `Topic`.

`-p, --promoteAs [promoteAs]`
: Update the page purpose. Allowed values `HomePage`, `NewsPage`, `Template`.

`--demoteFrom [demoteFrom]`
: Update the page purpose back to a regular article. Allowed values `NewsPage`.

`--commentsEnabled [commentsEnabled]`
: Set to `true`, to enable comments on the page. Allowed values `true`, `false`.

`--publish`
: Set to publish the page.

`--publishMessage [publishMessage]`
: Message to set when publishing the page.

`--description [description]`
: The description to set for the page.

`--title [title]`
: The title to set for the page.

`--content [content]`
: JSON string containing page content.
```

<Global />

## Remarks

If you try to create a page with a name of a page that already exists, you will get a `The file doesn't exists` error.

If you choose to promote the page using the `promoteAs` option or enable page comments, you will see the result only after publishing the page.

Running this command from the Windows Command Shell (cmd.exe) or PowerShell for Windows OS XP, 7, 8, 8.1 without bash installed might require additional formatting for command options that have JSON, XML or JavaScript values because the command shell treat quotes differently. For example, this is how you can add page content from the Windows cmd.exe:

```sh
m365 spo page set --name page.aspx --webUrl https://contoso.sharepoint.com/sites/a-team --content '[{\"controlType\": 4,\"id\": \"42b8afe8-dafe-4c11-bfbf-df5ef5b1feb7\",\"position\": {\"layoutIndex\": 1,\"zoneIndex\": 1,\"sectionIndex\": 1,\"sectionFactor\": 12,\"controlIndex\": 1},\"addedFromPersistedData\": true,\"innerHTML\":\"<p>Hello World</p>\"}]'
```

Note, how the content option has escaped double quotes `'[{\"controlType\": 4,\"id\": \"42b8afe8-dafe-4c11-bfbf-df5ef5b1feb7\",\"position\": {\"layoutIndex\": 1,\"zoneIndex\": 1,\"sectionIndex\": 1,\"sectionFactor\": 12,\"controlIndex\": 1},\"addedFromPersistedData\": true,\"innerHTML\":\"<p>Hello World</p>\"}]'` compared to execution from bash `''[{"controlType": 4,"id": "42b8afe8-dafe-4c11-bfbf-df5ef5b1feb7","position": {"layoutIndex": 1,"zoneIndex": 1,"sectionIndex": 1,"sectionFactor": 12,"controlIndex": 1},"addedFromPersistedData": true,"innerHTML":"<p>Hello World</p>"}]'`.

:::warning[Escaping JSON in PowerShell]

When using the `--content` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

## Examples

Change the layout of the existing page to _Article_

```sh
m365 spo page set --name page.aspx --webUrl https://contoso.sharepoint.com/sites/a-team --layoutType Article
```

Promote the existing article page as a news article

```sh
m365 spo page set --name page.aspx --webUrl https://contoso.sharepoint.com/sites/a-team --promoteAs NewsPage
```

Promote the existing article page as a template

```sh
m365 spo page set --name page.aspx --webUrl https://contoso.sharepoint.com/sites/a-team --promoteAs Template
```

Demote the existing newspage

```sh
m365 spo page set --name page.aspx --webUrl https://contoso.sharepoint.com/sites/a-team --demoteFrom NewsPage
```

Change the page's layout to Home and set it as the site's home page

```sh
m365 spo page set --name page.aspx --webUrl https://contoso.sharepoint.com/sites/a-team --layoutType Home --promoteAs HomePage
```

Enable comments on the existing page

```sh
m365 spo page set --name page.aspx --webUrl https://contoso.sharepoint.com/sites/a-team --commentsEnabled true
```

Publish existing page

```sh
m365 spo page set --name page.aspx --webUrl https://contoso.sharepoint.com/sites/a-team --publish
```

Set page description

```sh
m365 spo page set --name page.aspx --webUrl https://contoso.sharepoint.com/sites/a-team --description "Description to add for the page"
```

Set page content

```sh
m365 spo page set --name page.aspx --webUrl https://contoso.sharepoint.com/sites/a-team --content '[{\"controlType\": 4,\"id\": \"42b8afe8-dafe-4c11-bfbf-df5ef5b1feb7\",\"position\": {\"layoutIndex\": 1,\"zoneIndex\": 1,\"sectionIndex\": 1,\"sectionFactor\": 12,\"controlIndex\": 1},\"addedFromPersistedData\": true,\"innerHTML\":\"<p>Hello World</p>\"}]'
```

## Response

The command won't return a response on success.
