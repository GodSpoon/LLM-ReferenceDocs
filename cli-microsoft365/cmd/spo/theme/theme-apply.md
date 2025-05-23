-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo theme apply

Applies theme to the specified site

## Usage

```sh
m365 spo theme apply [options]
```

## Options

```md definition-list
`-n, --name <name>`
: Name of the theme to apply

`-u, --webUrl <webUrl>`
: URL of the site to which the theme should be applied

`--sharePointTheme`
: Set to specify if the supplied theme name is a standard SharePoint theme
```

<Global />

## Remarks

Following standard SharePoint themes are supported by the CLI for Microsoft 365: Blue, Orange, Red, Purple, Green, Gray, Dark Yellow and Dark Blue.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::
    
## Examples

Apply theme to the specified site

```sh
m365 spo theme apply --name Contoso-Blue --webUrl https://contoso.sharepoint.com/sites/project-x
```

Apply a standard SharePoint theme to the specified site

```sh
m365 spo theme apply --name Blue --webUrl https://contoso.sharepoint.com/sites/project-x --sharePointTheme
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  "/sites/team1/_catalogs/theme/Themed/BFCFD35C"
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  /sites/team1/_catalogs/theme/Themed/BFCFD35C
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  /sites/team1/_catalogs/theme/Themed/BFCFD35C
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  /sites/team1/_catalogs/theme/Themed/BFCFD35C
  ```

  </TabItem>
</Tabs>

## More information

- SharePoint site theming: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-theming/sharepoint-site-theming-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-theming/sharepoint-site-theming-overview)
- Theme Generator: [https://aka.ms/themedesigner](https://aka.ms/themedesigner)
