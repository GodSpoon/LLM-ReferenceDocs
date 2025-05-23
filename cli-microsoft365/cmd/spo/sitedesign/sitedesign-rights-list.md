-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo sitedesign rights list

Gets a list of principals that have access to a site design

## Usage

```sh
m365 spo sitedesign rights list [options]
```

## Options

```md definition-list
`-i, --siteDesignId <siteDesignId>`
: The ID of the site design to get rights information from
```

<Global />

## Remarks

If the specified `siteDesignId` doesn't refer to an existing site script, you will get a `File not found` error.

If no permissions are listed, it means that the particular site design is visible to everyone.

## Examples

Get information about rights granted for the site design with ID _2c1ba4c4-cd9b-4417-832f-92a34bc34b2a_

```sh
m365 spo sitedesign rights list --siteDesignId 2c1ba4c4-cd9b-4417-832f-92a34bc34b2a
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "DisplayName": "John",
      "PrincipalName": "i:0#.f|membership|john@contoso.onmicrosoft.com",
      "Rights": "View"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  DisplayName  PrincipalName                                  Rights
  -----------  ---------------------------------------------  ------
  John         i:0#.f|membership|john@contoso.onmicrosoft.com  View
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  DisplayName,PrincipalName,Rights
  John,i:0#.f|membership|john@contoso.onmicrosoft.com,View
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo sitedesign rights list --siteDesignId "00281728-3bc1-41d3-92b6-8fc493dcf4cc"

  Date: 2023-06-22

  ## John

  Property | Value
  ---------|-------
  DisplayName | John
  PrincipalName | i:0#.f\|membership\|john@contoso.onmicrosoft.com
  Rights | View
  ```

  </TabItem>
</Tabs>

## More information

- SharePoint site design and site script overview: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)
