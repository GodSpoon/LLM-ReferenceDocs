-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo page section get

Get information about the specified modern page section

## Usage

```sh
m365 spo page section get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the page to retrieve is located.

`-n, --pageName <pageName>`
: Name of the page to get section information of.

`-s, --section <sectionId>`
: ID of the section for which to retrieve information.
```

<Global />

## Remarks

If the specified `pageName` doesn't refer to an existing modern page, you will get a _File doesn't exists_ error.

## Examples

Get information about the specified section of the modern page

```sh
m365 spo page section get --webUrl https://contoso.sharepoint.com/sites/team-a --pageName home.aspx --section 1
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "order": 1,
    "columns": [
      {
        "factor": 12,
        "order": 1,
        "dataVersion": "1.0",
        "jsonData": "&#123;&quot;displayMode&quot;&#58;2,&quot;position&quot;&#58;&#123;&quot;sectionFactor&quot;&#58;12,&quot;sectionIndex&quot;&#58;1,&quot;zoneIndex&quot;&#58;1&#125;&#125;"
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  columns: [{"factor":12,"order":1}]
  order  : 1
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  order,columns
  1,"[{""factor"":12,""order"":1}]"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo page section get --webUrl "https://contoso.sharepoint.com/sites/team-a" --pageName "home.aspx" --section "1"

  Date: 5/3/2023

  Property | Value
  ---------|-------
  order | 1
  ```

  </TabItem>
</Tabs>
