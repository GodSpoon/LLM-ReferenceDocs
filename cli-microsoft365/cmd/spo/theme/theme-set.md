-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo theme set

Add or update a theme

## Usage

```sh
m365 spo theme set [options]
```

## Options

```md definition-list
`-n, --name <name>`
: Name of the theme to add or update

`-t, --theme <theme>`
: Theme JSON contents

`--isInverted`
: Set to specify that the theme is inverted
```

<Global />

## Remarks

To prevent the accidental creation of invalid themes the CLI for Microsoft 365 implements a set of checks. These checks are executed against the provided json file. A valid theme JSON file is as follows:

```json
{
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
```

When executing the `m365 spo theme set` command the following checks are executed:

- Validate if the provided theme is a valid `JSON` string.
- Validate if the provided theme, once deserialized, contains all properties of the sample above.
- Validate if the provided theme, once deserialized, contains only the properties of the sample above.
- Validate if each of the properties contains a valid hex color value prefixed with a `#`.

If any of these checks fails you are presented with a `The specified theme is not valid` error.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::
    
## Examples

Add or update a theme from a theme JSON file

```sh
m365 spo theme set --name Contoso-Blue --theme @/Users/user/themes/contoso-blue.json
```

Add or update an inverted theme from a theme JSON file

```sh
m365 spo theme set --name Contoso-Blue --theme @/Users/user/themes/contoso-blue.json --isInverted
```

Add or update a theme from inline JSON

```sh
m365 spo theme set --name Contoso-Red --theme '{"themePrimary":"#d81e05","themeLighterAlt":"#fdf5f4","themeLighter":"#f9d6d2","themeLight":"#f4b4ac","themeTertiary":"#e87060","themeSecondary":"#dd351e","themeDarkAlt":"#c31a04","themeDark":"#a51603","themeDarker":"#791002","neutralLighterAlt":"#eeeeee","neutralLighter":"#f5f5f5","neutralLight":"#e1e1e1","neutralQuaternaryAlt":"#d1d1d1","neutralQuaternary":"#c8c8c8","neutralTertiaryAlt":"#c0c0c0","neutralTertiary":"#c2c2c2","neutralSecondary":"#858585","neutralPrimaryAlt":"#4b4b4b","neutralPrimary":"#333333","neutralDark":"#272727","black":"#1d1d1d","white":"#f5f5f5"}'
```

Add or update an inverted theme from inline JSON

```sh
m365 spo theme set --name Contoso-Red --theme '{"themePrimary":"#d81e05","themeLighterAlt":"#fdf5f4","themeLighter":"#f9d6d2","themeLight":"#f4b4ac","themeTertiary":"#e87060","themeSecondary":"#dd351e","themeDarkAlt":"#c31a04","themeDark":"#a51603","themeDarker":"#791002","neutralLighterAlt":"#eeeeee","neutralLighter":"#f5f5f5","neutralLight":"#e1e1e1","neutralQuaternaryAlt":"#d1d1d1","neutralQuaternary":"#c8c8c8","neutralTertiaryAlt":"#c0c0c0","neutralTertiary":"#c2c2c2","neutralSecondary":"#858585","neutralPrimaryAlt":"#4b4b4b","neutralPrimary":"#333333","neutralDark":"#272727","black":"#1d1d1d","white":"#f5f5f5"}' --isInverted
```

## Response

The command won't return a response on success.

## More information

- SharePoint site theming: [https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-theming/sharepoint-site-theming-overview](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-theming/sharepoint-site-theming-overview)
- Theme Generator: [https://aka.ms/themedesigner](https://aka.ms/themedesigner)
