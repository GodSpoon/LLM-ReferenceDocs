-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo theme get

Gets custom theme information

## Usage

```sh
m365 spo theme get [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The name of the theme to retrieve
```

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Get information about a theme

```sh
m365 spo theme get --name Contoso-Blue
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "IsInverted": false,
    "Name": "Contoso-Blue",
    "Palette": {
      "themePrimary": "#d81e05",
      "themeLighterAlt": "#fdf5f4",
      "themeLighter": "#f9d6d2",
      "themeLight": "#f4b4ac",
      "themeTertiary": "#e87060",
      "themeSecondary": "#dd351e",
      "themeDarkAlt": "#c31a04",
      "themeDark": "#a51603",
      "themeDarker": "#791002",
      "neutralLighterAlt": "#eeeeee",
      "neutralLighter": "#f5f5f5",
      "neutralLight": "#e1e1e1",
      "neutralQuaternaryAlt": "#d1d1d1",
      "neutralQuaternary": "#c8c8c8",
      "neutralTertiaryAlt": "#c0c0c0",
      "neutralTertiary": "#c2c2c2",
      "neutralSecondary": "#858585",
      "neutralPrimaryAlt": "#4b4b4b",
      "neutralPrimary": "#333333",
      "neutralDark": "#272727",
      "black": "#1d1d1d",
      "white": "#f5f5f5"
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  IsInverted: false
  Name      : Contoso-Blue
  Palette   : {"themePrimary":"#d81e05","themeLighterAlt":"#fdf5f4","themeLighter":"#f9d6d2","themeLight":"#f4b4ac","themeTertiary":"#e87060","themeSecondary":"#dd351e","themeDarkAlt":"#c31a04","themeDark":"#a51603","themeDarker":"#791002","neutralLighterAlt":"#eeeeee","neutralLighter":"#f5f5f5","neutralLight":"#e1e1e1","neutralQuaternaryAlt":"#d1d1d1","neutralQuaternary":"#c8c8c8","neutralTertiaryAlt":"#c0c0c0","neutralTertiary":"#c2c2c2","neutralSecondary":"#858585","neutralPrimaryAlt":"#4b4b4b","neutralPrimary":"#333333","neutralDark":"#272727","black":"#1d1d1d","white":"#f5f5f5"}
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  IsInverted,Name
  ,Contoso-Blue
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo theme get --name "Contoso-Blue"

  Date: 2023-06-22

  ## Contoso-Blue

  Property | Value
  ---------|-------
  IsInverted | false
  Name | Contoso-Blue
  ```

  </TabItem>
</Tabs>

## More information

- SharePoint site theming: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-theming/sharepoint-site-theming-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-theming/sharepoint-site-theming-overview)
