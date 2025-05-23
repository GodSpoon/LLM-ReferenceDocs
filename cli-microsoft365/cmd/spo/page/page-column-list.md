-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo page column list

Lists columns in the specific section of a modern page

## Usage

```sh
m365 spo page column list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the page to retrieve is located.

`-n, --pageName <pageName>`
: Name of the page to list columns of.

`-s, --section <sectionId>`
: ID of the section for which to list columns.
```

<Global />

## Remarks

If the specified `pageName` doesn't refer to an existing modern page, you will get a _File doesn't exists_ error.

## Examples

List columns in the first section of a modern page

```sh
m365 spo page column list --webUrl https://contoso.sharepoint.com/sites/team-a --pageName home.aspx --section 1
```


## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "factor": 12,
      "order": 1,
      "dataVersion": "1.0",
      "jsonData": "&#123;&quot;displayMode&quot;&#58;2,&quot;position&quot;&#58;&#123;&quot;sectionFactor&quot;&#58;12,&quot;sectionIndex&quot;&#58;1,&quot;zoneIndex&quot;&#58;1&#125;&#125;",
      "controls": 1
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  controls: 1
  factor  : 12
  order   : 1
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  factor,order,controls
  12,1,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo page column list --webUrl "https://contoso.sharepoint.com/sites/team-a" --pageName "home.aspx" --section "1"

  Date: 5/1/2023

  Property | Value
  ---------|-------
  factor | 6
  order | 1
  dataVersion | 1.0
  jsonData | &#123;&quot;displayMode&quot;&#58;2,&quot;position&quot;&#58;&#123;&quot;sectionFactor&quot;&#58;6,&quot;sectionIndex&quot;&#58;1,&quot;zoneIndex&quot;&#58;1&#125;&#125;
  controls | 1    
  ```

  </TabItem>
</Tabs>
