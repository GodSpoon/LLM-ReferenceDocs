-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo knowledgehub set

Sets the Knowledge Hub Site for your tenant

## Usage

```sh
m365 spo knowledgehub set [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: URL of the site to set as Knowledge Hub.
```

<Global />

## Remarks

If the specified url doesn't refer to an existing site collection, you will get a `404 - "404 FILE NOT FOUND"` error.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::
    
## Examples

Sets the Knowledge Hub Site for your tenant.

```sh
m365 spo knowledgehub set --siteUrl https://contoso.sharepoint.com/sites/knowledgesite
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  "The knowledge hub site with url \"https://contoso.sharepoint.com\" is added to list."
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  The knowledge hub site with url "https://contoso.sharepoint.com" is added to list.
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  The knowledge hub site with url "https://contoso.sharepoint.com" is added to list.
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  The knowledge hub site with url "https://contoso.sharepoint.com" is added to list.
  ```

  </TabItem>
</Tabs>
