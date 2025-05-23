-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo page section list

List sections in the specific modern page

## Usage

```sh
m365 spo page section list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the page to retrieve is located.

`-n, --pageName <pageName>`
: Name of the page to list sections of.
```

<Global />

## Remarks

If the specified `pageName` doesn't refer to an existing modern page, you will get a _File doesn't exists_ error.

## Examples

List sections of a modern page

```sh
m365 spo page section list --webUrl https://contoso.sharepoint.com/sites/team-a --pageName home.aspx
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
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
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  order  columns
  -----  -------
  1      1
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  order,columns
  1,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo page section list --webUrl "https://contoso.sharepoint.com/sites/team-a" --pageName "home.aspx"

  Date: 5/3/2023

  Property | Value
  ---------|-------
  order | 1

  ```

  </TabItem>
</Tabs>
