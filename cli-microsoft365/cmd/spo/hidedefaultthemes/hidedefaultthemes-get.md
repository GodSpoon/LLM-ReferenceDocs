-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo hidedefaultthemes get

Gets the current value of the HideDefaultThemes setting

## Usage

```sh
m365 spo hidedefaultthemes get [options]
```

## Options

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Get the current value of the HideDefaultThemes setting.

```sh
m365 spo hidedefaultthemes get
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  false
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  false
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  false
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  false
  ```

  </TabItem>
</Tabs>

## More information

- SharePoint site theming: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-theming/sharepoint-site-theming-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-theming/sharepoint-site-theming-overview)
