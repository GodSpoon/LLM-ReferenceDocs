-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra siteclassification get

Gets site classification configuration

## Usage

```sh
m365 entra siteclassification get [options]
```

## Options

<Global />

## Examples

Get information about the Microsoft 365 Tenant site classification.

```sh
m365 entra siteclassification get
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "UsageGuidelinesUrl": "https://contoso.sharepoint.com/sites/compliance",
    "GuestUsageGuidelinesUrl": "",
    "Classifications": [
      "HBI",
      "MBI",
      "LBI",
      "GDPR"
    ],
    "DefaultClassification": "MBI"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Classifications        : ["HBI","MBI","LBI","GDPR"]
  DefaultClassification  : MBI
  GuestUsageGuidelinesUrl:
  UsageGuidelinesUrl     : https://contoso.sharepoint.com/sites/compliance
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  UsageGuidelinesUrl,GuestUsageGuidelinesUrl,DefaultClassification
  https://contoso.sharepoint.com/sites/compliance,,MBI
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra siteclassification get

  Date: 2023-06-02

  Property | Value
  ---------|-------
  UsageGuidelinesUrl | https://contoso.sharepoint.com/sites/compliance
  GuestUsageGuidelinesUrl |
  DefaultClassification | MBI
  ```

  </TabItem>
</Tabs>

## More information

- SharePoint "modern" sites classification: [https://learn.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification](https://learn.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)
