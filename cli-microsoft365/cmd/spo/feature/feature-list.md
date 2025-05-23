-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo feature list

Lists Features activated in the specified site or site collection

## Usage

```sh
m365 spo feature list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site (collection) to retrieve the activated Features from

`-s, --scope [scope]`
: Scope of the Features to retrieve. Allowed values `Site,Web`. Default `Web`
```

<Global />

## Examples

Return details about Features activated in the specified site collection

```sh
m365 spo feature list --webUrl https://contoso.sharepoint.com/sites/test --scope Site
```

Return details about Features activated in the specified site

```sh
m365 spo feature list --webUrl https://contoso.sharepoint.com/sites/test --scope Web
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "DefinitionId": "3019c9b4-e371-438d-98f6-0a08c34d06eb",
      "DisplayName": "TenantSitesList"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  DefinitionId                          DisplayName
  ------------------------------------  ------------------------
  3019c9b4-e371-438d-98f6-0a08c34d06eb  TenantSitesList
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  DefinitionId,DisplayName
  3019c9b4-e371-438d-98f6-0a08c34d06eb,TenantSitesList
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo feature list --webUrl "https://contoso.sharepoint.com/sites/test" --scope "Site"

  Date: 10/3/2023

  ## TenantSitesList

  Property | Value
  ---------|-------
  DefinitionId | 3019c9b4-e371-438d-98f6-0a08c34d06eb
  DisplayName | TenantSitesList
  ```

  </TabItem>
</Tabs>
